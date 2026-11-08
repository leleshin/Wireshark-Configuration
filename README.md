
<div align="center">

# 🔐 Cybersecurity Internship – B084
## Week 1: Virtual Lab Setup & Wireshark Network Traffic Analysis
**NETWORKWALKS | CYBERSECURITY & PENETRATION TESTING INTERNSHIP**

<img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
<img src="https://img.shields.io/badge/VirtualBox-v7.2-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Kali_Linux-v2026.2-E87500?style=flat-square&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
<img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square" />
<img src="https://img.shields.io/badge/Skill-Penetration_Testing-C00000?style=flat-square" />
<img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-Wireshark-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Platform-GitHub-404040?style=flat-square&logo=github&logoColor=white" />

</div>

---

## 📌 Project Overview

This repository documents my hands-on cybersecurity learning experience during Week 1 of the Networkwalks Cybersecurity and Penetration Testing Internship, Batch B084.

The project focuses on building a controlled virtual cybersecurity laboratory using Oracle VirtualBox, Kali Linux, Windows 11, and Wireshark.

As part of this practical training, I installed and configured Wireshark on Windows and explored its functionality within Kali Linux to understand network packet capture, traffic inspection, and security monitoring.

This project provides a foundation for developing practical skills in network administration, cybersecurity investigations, ethical hacking, and Security Operations Center (SOC) operations.

---

## 🎯 Project Objectives

1. Install and configure Oracle VirtualBox.
2. Import and configure Kali Linux.
3. Set up an isolated virtual network.
4. Install and configure Wireshark on Windows 11.
5. Explore Wireshark within Kali Linux.
6. Identify active network interfaces.
7. Capture and inspect network packets.
8. Analyze TCP, UDP, DNS, HTTP, and ICMP traffic.
9. Practice Wireshark display filters.
10. Develop network troubleshooting and security monitoring skills.

---

## 🛠️ Tools and Technologies

| Tool | Purpose |
|------|---------|
| Windows 11 | Host operating system |
| Oracle VirtualBox 7.2 | Virtual machine management |
| Kali Linux 2026.2 | Cybersecurity testing environment |
| Wireshark | Packet capture and protocol analysis |
| TCP/IP | Network communication analysis |
| Linux Terminal | System and network commands |
| GitHub | Project documentation and portfolio |

---

## 🖥️ Lab Setup and Configuration

### Step 1: Install Oracle VirtualBox

- Download Oracle VirtualBox from the official website.
- Install the application on Windows 11.
- Configure the virtual machine environment.
- Allocate appropriate RAM, CPU, and storage resources.

### Step 2: Import Kali Linux

- Download the Kali Linux VirtualBox image.
- Import the virtual machine into VirtualBox.
- Configure the virtual network adapter.
- Start Kali Linux and verify successful operation.

### Step 3: Configure Virtual Networking

Example lab network:

```text
Network:       10.0.0.0/24
IP Address:    10.0.0.2
Subnet Mask:   255.255.255.0
```

The virtual network is intended to support authorized communication between lab machines.

### Step 4: Install Wireshark on Windows

- Download Wireshark from the official website.
- Run the installation wizard.
- Install Npcap when prompted.
- Launch Wireshark.
- Identify available network interfaces.

### Step 5: Explore Wireshark in Kali Linux

Check whether Wireshark is installed:

```bash
wireshark --version
```

Launch Wireshark:

```bash
wireshark
```

If Wireshark is not installed:

```bash
sudo apt update
sudo apt install wireshark
```

Note: Installing Wireshark inside Kali Linux does not automatically install it on the Windows host.

---

## 📡 Wireshark Packet Analysis

Wireshark allows network administrators and cybersecurity analysts to inspect packets and investigate communication between devices.

### Common Display Filters

| Protocol | Wireshark Filter |
|----------|------------------|
| TCP | `tcp` |
| UDP | `udp` |
| DNS | `dns` |
| HTTP | `http` |
| ICMP | `icmp` |
| HTTPS/TLS | `tls` |
| Specific IP | `ip.addr == 10.0.0.2` |
| TCP Port 80 | `tcp.port == 80` |
| DNS Queries | `dns.flags.response == 0` |
| TCP SYN Packets | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |

These filters help identify specific protocols, network conversations, and potentially suspicious traffic patterns.

---

## 📚 Learning Outcomes

Through this project, I developed a better understanding of:

- Virtualization and virtual machine configuration.
- Kali Linux installation and administration.
- Network addressing and connectivity.
- Wireshark installation and configuration.
- Network packet inspection and protocol analysis.
- TCP/IP communication and troubleshooting.
- Network security monitoring fundamentals.
- Cybersecurity documentation using GitHub.

---

## 🛡️ Ethical Security Statement

All activities documented in this repository are performed for educational purposes and authorized cybersecurity testing.

Packet captures and security testing must be conducted only on systems and networks where appropriate permission has been granted.

---

## 👨‍💻 About the Author

**Lamidi Olatunji Micheal Eleshin**

Cybersecurity & Penetration Testing Intern | Aspiring Cybersecurity Analyst | IT Auditor | IT Support Engineer | GRC & Risk Management

**Specialization Areas:**

Cybersecurity | Network Security | IT Auditing | Governance, Risk & Compliance | Penetration Testing | SOC Operations

**Internship:** Networkwalks Cybersecurity & Penetration Testing

**Batch:** B084

**Project:** Week 1 – Virtual Lab Setup and Wireshark Network Traffic Analysis

---

<div align="center">

**"Cybersecurity begins with vigilance. Failure to prevent a threat today may become tomorrow's data disaster."**

*— Lamidi Olatunji Micheal Eleshin*

</div>
