
<div align="center">

# 🔐 Cybersecurity Internship – B084
## Week 1: Wireshark Installation, Configuration & Network Traffic Analysis

**NETWORKWALKS | CYBERSECURITY & PENETRATION TESTING INTERNSHIP**

**Hands-On Network Packet Capture, Protocol Analysis, Traffic Monitoring & Cybersecurity Investigation**

<img src="https://img.shields.io/badge/Tool-Wireshark-0070C0?style=flat-square&logo=wireshark&logoColor=white" />
<img src="https://img.shields.io/badge/Skill-Packet_Analysis-C00000?style=flat-square" />
<img src="https://img.shields.io/badge/Skill-Network_Security-404040?style=flat-square&labelColor=C00000" />
<img src="https://img.shields.io/badge/Skill-Traffic_Monitoring-238F89?style=flat-square" />
<img src="https://img.shields.io/badge/Protocols-TCP%2FIP-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Protocols-DNS%20%7C%20HTTP%20%7C%20ICMP-E87500?style=flat-square" />
<img src="https://img.shields.io/badge/Platform-Windows_11-0078D4?style=flat-square" />
<img src="https://img.shields.io/badge/Environment-Kali_Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/Skill-SOC_Analysis-404040?style=flat-square&labelColor=C00000" />
<img src="https://img.shields.io/badge/Internship-B084-238F89?style=flat-square" />

</div>

---

## 📌 Project Overview

This repository documents my hands-on experience with **Wireshark installation, configuration, and network traffic analysis** during Week 1 of the Networkwalks Cybersecurity and Penetration Testing Internship (Batch B084).

The primary focus of this project is to develop practical cybersecurity skills using Wireshark, an open-source network protocol analyzer designed to capture, inspect, monitor, and troubleshoot network communications.

As part of my training, I successfully installed Wireshark on Windows 11 and explored how to launch and operate Wireshark within Kali Linux running through Oracle VirtualBox.

This project focuses on understanding how network packets travel between devices, identifying network interfaces, examining communication protocols, and applying Wireshark display filters to investigate network activity.

The practical learning activities cover:

- Wireshark installation and initial configuration.
- Identifying network interfaces for packet capture.
- Capturing and examining network traffic.
- Understanding TCP, UDP, DNS, HTTP, and ICMP protocols.
- Applying Wireshark display filters to isolate relevant packets.
- Recognizing network communication patterns and potential security concerns.
- Developing foundational packet analysis and troubleshooting skills.
- Understanding the importance of Wireshark in Security Operations Center (SOC) investigations.

The project demonstrates my commitment to building hands-on experience in **network security monitoring, traffic investigation, packet analysis, and cybersecurity operations**.

---

## 🎯 Project Objectives

1. Install and configure Wireshark on Windows 11.
2. Understand Wireshark's graphical user interface and core functions.
3. Identify available network interfaces and select appropriate capture sources.
4. Capture live network packets within an authorized environment.
5. Examine packet details, including source and destination IP addresses, protocols, and ports.
6. Analyze TCP, UDP, DNS, HTTP, and ICMP network traffic.
7. Practice Wireshark display filters for efficient packet investigation.
8. Explore Wireshark functionality in Kali Linux.
9. Develop practical network troubleshooting and traffic monitoring skills.
10. Build foundational knowledge for cybersecurity investigations, SOC analysis, and ethical penetration testing.

---

## 🛠️ Primary Tool

**Wireshark – Network Protocol Analyzer**

Wireshark is the central application used throughout this project. Windows 11 serves as the primary installation platform, while Kali Linux and Oracle VirtualBox provide an additional environment for exploring network analysis.

---

## 🛡️ Ethical Security Statement

All packet capture and network analysis activities are intended strictly for educational purposes and authorized cybersecurity training. Network traffic should only be captured on systems and networks where permission has been granted.

---

**Author:** Lamidi Olatunji Micheal Eleshin

**Program:** Networkwalks Cybersecurity & Penetration Testing Internship

**Batch:** B084 | Week 1

**Project Focus:** Wireshark Installation, Packet Capture, Network Traffic Analysis & Security Monitoring


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
