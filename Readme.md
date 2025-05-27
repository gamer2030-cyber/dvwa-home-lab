# 🔐 DVWA Cybersecurity Home Lab

This project demonstrates a practical cybersecurity home lab setup using Damn Vulnerable Web Application (DVWA) hosted on an Ubuntu virtual machine, with attack simulations launched from a Kali Linux VM. It showcases common web application vulnerabilities and penetration testing techniques.

---

## 📦 Lab Architecture

- **Host System:** macOS (running UTM)
- **Target VM:** Ubuntu 24.04 with DVWA installed
- **Attacker VM:** Kali Linux (tools: Hydra, Nmap, Burp Suite, etc.)
- **Network:** Host-Only or Bridged Adapter (private lab network)

---

## ⚙️ Technologies & Tools

| Category        | Tools Used                      |
|----------------|----------------------------------|
| Web Vulnerabilities | DVWA, PHP, MySQL             |
| Penetration Testing | Kali Linux, Hydra, Nmap      |
| Scripting        | Bash                            |
| Brute Force      | Hydra, RockYou wordlist         |

---

## 🧪 Attacks Performed

### 1. **SQL Injection**
- Input used: `' OR '1'='1`
- Result: Dumped entire user table from the DVWA database

### 2. **Brute-force Login (Hydra)**
- Tool: `hydra`
- Target: DVWA web login form (`/login.php`)
- Wordlist: `/usr/share/wordlists/rockyou.txt`
- Result: Recovered valid passwords for `admin`

### 3. *(Optional – You can include these if done)*
- Command Injection
- XSS (Reflected/Stored)
- File Upload + Reverse Shell

---

## 🛠 How to Reproduce

### 🔧 On Ubuntu VM:
```bash
sudo apt update && sudo apt install apache2 php mariadb-server git unzip -y
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git
cd DVWA/config
sudo cp config.inc.php.dist config.inc.php
# Edit config.inc.php and set db_user = 'dvwauser', db_password = 'dvwapass'
