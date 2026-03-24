# cdp-launch

Launches Microsoft Edge with remote debugging enabled so CDP clients can connect.

## Requirements

- Windows PowerShell 5.1+ or PowerShell 7+
- Microsoft Edge installed

## Usage

```bash
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-launch/scripts/launch_edge_debug.ps1
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-launch/scripts/launch_edge_debug.ps1 -Port 9333
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-launch/scripts/launch_edge_debug.ps1 -Port 9223 -BrowserPath "C:\Program Files\Microsoft\Edge\Application\msedge.exe"
```

## Behavior

- Detects Edge from the registry, `Get-Command`, or standard install paths
- Uses port `9223` by default
- Creates an isolated browser profile unless `-UserDataDir` is provided
- Prints JSON with the chosen port, debug URL, browser path, and user-data directory
