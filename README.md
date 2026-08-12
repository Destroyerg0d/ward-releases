# Ward — downloads

This repository exists for one reason: to hold the installer files for
[Ward](https://ward.digitalheroesco.com) somewhere a browser can reach without a login.

**There is no source code here.** Ward's source is private. What you will find under
[Releases](https://github.com/Destroyerg0d/ward-releases/releases) is the same three files the
download page links to, with the same checksums printed beside them.

| Platform | File | Notes |
| --- | --- | --- |
| Windows 10/11, 64-bit | `Ward-<version>.msi` | The supported platform. This is where Ward is developed and tested |
| macOS, Apple silicon | `Ward-<version>.dmg` | Not signed with an Apple Developer ID. macOS refuses the first double-click; right-click the app in Applications, choose Open, then confirm |
| Debian / Ubuntu, 64-bit | `ward_<version>_amd64.deb` | No `.rpm` is built, so there is no Fedora or openSUSE package |

## Verifying what you downloaded

Every release lists a SHA-256 for each file, and the
[download page](https://ward.digitalheroesco.com/download) prints the same digests. They should
match. Recompute yours:

```powershell
Get-FileHash .\Ward-1.0.0.msi -Algorithm SHA256      # Windows
```

```bash
shasum -a 256 Ward-1.0.0.dmg                          # macOS
sha256sum ward_1.0.0_amd64.deb                        # Linux
```

PowerShell prints uppercase hex and the other two print lowercase; compare the letters, not the case.

## What runs where

The test suite passes on all three operating systems. That is not the same as the program working
on all three: Ward is a Windows application, and the parts that find an installed browser, adopt a
process holding a debugging port and read the machine's install layout are Windows-only today. The
macOS and Linux packages are published so they can be tried, not because anyone has run a browser
profile through them. The download page says the same thing in more detail.

Issues and questions: <support@digitalheroes.co.in>.
