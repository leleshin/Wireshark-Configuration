<div align="center">

# 🔐 Cybersecurity Internship – B084
## Week 2: Footprinting, Reconnaissance & Network Scanning

**Hands-On Domain Intelligence, DNS Enumeration, Website Fingerprinting & Local Network Discovery**

**NETWORKWALKS | CYBERSECURITY & PENETRATION TESTING INTERNSHIP**

<img src="https://img.shields.io/badge/Tool-WHOIS-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-WhatWeb-C00000?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-nslookup-404040?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-curl-238F89?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-wafw00f-E87500?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-DNSRecon-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/Tool-Zenmap%20%7C%20Nmap-C00000?style=flat-square" />

</div>

---

## 📌 Project Overview

This repository documents my hands-on experience with **footprinting, reconnaissance and network scanning** during Week 2 of the Networkwalks Cybersecurity and Penetration Testing Internship, Batch B084.

I used six Kali Linux tools to gather and compare information about **networkwalks.com**. I explored domain registration, website technologies, DNS resolution, HTTP response headers, web application firewall detection and DNS records.

For the second activity, I used **Zenmap**, the graphical interface for Nmap, to discover responding devices on my own local network and examine the topology view.

These activities helped me understand how information gathering supports a cybersecurity assessment. I also learned to support my observations with evidence and avoid treating every visible technical detail as a vulnerability.

**Modules covered:** W2-PM1 Multiple Kali Tools and W2-PM5 Zenmap Scanning.

**Activity dates:** 10 November 2026 for the dated footprinting outputs and 11 November 2026 for the documented Zenmap scan.

The practical learning activities include:

- Reviewing public domain registration information.
- Fingerprinting website technologies.
- Resolving domain names to IP addresses.
- Inspecting HTTP response headers.
- Checking for a detectable web application firewall.
- Enumerating DNS records and related infrastructure.
- Discovering responding hosts on my local network.
- Recording selected IP and MAC address pairs.
- Reviewing a network discovery topology.
- Protecting private details when preparing documentation.

---

## 🎯 Project Objectives

1. Use WHOIS to review domain registration details.
2. Identify website technologies with WhatWeb.
3. Resolve a domain name using nslookup.
4. Inspect HTTP response headers using curl.
5. Check for a detectable WAF using wafw00f.
6. Enumerate DNS records using DNSRecon.
7. Compare observations from different tools.
8. Run a local host discovery scan using Zenmap.
9. Review selected IP and MAC addresses and the topology view.
10. Document results accurately and protect private network information.

---

## 🛠️ Tools and Supporting Environment

| Tool or environment | Purpose in my practical |
|---|---|
| Kali Linux in Oracle VirtualBox | Run the footprinting commands |
| WHOIS | Review registration dates, registrar and name servers |
| WhatWeb | Identify reported web technologies and versions |
| nslookup | Resolve the target domain through DNS |
| curl | Inspect the HTTPS response headers with `-I` |
| wafw00f 2.4.2 | Check for a detectable web application firewall |
| DNSRecon | Enumerate DNS and service discovery records |
| Windows and Zenmap | Run and review the local host discovery scan |
| Nmap 7.993 | Host discovery engine reported in the scan output |

The target for the footprinting activity was **networkwalks.com**. The Zenmap activity concerned **my own local network**. The commands below record the exercises; they should only be used within an approved testing scope.

---

## 🌐 Step 1: Domain Registration Research with WHOIS

I started with WHOIS to understand the domain registration and identify the listed name servers.

```bash
whois networkwalks.com
```

### Screenshot 1: WHOIS Domain Information

![](images/01-WHOIS.png)

*Figure 1: WHOIS output for networkwalks.com.*

### Observations

| Field | Result shown in my output |
|---|---|
| Registrar | GoDaddy.com, LLC |
| Creation date | 6 November 2019 |
| Registry expiry date | 6 November 2027 |
| Name server 1 | NS6135.HOSTGATOR.COM |
| Name server 2 | NS6136.HOSTGATOR.COM |
| DNSSEC status | Unsigned |

I learned that domain registration information can provide an initial picture of a target. The unsigned DNSSEC status is a configuration observation for review; it does not establish that the domain has been compromised.

---

## 🧩 Step 2: Website Fingerprinting with WhatWeb

I used WhatWeb to identify technologies reported in the website responses.

```bash
whatweb networkwalks.com
```

### Screenshot 2: WhatWeb Technology Identification

![](images/02-WhatWeb.png)


*Figure 2: WhatWeb results, including an HTTPS redirect and reported web technologies.*

### Observations

- An HTTP **301 redirect** led to HTTPS, followed by **200 OK** responses.
- The output identified **Apache**.
- WhatWeb reported **WordPress 7.1.4**, **jQuery 3.7.1** and **WordPress Download Manager 3.3.76**.
- The website title appeared as **Networkwalks Academy**.
- The public web address was **192.232.216.135**.

I learned that website responses can reveal software information useful for further review. These are tool-reported versions, not independently verified installation details. I would confirm them before checking applicable security advisories or drawing conclusions about vulnerabilities.

---

## 📡 Step 3: DNS Resolution with nslookup

I used nslookup to identify the IP address associated with the domain.

```bash
nslookup networkwalks.com
```

### Screenshot 3: Domain Name Resolution

![nslookup DNS resolution output](images/03-nslookup.png)

*Figure 3: nslookup returning the target domain's public IP address.*

| Field | Observed result |
|---|---|
| DNS resolver | 8.8.8.8 |
| DNS port | 53 |
| Target name | networkwalks.com |
| Returned address | 192.232.216.135 |
| Response type | Non-authoritative answer |

The returned address matched my WhatWeb results. I learned that a non-authoritative answer comes from the resolver rather than directly from an authoritative name server. It does not automatically mean that the answer is incorrect.

The visible public IP addresses in the footprinting screenshots relate to the public target or its infrastructure. Private device details are handled separately in the Zenmap evidence.

---

## 📨 Step 4: HTTP Header Inspection with curl

I used curl with the `-I` option to request response headers.

```bash
curl -I https://networkwalks.com
```

### Screenshot 4: HTTP Response Headers

![curl output showing the HTTPS response headers](images/04-curl-Headers.png)

*Figure 4: curl response headers, including WordPress API links and server information.*

### Observations

- The response status was **HTTP/2 200**.
- The server header identified **Apache**.
- The content type was **text/html; charset=UTF-8**.
- The `x-nginx-cache` header showed **WordPress**.
- The Link header included `/wp-json/` and `/wp-json/wp/v2/pages/53`.
- A cookie included **Secure** and **HttpOnly** attributes.
- The response included **Permissions-Policy** and **Referrer-Policy** headers.

I learned that HTTP headers provide useful information about a web application. A WordPress REST API link is not, by itself, evidence of unauthorized access or a vulnerability. I would review exposed functionality and headers against the website's requirements.

---

## 🛡️ Step 5: WAF Detection with wafw00f

I used wafw00f to check whether the site appeared to use a web application firewall.

```bash
wafw00f networkwalks.com
```

### Screenshot 5: Web Application Firewall Detection

![wafw00f output reporting ModSecurity SpiderLabs](images/05-wafw00f.png)

*Figure 5: wafw00f reporting ModSecurity (SpiderLabs) after two requests.*

The tool reported **ModSecurity (SpiderLabs)** for the HTTPS site. This helped me understand how a security control may be identified from response behaviour.

Detection does not confirm the WAF's configuration, rule coverage or effectiveness. I did not validate attack blocking as part of this activity.

---

## 🗂️ Step 6: DNS Enumeration with DNSRecon

I used DNSRecon to examine the domain's DNS records and related services.

```bash
dnsrecon -d networkwalks.com
```

### Screenshot 6: DNSRecon Enumeration Results

![DNSRecon general enumeration showing DNS and service records](images/06-DNSRecon.png)

*Figure 6: DNSRecon output showing name servers, mail information, TXT records and autodiscover results.*

### Observations

| Record or detail | Result shown in my output |
|---|---|
| A record | networkwalks.com → 192.232.216.135 |
| Name server | ns6135.hostgator.com → 50.87.144.87 |
| Name server | ns6136.hostgator.com → 192.232.216.131 |
| Mail record | mail.networkwalks.com → 192.232.216.135 |
| TXT records | Site verification and SPF information |
| SPF policy ending | `~all`, indicating softfail |
| Reported DNS software | BIND 9.16.23-RH |
| Autodiscover service | Eight SRV results associated with cpanelemaildiscovery.cpanel.net on port 443 |
| DNSSEC query | No answer reported |

I learned how DNS records connect a website with its name servers, mail services and service discovery infrastructure. The DNS software version is tool-reported and would need verification. Public DNS records are not inherently vulnerabilities; their relevance depends on configuration and operational requirements.

---

## 🖥️ Step 7: Local Network Discovery with Zenmap

I used Zenmap's **Ping scan** profile to discover responding hosts on my own local network.

The generated command used **`nmap -sn`**, which performs host discovery without a port scan. The private target subnet is masked in the shared image.

### Screenshot 7: Scan Output and Annotated Topology

![Privacy-edited Zenmap scan and annotated topology showing four selected IP and MAC pairs](images/07-Zenmap-Scan-and-Topology.png)

*Figure 7: Combined Zenmap scan output and annotated topology. Four selected IP and MAC pairs remain visible; other devices' identifiers are obscured.*

### Scan Summary

| Scan detail | Recorded result |
|---|---|
| Profile | Ping scan |
| Nmap version shown | 7.993 |
| Start time | 11 November 2026, 21:56 -0500 |
| Addresses scanned | 256 |
| Hosts reported up | 10 |
| Duration | 8.35 seconds |
| Port scan results | Not part of this host discovery scan |

### Selected IP and MAC Addresses

| IP address | MAC address | Vendor reported by Nmap |
|---|---|---|
| 10.0.0.1 | A8:70:5D:03:CA:E5 | Commscope |
| 10.0.0.8 | 3A:87:26:7B:AA:B6 | Unknown |
| 10.0.0.29 | B0:22:7A:16:CB:C0 | HP |
| 10.0.0.31 | 1C:30:08:60:08:81 | Hui Zhou Gaoshengda Technology |

The four entries above are a selected subset of the **10 responding hosts**, not the full host inventory. I kept the other six devices' addresses and identifying labels hidden in the shared documentation.

I learned that host discovery supports an inventory review. A responding device is not automatically unauthorized or insecure, and a device that does not respond may still be present. Vendor labels also do not independently confirm ownership or device identity.

---

## 🕸️ Step 8: Network Topology Review

After reviewing the scan output, I examined Zenmap's Topology view. The lower panel of Figure 7 shows **ten green host nodes around localhost**.

The four selected MAC address labels were added to the shared topology image for documentation. This image is a **privacy-edited and annotated presentation of the evidence**, rather than an untouched screenshot. Those labels should not be treated as a separate native Zenmap measurement.

The topology helped me compare the discovery output visually. It does not establish the physical connections between the devices.

The image does not show an open legend. A separate topology export with the legend and a Windows network configuration screenshot can be added if required by the practical submission.

---

## 📊 Findings and Interpretation

| Observation | What I learned | Suggested follow-up |
|---|---|---|
| Public registration and DNS information | Public records help describe a domain's infrastructure | Confirm records are accurate and required |
| Reported CMS and plugin versions | Responses can identify technologies for further review | Verify versions and review relevant advisories |
| HTTP headers and REST API links | Headers reveal application behaviour and features | Review unnecessary disclosure and access requirements |
| ModSecurity detected | A WAF may be identifiable from responses | Confirm deployment and maintain rules and logs |
| Ten local hosts responded | Discovery supports device inventory work | Compare results with approved devices |
| Private device identifiers in scan results | Shared evidence can expose local network details | Retain privacy masks for devices outside the selected subset |

These observations are **not confirmed vulnerability findings**. I did not perform exploitation, password attacks or vulnerability validation in these exercises.

---

## 💡 Recommendations

1. Verify reported software versions before assessing their security status.
2. Maintain supported website software and plugins.
3. Review HTTP headers and exposed API functionality against operational needs.
4. Review DNS, DNSSEC and SPF settings with the responsible administrator or provider.
5. Maintain the WAF and review its logs.
6. Compare local discovery results with a current device inventory.
7. Keep commands, dates and screenshots together when documenting observations.
8. Protect private identifiers before publishing evidence.
9. Retain appropriate authorization and stay within the approved scope.

---

## 📚 Learning Outcomes

Through this practical project, I developed a better understanding of:

1. Using WHOIS for domain registration research.
2. Identifying reported website technologies with WhatWeb.
3. Resolving domain names using nslookup.
4. Reading HTTP response headers using curl.
5. Interpreting WAF detection results responsibly.
6. Examining DNS and service discovery records.
7. Comparing information returned by different tools.
8. Running a local Zenmap host discovery scan.
9. Recording selected IP and MAC addresses.
10. Explaining scan results without overstating their security implications.
11. Reviewing a network discovery topology.
12. Preparing clear documentation while protecting private network details.

---

## 📎 Evidence and Report Files

| File | Description |
|---|---|
| [01-WHOIS.png](images/01-WHOIS.png) | Domain registration screenshot |
| [02-WhatWeb.png](images/02-WhatWeb.png) | Website fingerprinting screenshot |
| [03-nslookup.png](images/03-nslookup.png) | DNS resolution screenshot |
| [04-curl-Headers.png](images/04-curl-Headers.png) | HTTP response header screenshot |
| [05-wafw00f.png](images/05-wafw00f.png) | WAF detection screenshot |
| [06-DNSRecon.png](images/06-DNSRecon.png) | DNS enumeration screenshot |
| [07-Zenmap-Scan-and-Topology.png](images/07-Zenmap-Scan-and-Topology.png) | Privacy-edited scan output and annotated topology |

**GitHub setup:** Extract this package, then upload `README.md`, the `images` folder and the Word report together to the repository root. Keep the filenames and folder structure unchanged so the image links work. The badges use externally hosted Shields.io images.

---

## 🛡️ Ethical Security Statement

I carried out these activities as part of my educational cybersecurity training, within the scope recorded for the practical. Reconnaissance and scanning must remain limited to systems and networks for which appropriate permission has been granted.

The public target's infrastructure addresses remain visible in the footprinting evidence. In the local network evidence, only the four selected IP and MAC pairs are disclosed. Other device identifiers are obscured.

---

## 👨‍💻 About the Author

**Lamidi Olatunji Micheal Eleshin**

Cybersecurity & Penetration Testing Intern | Aspiring Cybersecurity Analyst | IT Auditor | IT Support Engineer | GRC & Risk Management

**Specialization Areas:**

Cybersecurity | Network Security | IT Auditing | Governance, Risk & Compliance | Penetration Testing | SOC Operations

**Internship:** Networkwalks Cybersecurity & Penetration Testing

**Batch:** B084 | Week 2

**Project Focus:** Footprinting, Reconnaissance, DNS Enumeration, Host Discovery & Network Documentation

**LinkedIn:** [Lamidi Olatunji Eleshin](https://www.linkedin.com/in/lamidi-olatunji-eleshin-4834252ab/)

---

<div align="center">

**"Cybersecurity begins with vigilance. Failure to prevent a threat today may become tomorrow's data disaster."**

*— Lamidi Olatunji Micheal Eleshin*

</div>
