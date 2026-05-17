# Desktop set-up

The files I run through to bring a fresh machine up to my usable dev environment.

## Files

- `nameoflist.json` — winget package export. Apps I want on every Windows install (Discord, Docker Desktop, Git, Chrome, MSI Afterburner, HWiNFO, ASIO4ALL, etc.).
- `extensions.list` — VS Code extension IDs.
- `cli_inputs.txt` — the cheatsheet of commands I paste into a fresh terminal.

## How to use it

On the source machine (export current state):
```
winget export -o nameoflist.json
```

On the new machine (install everything from the list):
```
winget import -i nameoflist.json
```

VS Code extensions (PowerShell):
```
cat extensions.list | % { code --install-extension $_ }
```

Or bash:
```
xargs -n1 code --install-extension < extensions.list
```
