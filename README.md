<p align="center">
  <img width="256" height="256" alt="app" src="https://github.com/user-attachments/assets/f60394af-d66c-452a-af83-8d424edf223b" />
</p>

<h1 align="center">Røbin's Optimizer</h1>

<p align="center">
  A Windows 10/11 optimizer with a modern dark UI and smooth animations.<br>
  Every change is backed up first and can be undone with one switch.
</p>

<p align="center">
  <a href="https://github.com/R0bin-00/Robins-Optimizer/releases/latest"><b>⬇ Download the latest release</b></a> ·
  <a href="https://www.youtube.com/@R%C3%B8bin-o8d4t">YouTube</a> ·
  <a href="https://discord.gg/QW6yr9AH9H">Discord</a>
</p>

---

## What's new in 2.0

- **Completely redesigned UI**: new dark look, cleaner layout, smooth page and sidebar animations
- **Fully in English**
- **More tweaks** in every category, including more power-saving features that can be turned off
- **YouTube & Discord buttons** in the top right corner
- **Spotify Controller spotlight** on the Overview. You can close it and bring it back anytime with the icon in the top right

## Highlights

- **Real state, not guesses**: every switch reads the actual value from the registry or system.
- **Backup first**: original values are saved before anything changes, and each tweak can be switched off again.
- **One-click performance profile**, boost presets, or tweaks picked one by one.
- **Custom UI**: borderless rounded window, collapsible animated sidebar, global tweak search.
- **Self-updating**: checks GitHub releases and updates itself (SHA-256 verified, GitHub downloads only).

## Features

### Overview
- **Performance profile**: Game Mode on, Game Bar/DVR off, lean visual effects, 1:1 mouse, Delivery Optimization off, multimedia scheduler, Ultimate Performance power plan.
- **Clean system** shortcut.
- **Apply all recommended** or **apply all tweaks**. Defender is never part of "all".
- **Defender tweaks** as a separate action with a clear warning.
- **System status**: admin rights, Windows version, winget, number of active tweaks.
- **About & updates**: update check plus a quiet automatic check shortly after startup.
- **Spotify Controller** card (can be closed).

### Tweaks: 18 categories, 500+ switches, with search
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

Each category has an **"Apply recommended"** button. Tweak types include registry values, services, scheduled tasks, Appx packages, Windows features (DISM), BCD options, device-level settings, power plans / powercfg and OneDrive removal.

### Performance
- **Boost presets**: *Safe boost* (low-risk speed-ups that don't cost any features) and *Gaming boost* (adds latency tweaks for desktops). Both show how many of their tweaks are active, and each has its own **Undo**.
- **Power plans**: activate, duplicate, rename, delete, plus import / export `.pow` files.
- **USB power management**: block or allow "turn off this device to save power" for all USB devices (or root hubs only), with **Restore original**.
- Extra performance switches.

### Apps & Overlays
Debloat options for **Discord**, **Steam** and **Spotify**. Everything is optional and most of it is reversible:
- Disable autostart (the entry is switched off, not deleted)
- Quit completely on close (Discord)
- Disable the Steam overlay, Steam library low-performance mode
- No track-change notifications, hide friend feed, limit the stream cache to 1 GB (Spotify)
- Run apps with low background priority
- Clear caches / logs / crash dumps, remove old Discord versions
- Optional: turn off hardware acceleration

### Network
- DNS provider switcher (applies to all connected adapters) and **DNS speed test**
- Flush DNS cache
- Reset network stack (Winsock / TCP-IP)
- Latency tweaks (e.g. Nagle)

### Cleanup
Scans first, then removes only what you tick: user/Windows temp, Windows Update download cache, Delivery Optimization cache, error reports and crash dumps, log files, thumbnail cache, GPU shader caches (NVIDIA / AMD / Intel / DirectX), browser caches (Chrome, Edge, Brave, Vivaldi, Firefox), Recycle Bin. It also offers WinSxS component store cleanup. Documents, passwords, cookies and history are never touched.

### System & Disk
- Live CPU / RAM load and uptime
- Drive overview, SSD/HDD detection, TRIM status + enable TRIM, optimize drives
- Biggest memory users: end a program with one click (system processes and this app are protected)
- Memory & storage tweaks

### Autostart
Lists startup entries and turns them on or off the same way Task Manager does (StartupApproved). Nothing is deleted.

### Installer (winget)
One-click multi-install of current versions: Discord, Steam, Spotify, Epic Games Launcher, Brave, Malwarebytes, Proton VPN, Revo Uninstaller, 7-Zip, PowerToys, HWiNFO, WhoCrashed, Rufus, OCCT, OBS Studio, NVCleanstall, Visual Studio Code.

### Utilities
Quick access to Task Manager, Device Manager, Disk Management, Services, Resource Monitor, System Information, Disk Cleanup and Windows Update / Startup settings. Also includes handy terminal commands (flush DNS, IP config, ping, `sfc /scannow`, DISM repair), PowerShell snippets and useful download links.

### Backup & Undo
- Create a Windows **restore point**
- **Reset all tweaks** to the backed-up original values
- Backups are stored in `%APPDATA%\WindowsOptimizerPro`

## ⚠️ Antivirus warnings (false positives)

Some antivirus programs (on VirusTotal around **5 of 67**) flag `Robins-Optimizer.exe` as something like `Trojan.Python` or `malicious_confidence`. **These are false positives.**

Why it happens:
- The .exe is built with **PyInstaller**, which packs Python and the script into one file that unpacks itself when it starts. Malware uses the same packer, so some scanners flag *every* PyInstaller file.
- The app is **not code-signed**, because a signing certificate costs several hundred euros a year.
- An optimizer **asks for admin rights and changes registry values, services and scheduled tasks**. Heuristics treat that as "suspicious behavior", even though that's exactly what the tool is supposed to do.

What you can do:
- **Read the code.** The complete source is in this repo (`windows_optimizer_en.py`). There's no obfuscation and no hidden downloads, and the updater only downloads from GitHub releases of this repo.
- **Run it from source** or **build the .exe yourself** (see below). Then you know exactly what's inside.
- **Check the scan yourself:** [VirusTotal report](https://www.virustotal.com/gui/file/c55a376e841f28580633485c7bf263a9a94aad0533cb75bcdc3dc9c4bec308ac). Every new build has a different hash, so the link always belongs to one specific release.
- **Windows SmartScreen** ("Windows protected your PC"): click **More info → Run anyway**.

## Requirements

- Windows 10 / 11 (64-bit)
- Administrator rights for most tweaks (the app asks for them on start)
- Python 3.10+ (only when running from source)

## Run from source

```bat
pip install customtkinter pillow
python windows_optimizer_en.py
```

Keep `app.ico` in the same folder as the script.

## Build a single .exe

Put `windows_optimizer_en.py` and `app.ico` in one folder, open a terminal **in that folder** and run:

```bat
pip install customtkinter pillow pyinstaller
pyinstaller --onefile --noconsole --name "Robins-Optimizer" --icon "app.ico" --add-data "app.ico;." --collect-all customtkinter --uac-admin windows_optimizer_en.py
```

The result is `dist\Robins-Optimizer.exe`: one file, no Python needed, with the icon on the exe and in the taskbar.

## Self-update

The app checks the latest release of `GITHUB_REPO` (set in the script). Attach `Robins-Optimizer.exe` (and optionally the `.py`) to the release and use a tag that is higher than `APP_VERSION`.

## More from me

- 🎵 **[Spotify Controller](https://github.com/R0bin-00/Spotify-Controller)**: my other tool, a sleek little remote for Spotify
- 🎥 [YouTube](https://www.youtube.com/@R%C3%B8bin-o8d4t)
- 💬 [Discord](https://discord.gg/QW6yr9AH9H): questions, bugs, ideas

## Disclaimer

This tool changes system settings. Create a restore point first (Backup & Undo). Disabling Defender or services lowers security, and apps or features you remove can't be brought back with Undo. Use at your own risk.

## License

Copyright (c) 2026 R0bin-00. All rights reserved.
