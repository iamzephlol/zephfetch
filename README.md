# zephfetch

Minimal system info fetch with random cat ASCII art — works on **every distro**, **macOS**, **Windows**, and **Android**.

## Features

- **Works everywhere** — Linux, macOS, Windows CMD/PowerShell, Git Bash, MSYS2, Cygwin, WSL, Termux, NixOS
- **27+ package managers** — pacman, apt, dnf, yum, zypper, emerge, nix, flatpak, snap, apk, xbps, brew, port, eopkg, guix, pkg, cargo, gem, npm, pip, winget, choco
- **12 random cat ASCII art** variants on every run
- **10 themed layouts** — box, side, tree, clean, card, vertical, dots, retro, json, compact
- **Animated GIF/WebP** image display via chafa
- **Extended info** (`-mi`) — host, resolution, CPU, GPU, swap, shell, terminal, uptime
- **Self-update** from GitHub (`--update`)
- **No config needed** — just run and go

## Installation

### Universal (any platform)
```bash
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

### Linux

**Arch Linux (AUR):**
```bash
yay -S zephfetch
```

**Debian / Ubuntu / Linux Mint / Pop!_OS:**
```bash
sudo apt install curl git
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

**Fedora / RHEL / CentOS:**
```bash
sudo dnf install curl git
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

**openSUSE / SUSE:**
```bash
sudo zypper install curl git
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

**Gentoo:**
```bash
sudo emerge git curl
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

**Alpine Linux:**
```bash
sudo apk add curl
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

**Void Linux:**
```bash
sudo xbps-install -Sy curl
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

**NixOS:**
```bash
nix-shell -p curl --run 'curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch && chmod +x ~/.local/bin/zephfetch'
```

**Termux / Android:**
```bash
pkg update && pkg install curl
curl -o $PREFIX/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x $PREFIX/bin/zephfetch
```

### macOS
```bash
brew install curl
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

### Windows

**Command Prompt / PowerShell (native):**
```powershell
powershell -Command "Invoke-WebRequest -Uri https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch -OutFile $env:USERPROFILE\.local\bin\zephfetch"
```
- Add `$env:USERPROFILE\.local\bin` to your PATH if not already there
- PowerShell ships with Windows 10/11 by default
- For extended info, `pwsh` (PowerShell 7) is recommended

**Git Bash / MSYS2 / Cygwin:**
```bash
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/iamzephlol/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch
```

## Usage

```bash
zephfetch                  # basic output
zephfetch -mi              # extended info (host, res, cpu, gpu, swap, shell, term, uptime)
zephfetch --image cat.gif  # display animated GIF
zephfetch --theme side     # switch layout
zephfetch --list-themes    # list all themes
zephfetch --update         # self-update from GitHub
zephfetch --help           # show help
```

### Themes

| Theme | Style | Description |
|-------|-------|-------------|
| **thm4** clean | Lines | Default — clean horizontal separators |
| thm1 classic | Box | Original boxed layout |
| thm2 side | Columns | Two-column layout |
| thm3 tree | Tree | Branch/indent style |
| thm5 card | Panel | Rounded card panel |
| thm6 vertical | List | Icons left, values right |
| thm7 dots | Minimal | Dot separators |
| thm8 retro | Retro | UPPERCASE labels |
| thm9 json | Raw | JSON-like output |
| thm10 compact | One-line | Ultra compact |

**Quick switch:** `zephfetch --thm4`, `zephfetch -t clean`

### Image & GIF Support

Full-quality rendering uses terminal graphics protocols. Animated formats (GIF, WebP, APNG, AVIF, JXL) play for ~3 seconds before the info panel prints:

| Terminal | Protocol | Quality |
|----------|----------|---------|
| **kitty** | Kitty graphics | ✅ Full (+ native GIF animation) |
| **wezterm** | Sixels | ✅ Full |
| **iTerm2** | Sixels | ✅ Full |
| **gnome-terminal, tilix, konsole** | Sixels | ✅ Full |
| **alacritty, foot, xterm** | Block symbols (RGB) | ✅ Good |

**Requires:** `chafa` (install: `pacman -S chafa` / `apt install chafa` / `dnf install chafa`)

GIF playback duration is configurable via environment variable:
```bash
ZEPHFETCH_GIF_DURATION=5 zephfetch --image cat.gif   # play 5 seconds
```

Works from **any shell** (bash, zsh, fish, nushell) — the script uses `#!/bin/bash`.

### Package Managers Detected

zephfetch automatically counts packages from whatever is installed on your system:

| Platform | Detected managers |
|----------|-------------------|
| Arch | pacman, flatpak, nix, snap |
| Debian/Ubuntu | apt, flatpak, snap, nix |
| Fedora | dnf, flatpak, snap |
| openSUSE | zypper, flatpak, snap |
| macOS | brew, port, npm, pip, cargo, gem |
| Windows | winget, choco, pip, npm, port |
| Termux | dpkg |
| NixOS | nix (system + user) |
| Alpine | apk |
| Void | xbps |
| Gentoo | portage (emerge) |
| Solus | eopkg |
| Guix | guix |
| FreeBSD | pkg |

## Example Output (default: thm4 clean)

```
──────────────────────────────────────────────────
  user     zeph
──────────────────────────────────────────────────
  kernel   7.2.2-arch1-1
  os       Arch Linux
──────────────────────────────────────────────────
  wm       Hyprland 0.56.2
  disk     78G / 457G (18%)
  memory   1.29 GiB / 7.69 GiB (17%)
  pkgs     1102 total (1088 (pacman) 14 (flatpak))
──────────────────────────────────────────────────
```

## Customization

Edit the script directly to:
- Add/remove info fields
- Change colors
- Add more cat ASCII art
- Modify package managers detected

## Uninstall

```bash
rm ~/.local/bin/zephfetch          # Linux/macOS/Git Bash
rm $PREFIX/bin/zephfetch           # Termux
rm $env:USERPROFILE\.local\bin\zephfetch  # Windows CMD/PowerShell
yay -R zephfetch                   # AUR
```

## License

MIT License - see [LICENSE](LICENSE) for details.
