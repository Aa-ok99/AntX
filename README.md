# AntX

# 📱 Termux: The Ultimate Terminal Emulator for Android

![Termux Logo](https://raw.githubusercontent.com/termux/termux-app/master/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png)

> **Termux** is an Android terminal emulator and Linux environment app that works directly with no rooting or setup required. A minimal base system is installed automatically - additional packages are available using the APT package manager.

[![Status](https://img.shields.io/badge/Status-Pro_Ready-brightgreen.svg)](#)
[![Version](https://img.shields.io/badge/Version-0.118-blue.svg)](#)
[![Shell](https://img.shields.io/badge/Shell-Bash/Zsh/Fish-orange.svg)](#)
[![Platform](https://img.shields.io/badge/Platform-Android-34D058.svg)](#)

---

## 🚀 Basic Setup (Level: Beginner)

Start your journey by preparing the environment. Run these commands immediately after installation.

### 1. Update and Upgrade
Keep your repositories fresh.
```bash
pkg update && pkg upgrade -y
```

### 2. Setup Storage
Grant Termux permission to access your phone's internal storage.
```bash
termux-setup-storage
```
*This creates a `~/storage` folder linking to your internal storage.*

### 3. Essential Tools
Install the Swiss Army Knives of the terminal.
```bash
pkg install curl wget git vim nano -y
```

---

## 🛠️ Pro Setup (Level: Professional)

Transform your Termux into a powerful development workstation.

### 1. Stunning Shell (Zsh + Oh My Zsh)
```bash
pkg install zsh -y
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 2. High-Performance Shell Theme: Powerlevel10k
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
# Set ZSH_THEME="powerlevel10k/powerlevel10k" in ~/.zshrc
```

### 3. Package Management
Use `pkg` for Termux-specific packages and `apt` for standard Debian-based packages.
- Search: `pkg search <package>`
- Install: `pkg install <package>`

---

## 🏗️ Capabilities & Environments

Termux turns your phone into a portable server and development lab.

### 💻 Development Runtimes
| Language | Install Command | Logo |
| :--- | :--- | :--- |
| **Python** | `pkg install python` | ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) |
| **Node.js** | `pkg install nodejs` | ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) |
| **PHP** | `pkg install php` | ![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white) |
| **C++** | `pkg install clang` | ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) |
| **Ruby** | `pkg install ruby` | ![Ruby](https://img.shields.io/badge/ruby-%23CC342D.svg?style=for-the-badge&logo=ruby&logoColor=white) |
| **Golang** | `pkg install golang` | ![Go](https://img.shields.io/badge/go-%2300ADD8.svg?style=for-the-badge&logo=go&logoColor=white) |

### 🌐 Web Servers
Host websites directly from your pocket.
- **Apache**: `pkg install apache2`
- **Nginx**: `pkg install nginx`
- **MariaDB**: `pkg install mariadb`

### 🛡️ Networking & Security
- **OpenSSH**: `pkg install openssh` (Connect via `ssh` or start server with `sshd`)
- **Nmap**: `pkg install nmap` (Network scanning)
- **Metasploit**: `pkg install metasploit` (Security auditing)

---

## 📡 Termux:API (The Magic Sauce)
Access your Android hardware via the command line!
1. Install **Termux:API** app from F-Droid.
2. Install package: `pkg install termux-api`

**Commands:**
- `termux-battery-status`: Check battery level.
- `termux-camera-photo snapshot.jpg`: Take a photo.
- `termux-location`: Get GPS coordinates.
- `termux-notification --content "Hello!"`: Push an Android notification.
- `termux-vibrate -d 1000`: Vibrate the phone.

---

## 🎨 GUI in Termux (X11)
Yes, you can run a desktop environment!
```bash
pkg install x11-repo
pkg install xfce4 vncserver -y
# Start with vncserver and connect using a VNC Viewer app.
```

---

## ⌨️ Critical Keyboard Shortcuts
Termux uses Volume buttons to simulate special keys:
- **Volume Up + Q**: Toggle extra keys row.
- **Volume Down + C**: `Ctrl + C` (Interrupt).
- **Volume Up + L**: `Ctrl + L` (Clear).
- **Volume Up + W,A,S,D**: Arrow keys.

---

## 🤝 Community & Resources
- [Termux Wiki](https://wiki.termux.com/)
- [Termux Reddit](https://www.reddit.com/r/termux/)
- [GitHub Repository](https://github.com/termux/termux-app)

---

Developed by **[Your Name/Repo]** for the Ultimate Android Power User experience.
*"Your phone is a terminal. Use it."*
