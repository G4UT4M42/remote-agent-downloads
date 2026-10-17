# Remote Agent — Windows beta download

> **Installer upload pending.** This repository has been created, but `RemoteAgent-Emergency-Beta-2.6.35.zip` has not yet been uploaded. There is currently no working installer download in this repository. The instructions and checksum below describe the prepared package, not an available release.

This repository is intended for a temporary, **manual Windows beta installer** provided by the project owner. The prepared package includes the fix for the persistent 128-entry execution-journal blockage. This repository is separate from the private development repository and the regular Hetzner installer/update channel.

## Installation instructions — once the ZIP is available

1. Download the published ZIP and extract **all files** into a new folder.
2. Double-click `Install-RemoteAgent.cmd` in the extracted folder, using your normal Windows user account. Do not run it as SYSTEM.
3. Follow the browser account sign-in and device-pairing instructions. An Internet connection and a Remote Agent account are required.

**For new current-user installations only. Do not install this package over an existing Remote Agent background-service or dual-mode installation.** Those installations need a separately qualified service update.

## Beta status and limitations

The embedded journal fix has passed focused regression tests and was checked on the owner's Windows computer. The emergency installer wrapper has passed PowerShell syntax and package-integrity checks; **a full clean-machine installation test of this wrapper has not been completed**.

This bundle is **not a signed automatic product update**. Its checksum verifies that the downloaded bytes match the prepared package; it is not a digital signature proving publisher identity. Do not disable operating-system or antivirus protections to run it. This repository does not mean the regular `/downloads/windows` endpoint or the automatic-update channel has been repaired.

## Prepared package identity

File: `RemoteAgent-Emergency-Beta-2.6.35.zip`  
Size: **2,108,109 bytes**

Expected SHA-256:

```text
bfe8f6d9a87dd9b6c8c76d84863781539e064ed739d43e9550f26a2196c6090b
```

After downloading the actual ZIP, verify it in PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath '.\RemoteAgent-Emergency-Beta-2.6.35.zip'
```

Compare the resulting hash with the value above or [SHA256SUMS.txt](SHA256SUMS.txt).

The prepared ZIP contains `Install-RemoteAgent.cmd`, `install.ps1`, `manifest.json`, `README.txt`, and the embedded `remote-agent-2.6.35.zip`. The installer validates the embedded package hash and file inventory before installation.

## Build identity

| Component | Identity |
| --- | --- |
| Agent version | 2.6.35 |
| Source commit | `b3deb787788e2d94402e069247e9198c4cc2e7f2` |
| Embedded Agent ZIP SHA-256 | `538c11ffc70ed26f7744101e74e5abe4b3ddd55c937b86cf88d41f5aec2f31df` |
| Fixed `desktop_worker.py` SHA-256 | `76d9feaf6f521dae02cdf33a7ccd6ebe09ecdb20a7029b3adc3d0734e94f703f` |

Repository and documentation created on 17 October 2026. **Installer publication is not complete.**
