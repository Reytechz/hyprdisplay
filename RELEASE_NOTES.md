# 🚀 Release Notes - v0.1.16

This release introduces native Laptop Trackpad management with one-click toggling, real-time desktop synchronization, and persistent settings across system reboots and Hyprland reloads.

---

## 🌟 New Features & Enhancements

- **Native Laptop Trackpad Management**:
  - **Dynamic Device Detection**: Automatically scans connected mice and touchpads using `hyprctl devices -j` to identify internal laptop trackpads (e.g. `elan`, `synaptics`, `dell-touchpad`).
  - **Real-time Toggle**: Enables and disables the trackpad on the fly using Hyprland Lua `hl.device` (with legacy fallback to `hyprctl keyword`), instantly applying state changes without restarting.
  - **Hyprland Config Persistence**: Safely saves device rules into `~/.config/hypr/custom/general.lua` and `~/.config/hypr/custom/general.conf` within `# [nwg-react-displays] start...end` blocks, preventing settings from being overwritten or lost on `hyprctl reload`.
  - **Auto-Restore on Startup & Hotplug**: Persists preferences to `settings.json` and automatically restores your preferred trackpad state on application boot and display plug events.
  - **Quick Header Toolbar Toggle**: Added a 1-click `<Touchpad />` / `<TouchpadOff />` icon button in the top toolbar with visual status badges and tooltips.
  - **Settings Modal Integration**: A dedicated control card with an animated toggle switch, live status indicator, and detected device name.
  - **System Tray Menu Integration**: Added a quick-access checkbox menu item directly inside the system tray context menu for effortless toggling from Waybar or desktop panels.

---

## 📦 What's Changed

- Added `get_touchpad_status` and `set_touchpad_enabled` IPC handlers, `getDetectedTouchpads`, `applyTouchpadSetting`, and `updateCustomTouchpadConfig` in `src/main/index.ts`.
- Integrated trackpad UI controls and event listeners in `src/renderer/src/App.tsx`.
- Bumped version to `0.1.16` in `package.json`, `package-lock.json`, and `README.md`.