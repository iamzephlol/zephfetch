# zephfetch


A minimal, fast system info fetch tool written in Bash with random cat ASCII art.
  ```if you hate fastfetch then this is your way to go! it has cute ascii arts and its 100% better than fastfetch```



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

# Display custom image (full quality with graphics protocols)
zephfetch --image /path/to/image.png
zephfetch --image ~/Pictures/cat.jpg

# Show help
zephfetch --help

```

### Image Display Support

Full-quality image rendering uses terminal graphics protocols:

| Terminal | Protocol | Quality |
|----------|----------|---------|
| **kitty** | Kitty graphics | ✅ Full |
| **wezterm** | Sixels | ✅ Full |
| **iTerm2** | Sixels | ✅ Full |
| **gnome-terminal, tilix, konsole** | Sixels | ✅ Full |
| **alacritty, foot, xterm** | Block symbols (RGB) | ✅ Good |

**Requires:** `chafa` (install: `pacman -S chafa` / `apt install chafa` / `dnf install chafa`)

Works from **any shell** (bash, zsh, fish, nushell) - the script uses `#!/bin/bash` shebang.


## Example Output


```
₊˚⊹∧＿∧         ｡
  (  ̳ᴗ  ̫ ᴗ ̳)       ♡ ｡
  ノ    つつ     *.+ﾟ𝒇𝒐𝒓 𝒚𝒐𝒖.♡
 ⊂、  ノ        ♡.    ｡
   し′        ｡・
 """"""""""""""""""""""

  ╭─zeph@zeph─╮
  │  󰣇 user     zeph
  │  󰌛 kernel   7.1.8-arch1-3
  │  󰌽 os       Arch Linux
  │  󰒺 wm       Hyprland 0.56.2
  │  󰋊 disk     55G / 457G (13%)
  │  󰍛 memory   2.03 GiB / 7.69 GiB (26%)
  │  󰏖 pkgs     1102 total (1088 (pacman) 14 (flatpak))
  ╰────────────╯
```


## Customization


Edit the script directly to:

- Add/remove info fields

- Change colors

- Add more cat ASCII art

- Modify package managers detected


## Uninstall


```bash

# If installed via curl/manual copy

rm ~/.local/bin/zephfetch


# If installed via AUR (when available)

yay -R zephfetch

# or

pacman -R zephfetch


# If installed via AUR git version

yay -R zephfetch-git

```

## License


MIT License - see [LICENSE](LICENSE) for details. 
