<div align="center">

# 🔐 Cybersecurity Internship – B084
## Week 1: Wireshark Installation, Configuration & Network Traffic Analysis

**NETWORKWALKS | CYBERSECURITY & PENETRATION TESTING INTERNSHIP**

**Hands-On Packet Capture • Protocol Analysis • Traffic Monitoring • Network Investigation**

<img src="https://img.shields.io/badge/Tool-Wireshark_4.6.9-0070C0?style=flat-square" alt="Wireshark 4.6.9" />
<img src="https://img.shields.io/badge/Skill-Packet_Analysis-C00000?style=flat-square" alt="Packet analysis" />
<img src="https://img.shields.io/badge/Skill-Network_Security-404040?style=flat-square" alt="Network security" />
<img src="https://img.shields.io/badge/Skill-Traffic_Monitoring-238F89?style=flat-square" alt="Traffic monitoring" />
<img src="https://img.shields.io/badge/Protocols-mDNS%20%7C%20SSDP%20%7C%20TCP%20%7C%20ICMPv6-E87500?style=flat-square" alt="Observed protocols" />
<img src="https://img.shields.io/badge/Platform-Windows_11-0078D4?style=flat-square" alt="Windows 11" />
<img src="https://img.shields.io/badge/Internship-B084-238F89?style=flat-square" alt="Batch B084" />

</div>

---

## 📌 Project Overview

This repository documents my hands-on experience with **Wireshark installation, configuration, and network traffic analysis** during Week 1 of the Networkwalks Cybersecurity and Penetration Testing Internship (Batch B084).

I installed and launched Wireshark on Windows 11, identified available network interfaces, selected the Wi-Fi interface for a live packet capture, and inspected captured network traffic. I also explored Wireshark in Kali Linux running through Oracle VirtualBox as an additional learning environment.

The screenshots below document the Wireshark interface, an active capture, and inspection of packet headers. They show **mDNS, SSDP, TCP, and ICMPv6** traffic; the appearance of these protocols alone does not indicate malicious activity.

## 🎯 Project Objectives

1. Install and configure Wireshark on Windows 11.
2. Identify available network interfaces and select a capture source.
3. Capture live traffic on an authorized network.
4. Examine packet source and destination addresses, protocol names, and lengths.
5. Inspect Ethernet, IPv4, UDP, and application-protocol details.
6. Learn to apply display filters for TCP, UDP, DNS, HTTP, ICMP, mDNS, and SSDP.
7. Build foundational skills in network troubleshooting and SOC traffic analysis.

## 🛠️ Tools and Environment

| Tool / environment | Purpose |
|---|---|
| **Wireshark 4.6.9** | Packet capture and protocol inspection (version shown in screenshot) |
| **Windows 11** | Host system used for the documented capture |
| **Wi-Fi network interface** | Selected capture interface |
| **Kali Linux / Oracle VirtualBox** | Additional environment explored for Wireshark practice |
| **GitHub** | Lab documentation and evidence |

---

## 🖥️ Step 1: Launch Wireshark and Identify Interfaces

After installing Wireshark on Windows, I launched the application and reviewed the available capture interfaces, including Wi-Fi, Ethernet, loopback, and virtual adapters. The welcome screen confirmed that Wireshark was running and ready for a capture.

![Wireshark welcome screen showing version 4.6.9 and available capture interfaces](images/wireshark-interface.png)

*Figure 1: Wireshark welcome screen and available capture interfaces on Windows.*

## 📡 Step 2: Start a Live Capture on Wi-Fi

I selected the **Wi-Fi** interface and started a live packet capture. Wireshark populated its packet list with the packet number, time, source, destination, protocol, length, and summary information.

![Wireshark capturing Wi-Fi traffic, including mDNS packets and an SSDP packet detail view](images/live-packet-capture.png)

*Figure 2: Live Wi-Fi capture. The packet list shows mDNS discovery traffic; the packet-details pane displays an SSDP packet.*

In this capture, **mDNS** traffic used the IPv4 multicast destination `224.0.0.251`. The displayed discovery messages included references to a Roku TV and another local device. The selected packet's details showed **SSDP over UDP**, with destination `239.255.255.250` and port `1900`.

## 🔎 Step 3: Inspect Packet Headers and Protocol Fields

I examined packet details to understand how Wireshark breaks down a frame into protocol layers. The screenshot shows the packet list alongside expanded Ethernet and IPv4 fields, including header version, header length, total length, fragmentation flags, and time to live (TTL).

![Wireshark packet list with Ethernet and IPv4 header fields expanded](images/packet-details-analysis.png)

*Figure 3: Packet inspection with expanded IPv4 header fields; the capture also includes SSDP, mDNS, TCP, and ICMPv6 traffic.*

The capture reached **626 packets with 0 reported dropped packets** at the moment shown. This describes the capture status in the screenshot, not an overall network health or security assessment.

## 🧪 Step 4: Practice Wireshark Display Filters

The following are useful filters for continued analysis. They are **practice examples**, not evidence that every filter was applied in the screenshots.

| Investigation | Display filter |
|---|---|
| TCP traffic | `tcp` |
| UDP traffic | `udp` |
| DNS traffic | `dns` |
| HTTP traffic | `http` |
| ICMP traffic | `icmp` |
| ICMPv6 traffic | `icmpv6` |
| Multicast DNS | `mdns` |
| SSDP discovery | `ssdp` |
| Traffic involving a specific host | `ip.addr == 10.0.0.31` |
| SSDP UDP port | `udp.port == 1900` |
| Initial TCP SYN packets | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |

To apply a filter, enter it in the **display filter bar** at the top of Wireshark and press **Enter**. Display filters narrow what is shown; they do not change the packets already captured.

## 📊 Observations and Interpretation

| Observation from screenshots | Interpretation |
|---|---|
| mDNS packets to `224.0.0.251` | Local multicast service discovery |
| SSDP packets to `239.255.255.250` | Device/service discovery, commonly associated with UPnP |
| TCP packets with ACK flags | Acknowledgments within TCP communication |
| ICMPv6 Router Advertisement | IPv6 router/network configuration signaling |
| Expanded IPv4 header fields | Demonstrates how to inspect packet structure and metadata |

**Security note:** These observations are consistent with ordinary network activity. The screenshots alone do not establish an intrusion, compromise, or vulnerability.

## 📚 Learning Outcomes

Through this exercise, I practiced identifying capture interfaces, starting a Wi-Fi capture, reading packet lists, examining layered packet headers, and interpreting common local-network discovery traffic. I also gained a clearer understanding of how Wireshark supports network troubleshooting and security investigations.

## 🛡️ Ethical Security Statement

All activities in this repository are intended for education and authorized security training. Capture or inspect traffic only on systems and networks where you have permission. Review packet captures and screenshots before sharing them publicly because they may contain device names, IP addresses, or other network metadata.

---

## 👨‍💻 About the Author

**Lamidi Olatunji Micheal Eleshin**  
Cybersecurity & Penetration Testing Intern | Aspiring Cybersecurity Analyst | IT Auditing | IT Support | GRC & Risk Management

**Program:** Networkwalks Cybersecurity & Penetration Testing Internship  
**Batch:** B084 | Week 1  
**Project Focus:** Wireshark Installation, Packet Capture, Protocol Inspection & Network Traffic Analysis

<div align="center">

**“Cybersecurity begins with vigilance. Failure to prevent a threat today may become tomorrow's data disaster.”**

*— Lamidi Olatunji Micheal Eleshin*

</div>

