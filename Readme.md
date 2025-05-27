# 🔐 DVWA Cybersecurity Home Lab

This project demonstrates a practical cybersecurity home lab setup using Damn Vulnerable Web Application (DVWA) hosted on an Ubuntu virtual machine, with attack simulations launched from a Kali Linux VM. It showcases common web application vulnerabilities and penetration testing techniques.

---

## 📦 Lab Architecture

- **Host System:** macOS (running UTM)
- **Target VM:** Ubuntu with DVWA installed
- **Attacker VM:** Kali Linux (tools: Hydra, Nmap, Burp Suite, etc.)
- **Network:** Host-Only or Bridged Adapter (private lab network)

---

## ⚙️ Technologies & Tools

| Category             | Tools Used                       |
|----------------------|----------------------------------|
| Web Vulnerabilities  | DVWA, PHP, MySQL                 |
| Penetration Testing  | Kali Linux, Hydra, Nmap          |
| Wordlists            | rockyou.txt                      |

---

## 🧪 Attacks Performed

### 1. **SQL Injection**
- Input used: `' OR '1'='1`
- Result: Dumped user table from DVWA

### 2. **Brute-force Login (Hydra)**
- Target: DVWA login form
- Result: Cracked password for `admin` using Hydra and rockyou.txt

*(Optional: Add command injection, XSS, reverse shell if attempted)*

---

## 🛠 How to Reproduce

### On Ubuntu VM:
```bash
sudo apt update && sudo apt install apache2 php php-mysqli mariadb-server git unzip -y
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git
cd DVWA/config
sudo cp config.inc.php.dist config.inc.php
