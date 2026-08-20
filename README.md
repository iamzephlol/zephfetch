# zephfetch

A minimal, fast system info fetch tool written in Bash with random cat ASCII art.

## Features

- **Fast** - Pure bash, no dependencies (except standard coreutils)
- **Random cat ASCII art** - Different cat every run (4 variants)
- **Nerd Font icons** - Clean icons for each info field
- **Minimal** - Shows: user, kernel, OS, window manager, disk, memory, packages
- **No config needed** - Just run and go

## Requirements

- Bash
- Standard coreutils (`df`, `free`, `uname`, `cat`, `awk`, `grep`)
- `pacman` and/or `flatpak` for package counts (Arch-based)
- A [Nerd Font](https://www.nerdfonts.com/) for icons (optional but recommended)

## Installation

```bash
# Clone or copy the script
curl -o ~/.local/bin/zephfetch https://raw.githubusercontent.com/yourrepo/zephfetch/main/zephfetch
chmod +x ~/.local/bin/zephfetch

# Make sure ~/.local/bin is in your PATH
export PATH="$HOME/.local/bin:$PATH"
```

## Usage

```bash
zephfetch
```

## Example Output

```
      |\      _,,,---,,_
ZZZzz /,'.-'`    -.  ;-;;,_
     |,4-  ) )-,_.\ (  `'-'
    '---''(_/--'  `-'\_)

  ╭─user@hostname─╮
  │  󰣇 user     user
  │  󰌛 kernel   6.10.0-arch1-1
  │  󰌽 os       Arch Linux
  │  󰒺 wm       Hyprland 0.56.2
  │  󰋊 disk     54G / 457G (13%)
  │  󰍛 memory   1.44 GiB / 7.69 GiB (19%)
  │  󰏖 pkgs     14 (flatpak), 1062 (pacman)
  ╰────────────╯
```

## Customization

Edit the script directly to:
- Add/remove info fields
- Change colors
- Add more cat ASCII art
- Modify package managers detected

## License

MIT License - see [LICENSE](LICENSE) for details.