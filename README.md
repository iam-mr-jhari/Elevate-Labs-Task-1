# 🔍 Nmap Scan Observations – demo.testfire.net

This repository documents and analyzes various Nmap scan techniques performed on the target host demo.testfire.net. Each scan demonstrates different capabilities of Nmap, from basic host discovery to full-scale service enumeration. The goal is to provide clear, beginner-friendly insights into how Nmap works and what its outputs reveal.



## 📘 Observation of Command: nmap -Pn demo.testfire.net

### 🔧 Command and Purpose

The command nmap -Pn demo.testfire.net performs a scan **without host discovery**, assuming the host is up. This is useful when ICMP (ping) requests are blocked by firewalls or the target is configured to ignore them.

Unlike a ping scan (-sn), this command proceeds directly to port scanning and service detection, even if the host doesn't respond to pings.



## 📘 Observation of Command: nmap -sn demo.testfire.net

### 🔧 Command and Purpose

The command nmap -sn demo.testfire.net initiates a **ping scan**, which checks whether the host is online without scanning ports. The -sn flag tells Nmap to skip port probing and focus solely on host availability.

- **Result**: The host demo.testfire.net (IP: 65.61.137.117) is up and reachable.
- **Latency**: Approximately 0.047 seconds.

This scan is ideal for quickly identifying active hosts in a network.

### 🌐 IPv6 and Scan Duration

- **IPv6 Address**: 64:ff9b::413d:8975 was listed but not scanned, suggesting dual-stack support (IPv4 + IPv6).
- **Scan Duration**: 33.45 seconds, which is relatively long for a single host—likely due to DNS resolution or network latency.



## 📘 Observation of Command: nmap -p 1-65535 -T4 -A -v demo.testfire.net

### 🔧 Command Execution

This command performs an **intense scan** of all TCP ports on the target host, with aggressive timing and advanced detection features.

- -p 1-65535: Scans all 65,535 TCP ports.
- -T4: Uses a faster timing template for quicker results.
- -A: Enables OS detection, version detection, script scanning, and traceroute.
- -v: Activates verbose mode for detailed output.

This scan is ideal for deep reconnaissance and full visibility into a target’s services.

### 📊 Scan Results

- **Nmap Version**: 7.97
- **Scan Time**: 21:01 IST, August 4, 2025
- **NSE Scripts Loaded**: 158
- **Target IP**: 65.61.137.117

#### ✅ Open Ports Detected:
| Port      | Protocol | Description                          |
|--|-|--|
| 8080/tcp  | TCP      | Commonly used for web or proxy services |
| 443/tcp   | TCP      | HTTPS – Secure web traffic           |
| 80/tcp    | TCP      | HTTP – Standard web server           |

These results indicate that the host is actively serving web content over both secure and non-secure channels, with additional services possibly running on port 8080.



## 📚 Educational Value

This repository is part of a broader initiative to make cybersecurity tools and techniques accessible to learners and practitioners. Each scan is documented with clear explanations to help users understand:

- The purpose and impact of different Nmap flags
- How to interpret scan results
- What services and configurations are exposed by a target



## 🚀 Future Enhancements

- Add visual walkthroughs for each scan type
- Build interactive web-based tutorials using these examples
- Integrate scan outputs into a beginner-friendly cybersecurity dashboard




Feel free to fork, contribute, or suggest improvements!

