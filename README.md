# 📱 Termux [SCRIPT MASTER]: The Professional Android Rig

![Termux Logo](https://raw.githubusercontent.com/termux/termux-app/master/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png)

> **WARNING:** This is a high-performance configuration. These scripts are "Copy-Paste" ready for production-level terminal environments.

[![Status](https://img.shields.io/badge/Status-Script_Master-red.svg)](#)
[![Stack](https://img.shields.io/badge/Stack-AI_/_Node_/_Cloud-00ff41.svg)](#)

---

## 🔥 0. The "GOD MODE" Initializer
Run this once to turn a fresh Termux into a Pro environment automatically.

```bash
pkg update && pkg upgrade -y && pkg install git curl wget zsh neovim nodejs python openssh termux-api -y && termux-setup-storage
```

---

## 🚀 1. NPM & Vercel: Full-Stack Master Flow
*One script to create, build, and deploy an API server.*

```bash
# [COPY-PASTE] FULL DEPLOYMENT PROJECT
mkdir -p ~/projects/web-api && cd ~/projects/web-api

# Initialize Project
npm init -y && npm install express dotenv cors

# Create Server Code
cat <<EOF > index.js
const express = require('express');
const cors = require('cors');
require('dotenv').config();

const app = express();
app.use(cors());
app.use(express.json());

app.get('/', (req, res) => res.json({ status: 'live', host: 'Termux-Android' }));

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => console.log(\`✅ Master API running on port \${PORT}\`));
EOF

# Local Dev Start
node index.js &

# Cloud Deploy (Vercel)
npm install -g vercel
vercel login
vercel --prod
```
![Vercel](https://img.shields.io/badge/Deploy-Vercel-black?style=for-the-badge&logo=vercel)

---

## 🤖 2. AI Master Implementation (Gemini AI)
*Automated AI Agent with logging and shell integration.*

```bash
# [COPY-PASTE] GEMINI AI INTEGRATION
pkg update && pkg upgrade -y && pkg install python -y
pip install -U google-generativeai

# Setup Environment Variable (Persistent)
# Replace 'YOUR_KEY' with real key from aistudio.google.com
echo "export GEMINI_API_KEY='YOUR_KEY'" >> ~/.zshrc && source ~/.zshrc

# Create AI Function Script
cat <<EOF > ~/ai_agent.py
import google.generativeai as genai
import os, sys, datetime

genai.configure(api_key=os.environ["GEMINI_API_KEY"])
model = genai.GenerativeModel('gemini-1.5-flash')

def execute_ai(prompt):
    try:
        response = model.generate_content(prompt)
        timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        
        # Auto-Logging system
        with open("ai_master.log", "a") as log:
            log.write(f"[{timestamp}] Q: {prompt}\n[{timestamp}] A: {response.text}\n\n")
            
        print(f"\n🤖 AI RESPONDED:\n{response.text}")
    except Exception as e:
        print(f"❌ ERROR: {str(e)}")

if __name__ == "__main__":
    if len(sys.argv) > 1:
        execute_ai(" ".join(sys.argv[1:]))
    else:
        print("Usage: python ai_agent.py 'your question'")
EOF

# Create Easy Alias
echo "alias ask='python ~/ai_agent.py'" >> ~/.zshrc && source ~/.zshrc

# Usage: ask "How to secure Termux?"
```
![AI](https://img.shields.io/badge/Powered_By-Gemini_AI-4285F4?style=for-the-badge&logo=google-gemini)

---

## ⚡ 3. IDE Master: NvChad Full Config
*Turn Neovim into a VS Code replacement in 2 seconds.*

```bash
# [COPY-PASTE] NVCHAD INSTALLER
# Remove old config
rm -rf ~/.config/nvim && rm -rf ~/.local/share/nvim

# Install dependencies
pkg install build-essential make -y

# Clone & Launch
git clone https://github.com/NvChad/starter ~/.config/nvim && nvim
```
![NvChad](https://img.shields.io/badge/NvChad-IDE-blueviolet?style=for-the-badge&logo=neovim)

---

## 📊 4. Database Master: MariaDB Setup
*Full SQL Server initialization script.*

```bash
# [COPY-PASTE] MARIADB INITIALIZER
pkg install mariadb -y

# Start MySQL Server in background
nohup mysqld_safe --datadir=$PREFIX/var/lib/mysql &

# Wait for startup and configure
sleep 5
mysql_install_db
mysql -u $(whoami) -e "CREATE DATABASE master_db;"
mysql -u $(whoami) -e "SHOW DATABASES;"
```

---

## 🛠️ 5. Capabilities Quick-Reference

| System | Script Utility | Role |
| :--- | :--- | :--- |
| **Python** | `pkg install python` | AI / Automation |
| **Node.js** | `pkg install nodejs` | Web / React / Vite |
| **Docker** | *(Android Root Only)* | Virtualization |
| **Ngrok** | `pkg install wget` | Public Tunnels |
| **SSH** | `pkg install openssh` | Remote Access |

---

## ⌨️ Master Keyboard Shortcuts
- **Vol Up + Q**: Open Extra Keys.
- **Vol Down + C**: Kill Process (SIGINT).
- **Vol Up + T**: New Session.
- **Vol Up + K**: Kill Current Session.

---

## 📡 Hardware Integration (Termux:API)
```bash
# READ SENSORS
termux-battery-status
termux-location
termux-wifi-scaninfo

# PUSH NOTIFICATION
termux-notification --title "Master Script" --content "Process Completed"
```

---

*This Project is Optimized for **Cloudflare Pages** Deployment.*
*"Efficiency is not a choice, it is a script."*
