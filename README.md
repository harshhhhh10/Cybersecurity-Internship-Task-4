# 🔥 Task 4 – Windows Firewall Configuration & Testing

![Internship](https://img.shields.io/badge/Elevate%20Labs-Cybersecurity%20Internship-blue?style=for-the-badge)
![Tool](https://img.shields.io/badge/Tool-Windows%20Firewall-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Protocol](https://img.shields.io/badge/Blocked-Telnet%20Port%2023-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 📌 Objective

Configure and test basic firewall rules on Windows to block and allow network traffic — specifically blocking the insecure Telnet protocol (Port 23) and verifying the rule works.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Windows Defender Firewall** | Firewall rule configuration |
| **Windows Advanced Security** | Inbound rule creation |
| **CMD / Terminal** | Testing Telnet connection block |

---

## ⚙️ Firewall Rule Created

| Parameter | Value |
|-----------|-------|
| **Rule Type** | Inbound Rule |
| **Protocol** | TCP |
| **Port** | 23 (Telnet) |
| **Action** | Block the connection |
| **Profiles** | Domain, Private, Public |
| **Status** | ✅ Enabled |

---

## 🧪 Test & Result

**Command run:**
```cmd
telnet localhost 23
```

**Result:**
```
Connecting to localhost...Could not open connection to the host, on port 23: Connect failed
```

✅ **Rule is working — Port 23 successfully blocked.**

---

## ❓ Why Block Port 23 (Telnet)?

Telnet transmits **everything in plaintext** — including usernames and passwords. Anyone on the same network can intercept credentials with a simple packet sniffer.

| Protocol | Port | Encryption | Verdict |
|----------|------|-----------|---------|
| Telnet | 23 | ❌ None | 🚫 Insecure — Block it |
| SSH | 22 | ✅ Encrypted | ✅ Use this instead |

---

## 📚 Key Concepts

### Stateful vs Stateless Firewall
| Type | Memory | Intelligence | Example |
|------|--------|-------------|---------|
| **Stateful** | Remembers connections | High | Windows Defender Firewall |
| **Stateless** | Each packet independent | Low | Basic ACLs |

### Inbound vs Outbound Rules
- **Inbound** — Controls traffic *entering* your machine (e.g., block port 23)
- **Outbound** — Controls traffic *leaving* your machine (e.g., prevent malware callbacks)

---

## 📸 Screenshots

All screenshots are in the [`/screenshots`](./screenshots) folder:

| File | Description |
|------|-------------|
| `01_allowed_apps.png` | Allowed apps configuration |
| `02_advanced_security.png` | Advanced Security interface |
| `03_inbound_rules.png` | Inbound Rules list |
| `04_new_rule_type.png` | New Rule wizard — type selection |
| `05_port_config.png` | Protocol and port configuration |
| `06_action_block.png` | Action selection — Block |
| `07_profile_selection.png` | Profile selection |
| `08_rule_naming.png` | Rule name and description |
| `09_rule_complete.png` | Completed rule in list |
| `10_telnet_blocked.png` | Test result — connection failed |

---

## 🧠 Key Learnings

- How to create inbound firewall rules on Windows
- Why Telnet is insecure and should be replaced with SSH
- Difference between stateful and stateless firewalls
- How inbound and outbound rules differ
- Importance of testing rules after creation
- How NAT protects internal network structure

---

## 📁 Repository Structure

```
Cybersecurity-Internship-Task-4/
├── README.md
└── screenshots/
    ├── 01_allowed_apps.png
    ├── 02_advanced_security.png
    ├── 03_inbound_rules.png
    ├── 04_new_rule_type.png
    ├── 05_port_config.png
    ├── 06_action_block.png
    ├── 07_profile_selection.png
    ├── 08_rule_naming.png
    ├── 09_rule_complete.png
    └── 10_telnet_blocked.png
```
---

> 🔒 *This configuration was performed on a personal Windows machine for educational purposes only as part of the Elevate Labs Cybersecurity Internship.*
