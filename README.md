# ASLR-incompatible-windows-apps
A collection of known apps that has conflicts with the mandatory ASLR feature.

Make a pull request if you find another incompatible app.

## Incompatible Apps

### JetBrains IDE
All the launcher exes are incompatible:
- `idea64.exe`
- `pycharm64.exe`
- `goland64.exe`
- and so on.

**Workaround:** use the `.bat` file as the launcher, e.g. use `idea.bat` in favor of `idea64.exe`

### Git, Cygwin, and MSYS2
Shells and all programs that depends on `fork()`:
- `sh.exe`
- `bash.exe`
- and so on.

### TeX
The launcher for running `latexindent.pl`.
- `latexindent.exe`

### NSIS installers (old versions)
App installers that is packed up by old-version NSIS.
Example: [TeXstudio v4.2.2](https://github.com/texstudio-org/texstudio/releases/tag/4.2.2)

According to https://github.com/multitheftauto/mtasa-blue/issues/435, this bug was fixed in version 3.03 of NSIS.

### Game: Red Alert 2 mods (Ares-based)
- `gamemd.exe`
Ares injects the game exe file to provide extended gaming features, but the injection fails when ASLR turns on.
