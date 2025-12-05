# 🪟 Full Windows Setup

> Transform Windows into a keyboard-driven powerhouse with tiling window management and a beautiful, customizable workflow.

<div align="center">

![Windows 11](https://img.shields.io/badge/Windows-11-0078D4?style=for-the-badge&logo=windows11&logoColor=white)
![GlazeWM](https://img.shields.io/badge/WM-GlazeWM-FF6B35?style=for-the-badge)
![YASB](https://img.shields.io/badge/Bar-YASB-00D9FF?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

[Features](#-features) • [Installation](#-quick-start) • [Keybindings](#-keybindings) • [Customization](#-customization)

</div>

---

## 🎯 What is This?

A complete Windows desktop environment that brings the power and efficiency of Linux tiling window managers to Windows. Say goodbye to manually resizing windows and hello to a fully keyboard-driven, distraction-free workspace.

<div align="center">
  <img width="100%" alt="Windows Setup Preview" src="https://github.com/user-attachments/assets/2ee28128-6c93-449e-a35a-0c0c57e89220" />
</div>

### Why Use This Setup?

- ⚡ **Lightning Fast**: Navigate your entire desktop without touching the mouse
- 🎨 **Beautiful & Minimal**: Clean aesthetics that keep you focused
- 🔧 **Highly Customizable**: Make it yours with extensive configuration options
- 💪 **Productivity Boost**: Automatic window tiling means more screen space, less distraction
- 🐧 **Linux-Inspired**: Brings the best of i3wm/sway to Windows

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🪟 Tiling Window Manager
**GlazeWM** brings automatic window tiling to Windows:
- Dynamic window layouts
- 9 customizable workspaces
- Vim-style navigation
- Application-specific rules
- Multi-monitor support

</td>
<td width="50%">

### 📊 Status Bar
**YASB** provides real-time system information:
- Workspace indicators
- CPU, RAM, & disk usage
- Network status
- Date & time
- Custom widgets support

</td>
</tr>
<tr>
<td width="50%">

### ⌨️ Keyboard-Centric
Everything at your fingertips:
- Intuitive Vim-style keybindings
- No mouse required
- Customizable shortcuts
- Quick window manipulation

</td>
<td width="50%">

### 💻 Modern Terminal
Complete terminal experience:
- [WezTerm configuration](https://github.com/lazy-blake/windows-terminal-config)
- Oh-my-posh themes
- Fastfetch system info
- Powerline fonts

</td>
</tr>
</table>

---

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have:

- ✅ Windows 10 (version 1903+) or Windows 11
- ✅ Python 3.8 or higher
- ✅ PowerShell 5.1 or higher

### Installation Steps

**1️⃣ Clone the Repository**

```powershell
git clone https://github.com/lazy-blake/Full-Windows-Setup.git
cd Full-Windows-Setup
```

**2️⃣ Install GlazeWM**

Choose your preferred method:

```powershell
# Option A: Using winget (recommended)
winget install glzr-io.glazewm

# Option B: Manual download
# Visit: https://github.com/glzr-io/glazewm/releases
```

**3️⃣ Install YASB**

```powershell
winget install --id AmN.yasb
```

**4️⃣ Deploy Configuration Files**

```powershell
# Create directories if they don't exist
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.glzr\glazewm"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.yasb"

# Copy GlazeWM config
Copy-Item -Path ".\glazewm\config.yaml" -Destination "$env:USERPROFILE\.glzr\glazewm\config.yaml" -Force

# Copy YASB config
Copy-Item -Path ".\yasb\*" -Destination "$env:USERPROFILE\.yasb\" -Recurse -Force
```

**5️⃣ Launch Your New Workflow**

```powershell
# Start GlazeWM (or launch from Start Menu)
Start-Process "glazewm.exe"

# Start YASB
yasb
```

**6️⃣ Add to Startup (Optional but Recommended)**

```powershell
# Open startup folder
shell:startup

# Create shortcuts for GlazeWM and YASB here
```

> 💡 **Pro Tip**: Press `Alt + Enter` to open a terminal and start exploring your new setup!

---

## ⌨️ Keybindings

Master these shortcuts to unlock maximum productivity:

### Core Navigation

| Keybinding | Action |
|------------|--------|
| `Alt + H` | Focus window left |
| `Alt + J` | Focus window down |
| `Alt + K` | Focus window up |
| `Alt + L` | Focus window right |

### Window Management

| Keybinding | Action |
|------------|--------|
| `Alt + Enter` | Open terminal |
| `Alt + Shift + Q` | Close focused window |
| `Alt + Shift + H/J/K/L` | Move window (left/down/up/right) |
| `Alt + F` | Toggle fullscreen |
| `Alt + Space` | Toggle floating mode |
| `Alt + V` | Split vertical |
| `Alt + B` | Split horizontal |

### Workspace Control

| Keybinding | Action |
|------------|--------|
| `Alt + 1-9` | Switch to workspace 1-9 |
| `Alt + Shift + 1-9` | Move window to workspace 1-9 |
| `Alt + Shift + R` | Reload configuration |

> 📖 **All keybindings are fully customizable** in `glazewm/config.yaml`

---

## 🎨 Customization

### Theming GlazeWM

Edit `glazewm/config.yaml` to customize:

```yaml
gaps:
  inner_gap: 8
  outer_gap: 8

focus_borders:
  active:
    enabled: true
    color: "#00D9FF"  # Change this color
  inactive:
    enabled: true
    color: "#484848"
```

### Styling YASB

Modify `yasb/styles.css` for complete bar customization:

```css
/* Example: Change bar background */
.bar {
    background-color: #1a1b26;
    border-bottom: 2px solid #00D9FF;
}
```

### Adding Custom Widgets

Edit `yasb/config.yaml` to enable/disable widgets:

```yaml
widgets:
  left:
    - "workspaces"
    - "active_window"
  center:
    - "clock"
  right:
    - "cpu"
    - "memory"
    - "network"
    - "battery"
```

**Available Widgets:**
- 🔢 Workspaces indicator
- 🪟 Active window title
- 🕐 Clock & calendar
- 💻 CPU usage
- 🧠 RAM usage
- 📊 Disk usage
- 🌐 Network status
- 🔋 Battery indicator
- 🎵 Media controls
- 🔊 Volume control
- ⚡ Custom scripts

---

## 📁 Project Structure

```
Full-Windows-Setup/
├── 📂 glazewm/
│   └── config.yaml          # GlazeWM configuration
├── 📂 yasb/
│   ├── config.yaml          # YASB configuration
│   └── styles.css           # YASB styling
├── 📂 docs/
│   └── screenshots/         # Additional screenshots
└── 📄 README.md
```
---

## 🤝 Contributing

Contributions make the open-source community amazing! Any contributions you make are **greatly appreciated**.

### How to Contribute

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Ideas for Contributions

- 🎨 New color themes
- 📦 Additional widget configurations
- 📖 Documentation improvements
- 🐛 Bug reports and fixes
- ✨ Feature suggestions

---

## 🌟 Showcase

Using this setup? I'd love to see your customizations! 

- Share screenshots in [Discussions](https://github.com/lazy-blake/Full-Windows-Setup/discussions)
- Tag me on Twitter/X with your setup
- Open a PR to add your config to a `community-configs/` folder

---

## 📚 Related Projects

Enhance your Windows workflow even further:

- 🖥️ **[My Windows Terminal Config](https://github.com/lazy-blake/windows-terminal-config)** - Complete terminal setup with WezTerm, oh-my-posh, and fastfetch
- 🔧 **[GlazeWM Official Repo](https://github.com/glzr-io/glazewm)** - Tiling window manager documentation
- 📊 **[YASB Official Repo](https://github.com/denBot/yasb)** - Status bar documentation

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 💖 Acknowledgments

Special thanks to:

- **[GlazeWM Team](https://github.com/glzr-io)** - For creating an amazing tiling window manager for Windows
- **[YASB Contributors](https://github.com/denBot/yasb)** - For the flexible status bar
- **i3wm & sway communities** - For the inspiration
- **You!** - For checking out this project

---

<div align="center">

**⚡ Built with passion by [lazy-blake](https://github.com/lazy-blake) ⚡**

*Transform your Windows workflow from cluttered to keyboard-driven perfection!*

**[⬆ Back to Top](#-full-windows-setup)**

</div>
