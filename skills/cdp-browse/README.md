# cdp-browse

Uses the Chrome DevTools Protocol to inspect and control an already-running Edge session.

## Requirements

- Windows PowerShell 5.1+ or PowerShell 7+
- Edge started with remote debugging enabled, typically via `cdp-launch`

## Usage

```bash
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-browse/scripts/edge_cdp.ps1 -Command list
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-browse/scripts/edge_cdp.ps1 -Command navigate -Port 9223 -TargetId TARGET -Url https://example.com
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-browse/scripts/edge_cdp.ps1 -Command get_text -Selector "h1"
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-browse/scripts/edge_cdp.ps1 -Command click -Selector "#submit"
powershell.exe -ExecutionPolicy Bypass -File skills/cdp-browse/scripts/edge_cdp.ps1 -Command evaluate -Expression "document.body.innerText.slice(0, 200)"
```

## Supported commands

- `list`: list CDP targets
- `navigate`: load a new URL in a target
- `get_text`: return `textContent` for a selector
- `click`: click the first matching element
- `evaluate`: run JavaScript and return the result

## Notes

- If `-TargetId` is omitted, the script uses the first target with `type=page`
- The default port is `9223`
- JSON output is intended to be piped into other tooling
