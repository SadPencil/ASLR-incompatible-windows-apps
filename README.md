# ASLR-incompatible-windows-apps
A collection of known apps that have conflicts with the mandatory ASLR feature.

Make a pull request if you find another incompatible app.

## Why should I care
Mandatory ASLR improves system security. Though it has not become the default option for fresh Windows 10 / 11 installations, your new machine might have this feature turned on by OEMs.

But not all apps are ready for this. Incompatible apps crash with an unfriendly error message. Instead of completely turning off this feature, you may also choose to set up bypass rules according to the filename if you are a super fan of security.

## Incompatible Apps

### JetBrains IDE
All the launcher exes are incompatible:
- `idea64.exe`
- `pycharm64.exe`
- `goland64.exe`
- and so on.

**Workaround:** use the `.bat` file as the launcher, e.g. use `idea.bat` in favor of `idea64.exe`

See also:
- https://youtrack.jetbrains.com/issue/IDEABKL-7997

### Git, Cygwin, and MSYS2
Shells and all programs that depend on `fork()`:
- `sh.exe`
- `bash.exe`
- and so on.

See also:
- https://github.com/desktop/desktop/issues/9089

### TeX
The launcher for running `latexindent.pl`.
- `latexindent.exe`

### NSIS installers (old versions)
App installers that are packed up by old-version NSIS.
Example: [TeXstudio v4.2.2](https://github.com/texstudio-org/texstudio/releases/tag/4.2.2)

According to https://github.com/multitheftauto/mtasa-blue/issues/435, this bug was fixed in version 3.03 of NSIS.

### Game: Red Alert 2 mods (Ares-based)
- `gamemd.exe`

Ares injects the game executable file to provide extended gaming features, but the injection fails when ASLR turns on.
