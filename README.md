# <p align="center"><img src="https://raw.githubusercontent.com/termux/termux-app/master/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png" width="200" alt="Termux Logo"></p>

# <p align="center">📱 TERMUX [SCRIPT MASTER] v1.0</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Script_Master-FF3131?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/Architecture-Advanced_Automation-00ff41?style=for-the-badge" alt="Arch">
</p>

---

## ⚡ 0. [CORE] THE GENESIS INITIALIZER
*Turn a raw terminal into a professional workstation in one shot.*

```bash
# [SCRIPT MASTER] TOTAL SYSTEM UPGRADE
pkg update && pkg upgrade -y && pkg install \
  git curl wget zsh neovim nodejs python \
  openssh termux-api build-essential make \
  zip unzip jq -y && termux-setup-storage
```

---

## <img src="https://www.gstatic.com/lamda/images/gemini_sparkle_v002_d473530c25e7e4161697.svg" width="40" vertical-align="middle"> 1. [INTELLIGENCE] GEMINI AI MASTER CLI
*The complete, non-stop integration for Google's most powerful AI.*

### <p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/8/8a/Google_Gemini_logo.svg" width="300" alt="Gemini Logo"></p>

```bash
# [SCRIPT MASTER] INSTALL GEMINI AI CLI (FULL VERSION)
# 1. Install Runtimes
pkg install python -y
pip install -U google-generativeai

# 2. Configure Credentials (PERSISTENT)
# GET YOUR API KEY: https://aistudio.google.com/
read -p "ENTER YOUR GEMINI API KEY: " MY_API_KEY
echo "export GEMINI_API_KEY='$MY_API_KEY'" >> ~/.zshrc
source ~/.zshrc

# 3. Create High-Performance Python Wrapper
cat <<EOF > ~/gemini_master.py
import google.generativeai as genai
import os, sys, textwrap

def main():
    api_key = os.getenv("GEMINI_API_KEY")
    if not api_key:
        print("❌ ERROR: GEMINI_API_KEY NOT FOUND IN ENV")
        return
        
    genai.configure(api_key=api_key)
    model = genai.GenerativeModel('gemini-1.5-flash')
    
    prompt = " ".join(sys.argv[1:])
    if not prompt:
        print("💡 Usage: ask 'your question'")
        return

    try:
        response = model.generate_content(prompt)
        print("\n" + "="*50)
        print("🤖 GEMINI AI RESPONDED:")
        print("="*50)
        print(textwrap.fill(response.text, width=80))
        print("="*50 + "\n")
    except Exception as e:
        print(f"🔥 FATAL ERROR: {e}")

if __name__ == "__main__":
    main()
EOF

# 4. Bind to Global Shell
echo "alias ask='python3 ~/gemini_master.py'" >> ~/.zshrc
source ~/.zshrc

# TEST IT: ask "How do I optimize CPU on Termux?"
```

---

## <img src="https://assets.vercel.com/image/upload/v1588805858/repositories/vercel/logo.png" width="40" vertical-align="middle"> 2. [ORCHESTRATION] VERCEL & NODE.JS MASTER
*Deploy live production environments directly from your device.*

### <p align="center"><img src="https://www.vectorlogo.zone/logos/vercel/vercel-ar21.svg" width="250" alt="Vercel Logo"></p>

```bash
# [SCRIPT MASTER] NPM TO VERCEL WORKFLOW
# Setup Master Directory
mkdir -p ~/master-apps && cd ~/master-apps

# Automated Scaffolding
cat <<EOF > package.json
{
  "name": "termux-edge-api",
  "version": "1.0.0",
  "main": "api/index.js",
  "scripts": {
    "start": "node api/index.js",
    "deploy": "vercel --prod"
  }
}
EOF

# Install Core Stack
npm install express cors helmet dotenv

# Create Master API Entry
mkdir api
cat <<EOF > api/index.js
const express = require('express');
const app = express();
app.get('/', (req, res) => res.json({ status: 'MASTER_LEVEL', platform: 'Android_Termux' }));
module.exports = app;
if (require.main === module) app.listen(3000);
EOF

# Deploy to Vercel (Login Required)
npm install -g vercel
vercel login
npm run deploy
```

---

## <img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Neovim_logo.svg" width="40" vertical-align="middle"> 3. [IDE] NVCHAD ULTRA RECON
*Total Transformation of your text editor into a elite IDE.*

### <p align="center"><img src="https://nvchad.com/logo.webp" width="200" alt="NvChad Logo"></p>

```bash
# [SCRIPT MASTER] NVCHAD CLEAN INSTALL
# Purge Existing Configs
rm -rf ~/.config/nvim ~/.local/share/nvim ~/.cache/nvim

# Inject Optimized Starter
git clone https://github.com/NvChad/starter ~/.config/nvim

# Run First-Time Setup
nvim --headless "+Lazy! sync" +qa
nvim
```

---

## <img src="https://mariadb.org/wp-content/uploads/2019/08/MariaDB_Logo_Primary_No_Background.png" width="40" vertical-align="middle"> 4. [PERSISTENCE] RELATIONAL DATA HUB (MariaDB)
*Robust SQL backends for localized data engineering.*

```bash
# [SCRIPT MASTER] MARIADB INITIALIZER
pkg install mariadb -y

# Zero-Config Setup
mysql_install_db
mysqld_safe --datadir=$PREFIX/var/lib/mysql &

# Wait and Seed Root Database
sleep 5
mysql -u $(whoami) -e "CREATE DATABASE IF NOT EXISTS core_vault;"
mysql -u $(whoami) -e "SHOW DATABASES;"
```

---

## 🏗️ 5. OTHER MASTER VECTORS

### 📡 Network Tunneling (Bypass Localhost)
```bash
# Cloudfare Master Tunnel
pkg install cloudflared
cloudflared tunnel --url http://localhost:3000
```

### ⌨️ Automation (Crontab Master)
```bash
# Keep services alive indefinitely
pkg install cronie
(crontab -l 2>/dev/null; echo "*/15 * * * * pgrep mysqld || mysqld_safe --datadir=\$PREFIX/var/lib/mysql &") | crontab -
```

---

## 🤝 Community & Support
- [Termux Official Wiki](https://wiki.termux.com/)
- [Master Scripts Repo](https://github.com/termux/termux-app)

---

<p align="center">
  <b>"TERMINAL IS NOT AN APP, IT IS AN OS."</b><br>
  Developed for High-Speed Deployment by <i>Termux_Master_Architect</i>
</p>
