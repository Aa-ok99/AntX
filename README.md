# 📱 Termux [SCRIPT MASTER]: High-Performance Android Rig

![Termux Logo](https://raw.githubusercontent.com/termux/termux-app/master/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png)

> **TECHNICAL OVERVIEW:** This repository provides protocol-level configurations and automation scripts for transforming Android environments into production-grade workstations. Optimized for deployment on **Cloudflare Pages**.

[![Engine](https://img.shields.io/badge/Engine-Script_Master-FF3131.svg)](#)
[![Stack](https://img.shields.io/badge/Architecture-Full_Stack_/_Artificial_Intelligence-00ff41.svg)](#)

---

## ⚡ 1. [CORE] SYSTEM ARCHITECTURE INITIALIZATION
*Bootstrapping the environment with high-performance binaries.*

```bash
# [SCRIPT MASTER] AUTO-INIT
pkg update && pkg upgrade -y && pkg install \
  git curl wget zsh neovim nodejs python \
  openssh termux-api build-essential make -y \
  && termux-setup-storage
```

---

## 🤖 2. [INTELLIGENCE] INTEGRATION LAYER
*Three operational paths for AI orchestration.*

### Path A: Standard SDK Integration (Gemini)
*Uses high-level libraries for rapid development.*
```bash
pip install -U google-generativeai
# Automated Wrapper Creation
cat <<EOF > ~/ai_native.py
import google.generativeai as genai, os, sys
genai.configure(api_key=os.environ["GEMINI_API_KEY"])
model = genai.GenerativeModel('gemini-1.5-flash')
print(model.generate_content(" ".join(sys.argv[1:])).text)
EOF
alias ask='python ~/ai_native.py'
```

### Path B: Protocol-Level Bypass (Direct REST)
*Interacts directly with the API via cURL. No dependencies, faster execution, avoids library-level tracking.*
```bash
# [SCRIPT MASTER] BYPASS METHOD
cat <<EOF > ~/ai_bypass.sh
curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=\$GEMINI_API_KEY" \\
    -H 'Content-Type: application/json' \\
    -X POST \\
    -d '{
      "contents": [{
        "parts":[{"text": "'"\$*"'"}]
      }]
    }' | jq -r '.candidates[0].content.parts[0].text'
EOF
chmod +x ~/ai_bypass.sh
alias bash-ai='~/ai_bypass.sh'
```

### Path C: Edge Intelligence (Local LLM)
*Zero-Cloud dependency. True privacy and off-grid execution.*
```bash
# [MASTER] OLLAMA DEPLOYMENT
pkg install ollama
# Start server in background
ollama serve &
# Execute model (Requires 8GB+ RAM recommended)
ollama run llama3 "Explain quantum computing shortly"
```

---

## 🚀 3. [ORCHESTRATION] DEV-OPS & DEPLOYMENT
*Master script for automated Project Lifecycle.*

```bash
# [SCRIPT MASTER] FULL STACK AUTOMATION
mkdir -p ~/master-node && cd ~/master-node

# Scaffold
cat <<EOF > package.json
{
  "name": "termux-master-api",
  "version": "1.0.0",
  "scripts": { "start": "node index.js", "dev": "node --watch index.js" }
}
EOF

# Install Core Stack
npm install express dotenv cors helmet

# Build Integrated Server
cat <<EOF > index.js
const express = require('express');
const helmet = require('helmet');
const app = express();
app.use(helmet());
app.use(express.json());
app.get('/api/status', (req, res) => res.json({ 
    epoch: Date.now(), 
    arch: process.arch, 
    platform: 'Termux_Master' 
}));
app.listen(3000, () => console.log('🚀 MASTER_ACTIVE_ON_3000'));
EOF

# Cloud-Push (Vercel)
npm install -g vercel
vercel deploy --prod --yes
```

---

## 📊 4. [PERSISTENCE] RELATIONAL & NO-SQL DATA
*Database services for stateful application management.*

```bash
# [MASTER] MARIADB INITIALIZER
pkg install mariadb -y
mysql_install_db
mysqld_safe --datadir=\$PREFIX/var/lib/mysql &
# Quick-Table Setup
mysql -u \$(whoami) -e "CREATE DATABASE logs; USE logs; CREATE TABLE events (id INT AUTO_INCREMENT PRIMARY KEY, msg TEXT, ts TIMESTAMP DEFAULT CURRENT_TIMESTAMP);"
```

---

## 🌐 5. [INTEROPERABILITY] NETWORKING & TUNNELS
*Exposing services across network boundaries.*

| Method | Role | Script Hook |
| :--- | :--- | :--- |
| **SSH-Tunnel** | Remote Shell | `ssh -R 80:localhost:3000 nokey@localhost.run` |
| **Cloudflare** | Edge Proxy | `cloudflared tunnel --url http://localhost:3000` |
| **Ngrok** | Public URL | `./ngrok http 3000` |

---

## 📡 6. [HARDWARE] PERIPHERAL BRIDGING
*Direct hardware interaction via CLI.*

```bash
# SYSTEM DATA EXTRACTION
termux-telephony-deviceinfo
termux-sensor -list

# HAPTIC & AUDIO
termux-vibrate -d 500
termux-tts-speak "Master script execution successful"
```

---

## ⌨️ KEYBOARD COMMAND BINDINGS
*The Script Master's efficiency keys.*
- **`CTRL + A`** -> **`CTRL + E`** : Head/Tail navigation.
- **`Vol Up + L`** : Clear Buffer.
- **`Vol Up + V`** : Toggle Controls.

---

*"Code is the law. Scripts are the execution."*
*Deployed via Cloudflare Pages // [Your Repo]*
