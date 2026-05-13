# 🚀 TERMUX MASTER HUB | ULTIMATE TOOLKIT
**The definitive collection of high-performance scripts and tools for Termux. Copy, Paste, and Dominate.**

<p align="center">
  <img src="https://img.shields.io/badge/Status-Ready_for_Deployment-FF3131?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/Environment-Termux_Android-00ff41?style=for-the-badge" alt="Env">
  <img src="https://img.shields.io/badge/Mode-Copy--Paste-blue?style=for-the-badge" alt="Mode">
</p>

---

## ⚡ 0. [CORE] THE GENESIS INITIALIZER
*Transform your terminal into a professional workstation in one shot.*

```bash
# [CORE] Total System Upgrade & Essential Tools
pkg update && pkg upgrade -y && pkg install \
  git curl wget zsh neovim nodejs python \
  openssh termux-api build-essential make \
  zip unzip jq -y && termux-setup-storage
```

---

## 🧠 1. [INTELLIGENCE] AI MASTER TOOLS
<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/8/8a/Google_Gemini_logo.svg" width="200" alt="Gemini Logo"></p>

### 🤖 Gemini AI CLI (Full Version)
```bash
# [AI] Install Runtimes & Wrapper
pkg install python -y && pip install -U google-generativeai

# Get API Key: https://aistudio.google.com/
read -p "ENTER YOUR GEMINI API KEY: " MY_API_KEY
echo "export GEMINI_API_KEY='$MY_API_KEY'" >> ~/.zshrc
source ~/.zshrc

# Create High-Performance Python Wrapper
cat <<EOF > ~/gemini_master.py
import google.generativeai as genai
import os, sys, textwrap
def main():
    api_key = os.getenv("GEMINI_API_KEY")
    if not api_key:
        print("❌ ERROR: GEMINI_API_KEY NOT FOUND"); return
    genai.configure(api_key=api_key)
    model = genai.GenerativeModel('gemini-1.5-flash')
    prompt = " ".join(sys.argv[1:])
    if not prompt:
        print("💡 Usage: ask 'your question'"); return
    try:
        response = model.generate_content(prompt)
        print("\n" + "="*50 + "\n🤖 GEMINI AI:\n" + "="*50 + "\n" + textwrap.fill(response.text, width=80) + "\n" + "="*50 + "\n")
    except Exception as e: print(f"🔥 ERROR: {e}")
if __name__ == "__main__": main()
EOF

# Bind to Global Shell
echo "alias ask='python3 ~/gemini_master.py'" >> ~/.zshrc
source ~/.zshrc
# TEST: ask "How to optimize Termux?"
```

---

## ☁️ 2. [CLOUD] DEPLOYMENT & ORCHESTRATION
<p align="center"><img src="https://www.vectorlogo.zone/logos/vercel/vercel-ar21.svg" width="200" alt="Vercel Logo"></p>

### ⚡ Vercel & Node.js Workflow
```bash
# [CLOUD] NPM to Vercel Setup
mkdir -p ~/master-apps && cd ~/master-apps
npm install -g vercel

# Scaffold basic API
mkdir api && cat <<EOF > package.json
{
  "name": "termux-edge-api",
  "version": "1.0.0",
  "scripts": { "deploy": "vercel --prod" }
}
EOF

cat <<EOF > api/index.js
const express = require('express');
const app = express();
app.get('/', (req, res) => res.json({ status: 'ONLINE', platform: 'Termux' }));
module.exports = app;
if (require.main === module) app.listen(3000);
EOF

npm install express cors helmet dotenv
vercel login
npm run deploy
```

---

## 💻 3. [IDE] ULTRA-MODERN EDITOR
<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Neovim_logo.svg" width="100" alt="Neovim Logo"></p>

### 🌌 NvChad Recon
```bash
# [IDE] Purge & Install NvChad
rm -rf ~/.config/nvim ~/.local/share/nvim ~/.cache/nvim
git clone https://github.com/NvChad/starter ~/.config/nvim
nvim --headless "+Lazy! sync" +qa
nvim
```

---

## 🗄️ 4. [DATA] RELATIONAL PERSISTENCE
<p align="center"><img src="https://mariadb.org/wp-content/uploads/2019/08/MariaDB_Logo_Primary_No_Background.png" width="200" alt="MariaDB Logo"></p>

### 🐬 MariaDB Hub
```bash
# [DATA] MariaDB Setup
pkg install mariadb -y
mysql_install_db
mysqld_safe --datadir=$PREFIX/var/lib/mysql &
sleep 5
mysql -u $(whoami) -e "CREATE DATABASE IF NOT EXISTS core_vault;"
mysql -u $(whoami) -e "SHOW DATABASES;"
```

---

## 🛠️ 5. [UTILITIES] MASTER VECTORS
<p align="center"><img src="https://www.vectorlogo.zone/logos/cloudflare/cloudflare-ar21.svg" width="200" alt="Cloudflare Logo"></p>

### 📡 Cloudflare Tunnel (Bypass Localhost)
```bash
# [NET] Expose local port 3000 to the web
pkg install cloudflared -y
cloudflared tunnel --url http://localhost:3000
```

### ⌨️ Cron Master (Persistence)
```bash
# [AUTO] Keep MariaDB alive every 15 mins
pkg install cronie -y
(crontab -l 2>/dev/null; echo "*/15 * * * * pgrep mysqld || mysqld_safe --datadir=\$PREFIX/var/lib/mysql &") | crontab -
```

---

## 🌟 6. [LAB] 10 NEXT-GEN MINI-PROJECTS
*Ready-to-deploy prototypes. Copy and explore!*

### 🛡️ 6.1 SentryWall (Network Guard)
```bash
# [SEC] Network Monitoring Setup
pkg install tcpdump tshark python -y
echo "alias monitor='tcpdump -i any'" >> ~/.zshrc
source ~/.zshrc
```

### 🤖 6.2 AutoBot-OS (Headless Bot)
```bash
# [BOT] Node.js Bot Environment
mkdir ~/bots && cd ~/bots
npm init -y && npm install telegraf discord.js
```

### 📦 6.3 PocketStore (JSON Gateway)
```bash
# [API] FastAPI Micro-Store
pip install fastapi uvicorn
cat <<EOF > ~/store.py
from fastapi import FastAPI
app = FastAPI()
@app.get("/")
def read_root(): return {"status": "PocketStore Online"}
EOF
# Run: uvicorn store:app --port 8000
```

### ⚡ 6.4 SpeedScribe (Voice-to-Code)
```bash
# [AI] Voice-to-Code Bridge
pkg install termux-api -y
# Requirement: Use 'termux-speech-to-text' and pipe to 'ask' alias
```

### 📊 6.5 TermuStats (Hardware Dash)
```bash
# [MON] System Dashboard
pkg install htop btop -y
alias sysstat='btop'
```

### 🔒 6.6 VaultKey (Secret Manager)
```bash
# [SEC] Encryption Toolkit
pkg install openssl -y
# Simple Encrypt: openssl enc -aes-256-cbc -salt -in secret.txt -out secret.enc
```

### 🌐 6.7 MirrorNode (Static Host)
```bash
# [WEB] Nginx Light Server
pkg install nginx -y
# Start server: nginx
```

### 📜 6.8 GitAuto-Sync (Backup)
```bash
# [DEV] Auto-Sync Configs
(crontab -l 2>/dev/null; echo "0 0 * * * cd ~/.config && git add . && git commit -m 'Daily Backup' && git push") | crontab -
```

### 📡 6.9 MeshChat (Local Peer P2P)
```bash
# [NET] Socket Programming Environment
pkg install python -y
# Use python3 -m http.server for quick file sharing
```

### 📅 6.10 LifeFlow (Productivity)
```bash
# [PROD] Task Management
pkg install taskwarrior -y
task add "Finish Termux Master Project"
```

---

## 🤝 Quick Resources
- **Wiki**: [Termux Official](https://wiki.termux.com/)
- **Docs**: [Google AI Studio](https://aistudio.google.com/)
- **IDE**: [NvChad](https://nvchad.com/)

<p align="center">
  <b>"TERMINAL IS NOT AN APP, IT IS AN OS."</b><br>
  Designed for ⚡ High-Speed Deployment by <i>Termux Master Architect</i>
</p>
