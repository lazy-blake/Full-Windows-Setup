# Full Windows Setup

A complete, modern Windows desktop environment featuring a tiling window manager (GlazeWM) and a customizable status bar (YASB) for an efficient, keyboard-driven workflow.

![Windows Setup](https://img.shields.io/badge/Windows-11-blue?logo=windows11)
![GlazeWM](https://img.shields.io/badge/WM-GlazeWM-orange)
![YASB](https://img.shields.io/badge/Bar-YASB-green)

## 🎯 Overview

This repository contains my complete Windows desktop configuration, transforming Windows into a productive, customizable environment inspired by Linux tiling window managers. Perfect for developers, power users, and anyone who prefers keyboard-centric workflows.

## ✨ Features

- **Tiling Window Manager**: GlazeWM for automatic window tiling and keyboard-driven window management
- **Custom Status Bar**: YASB (Yet Another Status Bar) with widgets for system monitoring
- **Keyboard-Centric**: Vim-style keybindings and efficient navigation
- **Windows Terminal**: A clean modern terminal with wezterm, oh-my-posh and fastfetch

## 📦 Components

### GlazeWM

A tiling window manager for Windows inspired by i3wm. Provides automatic window tiling, workspaces, and extensive keyboard control.

### YASB

A highly customizable status bar written in Python. Displays system information, workspace indicators, and custom widgets.

### Windows Terminal

For the complete terminal experience, check out my Windows Terminal configuration:

- 🔗 [Windows Terminal Config Repository](https://github.com/lazy-blake/windows-terminal-config)

## 🚀 Installation

### Prerequisites

- Windows 10/11
- Python 3.8 or higher (for YASB)
- PowerShell 5.1 or higher

### Quick Setup

1. **Clone this repository**

   ```powershell
   git clone https://github.com/lazy-blake/Full-Windows-Setup.git
   cd Full-Windows-Setup
   ```

2. **Install GlazeWM**

   ```powershell
   # Download from: https://github.com/glzr-io/glazewm/releases
   # Or use winget:
   winget install glzr-io.glazewm
   ```

3. **Install YASB**

   ```powershell
   winget install --id AmN.yasb
   ```

4. **Copy Configuration Files**

   ```powershell
   # Copy GlazeWM config
   Copy-Item -Path ".\glazewm\config.yaml" -Destination "$env:USERPROFILE\.glzr\glazewm\config.yaml" -Force

   # Copy YASB config
   Copy-Item -Path ".\yasb\*" -Destination "$env:USERPROFILE\.yasb\" -Recurse -Force
   ```

5. **Start GlazeWM**
   - Launch GlazeWM from the Start Menu or run `glazewm.exe`
   - You have to manually add the exe to the startup(Press win+r , run `shell:startup`)

6. **Start YASB**
   ```powershell
   yasb
   ```

## ⚙️ Configuration

### GlazeWM Configuration

The GlazeWM config file is located at `glazewm/config.yaml`. Key features:

- **Workspaces**: 9 numbered workspaces for organizing applications
- **Keybindings**: Vim-style navigation (Alt+H/J/K/L)
- **Gaps & Borders**: Customizable window gaps and borders
- **Rules**: Application-specific window rules

### YASB Configuration

YASB configuration is in `yasb/config.yaml`. Customize:

- **Widgets**: Choose which information to display
- **Styling**: Colors, fonts, and layout
- **Positioning**: Top, bottom, or side placement

### Key Bindings (Default)

| Keybinding              | Action                                |
| ----------------------- | ------------------------------------- |
| `Alt + Enter`           | Open terminal                         |
| `Alt + Shift + Q`       | Close window                          |
| `Alt + H/J/K/L`         | Navigate windows (left/down/up/right) |
| `Alt + Shift + H/J/K/L` | Move windows                          |
| `Alt + 1-9`             | Switch to workspace                   |
| `Alt + Shift + 1-9`     | Move window to workspace              |
| `Alt + V`               | Split vertical                        |
| `Alt + H`               | Split horizontal                      |
| `Alt + F`               | Toggle fullscreen                     |
| `Alt + Space`           | Toggle floating                       |

## 🎨 Customization

### Themes

Both GlazeWM and YASB support theming. Modify color schemes in their respective config files:

- **GlazeWM**: Edit `glazewm/config.yaml` under `gaps` and `focus_borders`
- **YASB**: Edit `yasb/styles.css` for bar styling

### Adding Widgets

YASB supports various widgets. Edit `yasb/config.yaml` to add or remove:

- Clock & Date
- CPU/RAM usage
- Network status
- Battery indicator
- Custom scripts
- And more...

## 📁 Repository Structure

```
Full-Windows-Setup/
├── glazewm/
│   └── config.yaml          # GlazeWM configuration
├── yasb/
│   ├── config.yaml          # YASB configuration
│   └── styles.css           # YASB styling
└── README.md
```

## 🔧 Troubleshooting

### GlazeWM not starting

- Ensure you have the latest version installed
- Check Task Manager for conflicting window managers
- Review logs at `%USERPROFILE%\.glzr\glazewm\glazewm.log`

### YASB not displaying

- Verify Python and pip are in your PATH
- Check YASB is running in Task Manager
- Review YASB logs: `yasb --log-level DEBUG`

### Keybindings not working

- Ensure GlazeWM is running
- Check for keybinding conflicts with other applications
- Verify config.yaml syntax is correct

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs
- Suggest new features
- Submit pull requests
- Share your customizations

## 📝 License

This configuration is provided as-is for personal use. Feel free to modify and share.

## 🌟 Acknowledgments

- [GlazeWM](https://github.com/glzr-io/glazewm) - The tiling window manager
- [YASB](https://github.com/denBot/yasb) - Yet Another Status Bar
- The i3wm and sway communities for inspiration

## 📚 Additional Resources

- **My Windows Terminal Setup**: [Link to repository](https://github.com/lazy-blake/windows-terminal-config)
- [GlazeWM Documentation](https://github.com/glzr-io/glazewm#readme)
- [YASB Documentation](https://github.com/denBot/yasb#readme)

---

**Made with ⚡ by [lazy-blake](https://github.com/lazy-blake)**

_Transform your Windows experience into a productive powerhouse!_
