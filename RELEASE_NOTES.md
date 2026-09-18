# 🚀 Release Notes - v0.1.15

This release introduces comprehensive cursor theme and size synchronization across GTK3, GTK4, XWayland, and X11 legacy applications, ensuring a consistent cursor experience across all desktop windows.

---

## 🌟 Fixes & Enhancements

- **Comprehensive GTK & XWayland Cursor Synchronization**: When changing cursor themes or during system restoration, the app now automatically synchronizes:
  - GTK 3 settings (`~/.config/gtk-3.0/settings.ini`)
  - GTK 4 settings (`~/.config/gtk-4.0/settings.ini`)
  - Xsettingsd configuration daemon (`~/.config/xsettingsd/xsettingsd.conf`)
  - X11 fallback theme (`~/.icons/default/index.theme`)
  - Active XWayland resource database (`xrdb -merge`)
  - User session environment (`systemctl --user import-environment`)
- **Fix Cursor Theme Inconsistency**: Resolves an issue where certain GTK and XWayland applications continued using previously configured or fallback cursor themes instead of the newly selected theme.

---

## 📦 What's Changed

- Implemented `applyGlobalCursor`, `updateGtkSettingsFile`, `updateXsettingsdConfig`, and `updateDefaultIconTheme` in `src/main/index.ts`.
- Integrated global cursor synchronization into `apply_cursor_settings` and startup monitor sync logic.
- Bumped version to `0.1.15` in `package.json`, `package-lock.json`, and `README.md`.