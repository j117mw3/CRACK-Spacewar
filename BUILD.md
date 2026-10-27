# Building and testing

Build on 64-bit Windows with Python 3, a Rust `x86_64-pc-windows-msvc`
toolchain and its bundled `lld-link.exe`. The released binary was built with
Rust 1.94.0 (4a4ef493e, LLVM 21.1.8) and Python 3.11.5. The isolated probe
also requires the 64-bit .NET Framework 4 compiler and System.Web.Extensions.
No game files are needed.

From the repository root in PowerShell:

```powershell
python native/build.py
python native/test.py
Get-FileHash native/build/winmm.dll -Algorithm SHA256
```

`build.py` reads the local System32 `winmm.dll` export table and regenerates
`generated.rs` and `exports.s`, then builds the production and test DLLs.
Differences in Windows versions, export tables, Rust toolchains, or build
environment may change the DLL and its hash. The release payload's DLL SHA-256
is `c4be1c436889b2f87b39727bef0a17e1a4ff2cc8cb2f94dad3e09e89dfe3bc26`.
A rebuild should be compared with this value; a different value alone does not
prove incompatibility or equivalence. `test.py` creates disposable probe
executables under `native/build` and tests configuration, the process-name
guard, export resolution, timer and output-pointer forwarding, concurrent
initialization, and integer and floating-point calling conventions. These
checks do not launch the game or establish live multiplayer functionality.
