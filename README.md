# Dotfiles

Wayland desktop configuration files for a Hyprland-based setup.

## What’s here

- `hypr/` - Hyprland configuration, including startup, display layout, input, and theme variables.
- `waybar/` - Waybar panel config and styling.
- `swaync/` - Sway Notification Center config and styling.

## Components

The configs reference these tools and apps:

- `hyprland`
- `hyprpaper`
- `waybar`
- `swaync`
- `hyprlauncher`
- `kitty`
- `dolphin`
- `chromium`
- `nm-applet`
- `pavucontrol`
- `btop`
- `impala`

The Hyprland config also starts a few user services and helper processes on login, including `hyperpolkitagent` and `swaywc`.

## Layout notes

- The Hyprland config is set up for two displays:
  - `HDMI-A-1` at `1920x1080@60`
  - `eDP-1` at `2560x1440@165`
- Wallpapers are loaded through `hyprpaper` from `$HOME/Wallpapers/`.
- Waybar uses a dark themed palette with accent colors that match the notification styling.
- SwayNC is configured to appear on the top-right and uses a matching theme in `swaync/style.css`.

## Files

### `hypr/hyprland.conf`

Main Hyprland configuration:

- display outputs
- autostart applications
- environment variables
- window gaps, borders, blur, shadows, and animations
- input settings

### `hypr/hyprpaper.conf`

Wallpaper configuration for both monitors.

### `hypr/hyprlauncher.conf`

Launcher behavior, cache, and UI sizing.

### `hypr/hyprtoolkit.conf`

Color and typography settings for the launcher/theme toolkit.

### `waybar/config.jsonc`

Panel modules and module behavior, including:

- workspaces
- clock
- idle inhibitor
- notification indicator
- audio
- network
- power profiles
- CPU
- battery
- power menu

### `waybar/style.css`

Visual styling for the Waybar modules.

### `waybar/power_menu.xml`

Menu definition used by the custom power button.

### `swaync/config.json`

SwayNC behavior, widget layout, and notification handling.

### `swaync/style.css`

SwayNC theme styling.

## Install

The repo does not currently include an installer. Copy or symlink the relevant folders into `~/.config/`:

```bash
~/.config/hypr/
~/.config/waybar/
~/.config/swaync/
```

Example:

```bash
ln -s /home/silver/code/dotfiles/hypr ~/.config/hypr
ln -s /home/silver/code/dotfiles/waybar ~/.config/waybar
ln -s /home/silver/code/dotfiles/swaync ~/.config/swaync
```

## Notes

- The configs contain a few hard-coded paths such as `$HOME/Wallpapers/`.
- If you use different monitor names, update the Hyprland and Hyprpaper monitor entries.
- If a referenced helper binary is missing, remove or replace the corresponding `exec-once` or click action.
