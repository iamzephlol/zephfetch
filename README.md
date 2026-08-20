zephfetch

A minimal, fast system information fetch tool written in pure Bash with random cat ASCII art on every run.
Preview

      |\      _,,,---,,_
ZZZzz /,'.-'`    -.  ;-;;,_
     |,4-  ) )-,_.\ (  `'-'
    '---''(_/--'  `-'\_)

  ╭─user@hostname─╮
  │  󰣇 user    user
  │  󰌛 kernel  6.10.0-arch1-1
  │  󰌽 os      Arch Linux
  │  󰒺 wm      Hyprland 0.56.2
  │  󰋊 disk    54G / 457G (13%)
  │  󰍛 memory  1.44 GiB / 7.69 GiB (19%)
  │  󰏖 pkgs    14 (flatpak), 1062 (pacman)
  ╰────────────╯

Features

    Blazing Fast: Written in pure Bash with minimal subshells for fast execution.

    Zero External Tool Dependencies: Relies entirely on standard Unix utility tools (coreutils, awk, grep).

    Randomized ASCII Art: Switches between 4 distinct cat variants automatically.

    Nerd Font Integration: Displays clean icons for every system field out of the box.

    Zero Configuration: Works right after installation with sensible defaults.

Tracked Metrics

    User & Hostname: Current session user

    Kernel: System kernel version

    OS: Operating system name

    Window Manager: Active desktop environment or window manager

    Disk Usage: Used space vs. total available root space

    Memory Usage: Active RAM vs. total RAM

    Package Count: Installed packages (pacman and flatpak)

Requirements
Core Dependencies

    Bash (v4.0+)

    Standard Core Utilities: df, free, uname, cat, awk, grep

Optional Enhancements

    A Nerd Font installed and set as your terminal font (for icons).

    pacman and/or flatpak installed for package counts.

Installation
One-Line Install

Run the following command to download the script and place it in ~/.local/bin:
Bash

curl -sSLo ~/.local/bin/zephfetch https://raw.githubusercontent.com/yourusername/zephfetch/main/zephfetch && chmod +x ~/.local/bin/zephfetch

Manual Clone
Bash

git clone https://github.com/yourusername/zephfetch.git
cd zephfetch
chmod +x zephfetch
mv zephfetch ~/.local/bin/

    Note: Ensure ~/.local/bin is in your environment PATH. If not, add this to your ~/.bashrc or ~/.zshrc:
    Bash

    export PATH="$HOME/.local/bin:$PATH"

Usage

Run the tool anywhere in your terminal:
Bash

zephfetch

Run on Shell Startup

To display your system details every time you open a terminal, append zephfetch to the end of your shell configuration file:
Bash

# For Bash
echo "zephfetch" >> ~/.bashrc

# For Zsh
echo "zephfetch" >> ~/.zshrc

Customization

Because zephfetch is a single, self-contained shell script, customization is straightforward. Open the script in your editor to adjust:

    ASCII Art: Add or edit cat variants in the internal array.

    Colors: Modify ANSI escape sequences to match your terminal theme.

    Fields: Comment out unwanted rows or add custom metrics (e.g., Uptime, GPU).

    Package Managers: Add detection for apt, dnf, brew, or nix.

License

Distributed under the MIT License. See LICENSE for details.
