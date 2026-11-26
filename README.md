<p align="center">
  <img width="256" height="256" alt="app" src="https://github.com/user-attachments/assets/f60394af-d66c-452a-af83-8d424edf223b" />




<h1 align="center">Røbin's Optimizer</h1>

<p align="center">
  A Windows 10/11 optimizer with a modern glass UI.<br>
  Every change is backed up first and can be undone with one switch.
</p>

---

## Highlights

- **Real state, not guesses** – every switch reads the actual value from the registry / system.
- **Backup first** – original values are saved before anything is changed; each tweak can be switched off again.
- **One-click performance profile** – or pick tweaks one by one.
- **Custom glass UI** – borderless rounded window, collapsible sidebar, tray icon.

## Features

### Overview
- **Performance profile**: Game Mode on, Game Bar/DVR off, lean visual effects, 1:1 mouse, Delivery Optimization off, multimedia scheduler, Ultimate Performance power plan.
- **Clean system** shortcut.
- **Apply recommended tweaks** or **apply all tweaks** (Defender and app/feature removal are never part of "all").
- **Defender tweaks** as a separate, clearly warned action.
- **About & updates**: checks the latest GitHub release and updates itself (SHA-256 verified, GitHub downloads only).

### Tweaks (18 categories, hundreds of switches)
| Category | What it covers |
|---|---|
| Privacy & Security | Telemetry, advertising, suggestions, search, app permissions, network hardening |
| Energy | Power plan, hibernation, USB / PCIe / Wi-Fi power saving, timeouts |
| Gaming & Performance | Game Mode, mouse, scheduler, services, memory, visual effects |
| Update | Restart behavior, drivers, deferral, Store and Insider settings |
| Notifications | Tips, lock screen, welcome screens, toasts |
| Sound | Startup sound, volume ducking, beeps, voice activation |
| Privacy (Extended) | More telemetry, content delivery, cross-device, permissions |
| Security (Defender) | Defender, SmartScreen, attachment scanning *(lowers protection)* |
| CPU/Kernel Mitigations | VBS, Credential Guard, Spectre/Meltdown mitigations |
| AI / Copilot / Recall | Copilot, Recall, AI components and policies |
| Explorer / UI | Explorer, taskbar, Start, context menus |
| Visuals / Animations | Animations, effects, wallpaper quality, window behavior |
| Hardware | Bluetooth, printing, Wi-Fi |
| Apps & Bloatware | Store, OneDrive, Edge, Teams and other preinstalled apps |
| Services | Telemetry, legacy and unused services (set to disabled + stopped) |
| Scheduled Tasks | Telemetry, sync, diagnostics and maintenance tasks |
| System & Features | Hyper-V, optional Windows features, hypervisor boot option, OneDrive |
| Other | Everything else |

Tweak types: registry values, services, scheduled tasks, Appx packages, Windows features (DISM), BCD options, device-level settings, power plans / powercfg, OneDrive removal.

### Apps & Overlays
Debloat options for **Discord**, **Steam** and **Spotify** (all optional, most reversible):
- Disable autostart (entry is switched off, not deleted)
- Quit completely on close (Discord)
- Disable the Steam overlay, Steam library low-performance mode
- No track-change notifications, hide friend feed, limit stream cache to 1 GB (Spotify)
- Clear caches / logs / crash dumps, remove old Discord versions
- Optional: turn off hardware acceleration

### Network
- DNS provider switcher (applies to all connected adapters) and **DNS speed test**
- Flush DNS cache
- Reset network stack (Winsock / TCP-IP)
- Latency tweaks (e.g. Nagle)

### Cleanup
Scans first, then removes only what you tick: user/Windows temp, Windows Update download cache, Delivery Optimization cache, error reports and crash dumps, log files, thumbnail cache, GPU shader caches (NVIDIA / AMD / Intel / DirectX), browser caches (Chrome, Edge, Brave, Vivaldi, Firefox), Recycle Bin. No documents, passwords, cookies or history.

### System & Disk
- Live CPU / RAM load and uptime
- Drive overview, SSD/HDD detection, TRIM status + enable TRIM, optimize drives
- Biggest memory users (end a program with one click; system processes and this app are protected)
- Memory & storage tweaks

### Autostart
Lists startup entries and enables/disables them exactly like Task Manager (StartupApproved) – nothing is deleted.

### Installer (winget)
One-click multi-install of current versions: Discord, Steam, Spotify, Epic Games Launcher, Brave, Malwarebytes, Proton VPN, Revo Uninstaller, 7-Zip, PowerToys, HWiNFO, WhoCrashed, Rufus, OCCT, OBS Studio, NVCleanstall, Visual Studio Code.

### Utilities
Quick access to Task Manager, Device Manager, Disk Management, Services, Resource Monitor, System Information, Disk Cleanup, Windows Update / Startup settings, handy terminal commands (flush DNS, IP config, ping, `sfc /scannow`, DISM repair), PowerShell snippets and useful download links. The list is easy to edit in `UTILITIES`.

### Backup & Undo
- Create a Windows **restore point**
- **Reset all tweaks** to the backed-up original values
- Backups live in `%APPDATA%\WindowsOptimizerPro`

### Tray icon
Closing the window with **X** hides it in the system tray. Left-click / double-click the tray icon to open it again, right-click → **Exit** to quit. Set `CLOSE_TO_TRAY = False` to quit on close instead.

## Requirements

- Windows 10 / 11 (real glass effect needs Windows 11 22H2+, otherwise a painted fallback is used)
- Administrator rights for most tweaks (the app asks for them on start)
- Python 3.10+ (only when running from source)

## Run from source

```bat
pip install -r requirements.txt
python windows_optimizer_en.py
```

Keep `app.ico` in the same folder as the script.

## Build a single .exe

Put `windows_optimizer_en.py`, `app.ico` and `requirements.txt` in one folder and run `build.bat`, or manually:

```bat
pip install customtkinter pillow pystray pyinstaller
pyinstaller --onefile --noconsole --clean --name "RobinsOptimizer" --icon "app.ico" --add-data "app.ico;." --collect-all customtkinter windows_optimizer_en.py
```

The result is `dist\RobinsOptimizer.exe` – one file, with the icon on the exe, in the taskbar and in the tray.

## Self-update

Set `GITHUB_REPO = "your-name/your-repo"` in the script and attach `RobinsOptimizer.exe` to your GitHub release.

## ⚠️ Disclaimer

This tool changes system settings. Create a restore point first (Backup & Undo). Disabling Defender, services or removing apps/features lowers security or cannot be undone for removed apps. Use at your own risk.

## License

Copyright (c) 2026 R0bin-00. All rights reserved.
