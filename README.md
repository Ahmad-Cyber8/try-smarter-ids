# 🔍 Try Smarter IDS

> Python/Scapy Intrusion Detection System with automatic attacker blocking

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)
![Scapy](https://img.shields.io/badge/Scapy-IDS-green?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Linux-orange?style=flat-square&logo=linux)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

---

## 📌 Overview

**Try Smarter IDS** is a custom-built Intrusion Detection System developed in Python using the Scapy library.

The system monitors live network traffic, detects Nmap SYN scan patterns in real time, and automatically blocks the attacker's IP address using `iptables` — without any manual intervention.

This project was built as part of an Information Systems Project module at UCLan (via NCC Education).

---

## 🎯 Objectives

- Monitor live network traffic on a Linux host
- Detect Nmap SYN port scans in real time
- Automatically block attacking IPs via iptables
- Log all detected threats with timestamps

---

## ⚙️ How It Works

1. Scapy captures all incoming TCP packets
2. The IDS counts SYN packets per source IP
3. If a single IP exceeds the threshold → flagged as attack
4. iptables rule is automatically added to DROP all traffic from that IP
5. Alert is printed to terminal with timestamp and attacker IP

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python 3 | Core programming language |
| Scapy | Packet sniffing and analysis |
| iptables | Automatic IP blocking |
| VMware Workstation | Lab environment |
| Kali Linux | Attacker machine |
| Ubuntu | Victim / IDS machine |
| Nmap | Attack simulation |

---

## 🖥️ Lab Environment

| Machine | Role | OS |
|---------|------|----|
| Attacker VM | Runs Nmap SYN scan | Kali Linux |
| Victim VM | Runs IDS, receives attack | Ubuntu |

Both machines connected via VMware Host-Only Network.

---

## 🚀 Installation & Usage

**Install dependency:**

```bash
pip install scapy
```

**Run the IDS:**

```bash
sudo python3 try_smarter.py
```

**Simulate attack (from attacker machine):**

```bash
nmap -sS <victim-ip>
```

---

## 📊 Results

- ✅ Successfully detected Nmap SYN scans in real time
- ✅ Attacker IP automatically blocked via iptables within seconds
- ✅ All alerts logged with source IP and timestamp
- ✅ Zero false positives in lab testing

---

## 📁 Project Structure

```
try-smarter-ids/
├── try_smarter.py        # Main IDS script
├── README.md             # Project documentation
├── report/
│   └── IDS_Report.pdf    # Full lab report
└── screenshots/
    ├── detection.png     # IDS detecting attack
    └── blocking.png      # iptables blocking attacker
```

---

## 📜 Academic Context

| Detail | Info |
|--------|------|
| Module | Information Systems Project |
| Institution | UCLan / NCC Education |
| Level | Undergraduate |
| Year | 2025–2026 |

---

## ⚠️ Disclaimer

This project was developed strictly for educational purposes in a controlled lab environment. Do not use against systems you do not own or have explicit permission to test.

---

## 👤 Author

**Ahmad** — Cybersecurity & Networking Student

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fadi-morad-775384381)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Ahmad-Cyber8)
