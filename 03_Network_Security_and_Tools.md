# 🔐 Chapter 3: Network Security and Tools  
*A complete guide for understanding network defense, analysis, and tools — designed for SOC Analyst learning.*

---

## 🧠 3.1 What is Network Security?

**Network Security** involves protecting the integrity, confidentiality, and availability of data transmitted across networks.  
It includes defense mechanisms that detect, prevent, and respond to cyber threats.

### Why it matters for a SOC Analyst:
As a SOC Analyst, you monitor network traffic, logs, and alerts to identify intrusions, malware activity, or data breaches in real time.

---

## 🧱 3.2 The CIA Triad (Security Foundation)

| Principle | Meaning | SOC Relevance |
|------------|----------|----------------|
| **Confidentiality** | Data is accessible only to authorized users. | Prevent data leaks and unauthorized access. |
| **Integrity** | Data is accurate and unaltered. | Detect tampering using checksums/log validation. |
| **Availability** | Systems and data are available when needed. | Monitor uptime and detect DoS/DDoS attacks. |

🧩 **SOC Tip:**  
Security logs should help you detect which part of CIA is violated during an incident.

---

## 🔒 3.3 Common Network Security Components

| Component | Function | Example / Relevance |
|------------|-----------|----------------------|
| **Firewall** | Filters inbound/outbound traffic using rules. | First layer of network defense. |
| **IDS (Intrusion Detection System)** | Detects suspicious activity. | Sends alerts to SOC dashboards (e.g., Suricata). |
| **IPS (Intrusion Prevention System)** | Detects & blocks malicious traffic. | Works inline with firewalls. |
| **Proxy Server** | Intermediary that filters web traffic. | Blocks malicious or unwanted sites. |
| **VPN** | Encrypts data for secure remote access. | Protects users on public Wi-Fi. |
| **DMZ (Demilitarized Zone)** | Public-facing network segment. | Hosts web/mail servers away from internal network. |
| **NAC (Network Access Control)** | Restricts unauthorized devices from joining. | Ensures device compliance. |

---

## 🧰 3.4 SOC Monitoring Layers

| Layer | What You Monitor | Example Tools |
|--------|------------------|----------------|
| **Network Layer** | Traffic patterns, ports, IPs | Wireshark, Zeek, Suricata |
| **Host Layer** | Logs, processes, user actions | Wazuh, Sysmon |
| **Application Layer** | HTTP, DNS, mail logs | ELK Stack, SIEM tools |
| **Perimeter Layer** | Firewall & IDS events | pfSense, Snort |
| **Cloud Layer** | Access logs, API events | Azure Sentinel, AWS GuardDuty |

---

## 🧩 3.5 Common Network Attacks (SOC View)

| Attack | Description | Detection Method |
|---------|--------------|------------------|
| **DoS / DDoS** | Overloads servers with traffic. | Monitor bandwidth spikes. |
| **ARP Spoofing** | Attacker impersonates another MAC. | Detect ARP table changes. |
| **DNS Spoofing** | Redirects traffic to malicious sites. | DNS query monitoring. |
| **MITM (Man-in-the-Middle)** | Intercepts communication between hosts. | SSL inspection and anomaly detection. |
| **Port Scanning** | Attacker identifies open ports. | Detect via Nmap fingerprinting alerts. |
| **Phishing / Malware** | Social engineering & malicious payloads. | Correlate email + proxy + endpoint logs. |

🧠 **SOC Note:**  
Your SIEM should alert if unusual DNS requests or port scans are detected on internal systems.

---

## 🧮 3.6 Encryption and Authentication

| Type | Description | Example |
|------|--------------|----------|
| **Symmetric Encryption** | Same key for encryption/decryption. | AES |
| **Asymmetric Encryption** | Public/private key pair. | RSA |
| **Hashing** | One-way function to verify integrity. | SHA-256 |
| **Authentication** | Verifies identity. | MFA, Kerberos |
| **Authorization** | Grants permissions post-authentication. | Role-based Access Control (RBAC) |

🧩 **SOC Tip:**  
Check if encryption protocols (TLS 1.2+) are enforced in web logs and disable insecure ones (SSL, TLS 1.0).

---

## ⚙️ 3.7 Key Network Security Tools

| Tool | Category | Use Case |
|------|-----------|-----------|
| **Wireshark** | Packet Analyzer | Capture and inspect network packets. |
| **tcpdump** | CLI Packet Capture | Lightweight traffic analysis. |
| **Nmap** | Network Scanner | Detect hosts, open ports, services. |
| **Netcat** | Network Utility | Port listening & data transfer testing. |
| **Snort / Suricata** | IDS/IPS | Detect suspicious traffic using signatures. |
| **Zeek (Bro)** | Network Monitor | Deep network traffic analysis. |
| **Nikto** | Web Vulnerability Scanner | Detect insecure HTTP configurations. |
| **TheHarvester** | Recon Tool | Gather emails, subdomains, hosts. |
| **Fping / Hping3** | Ping sweeps & packet crafting | Network discovery and testing. |

🧠 **SOC Application:**  
When your SIEM shows an alert (e.g., outbound connection to unknown IP), use `Wireshark` or `tcpdump` to investigate packet-level details.

---

## 🔍 3.8 Network Logs & SIEM Correlation

### 🔸 Network Log Sources
- Firewall logs (deny/allow rules)
- IDS/IPS alerts
- DNS logs
- Proxy logs
- VPN authentication logs
- Router & switch syslogs

### 🔸 SIEM Example: Azure Sentinel or Splunk
SOC Analysts use **correlation rules** like:
```spl
index=firewall OR index=dns
| stats count by src_ip, dest_ip, dest_port
| where count > 100 AND dest_port in (22,23,3389)
```

## 3.9 Important Network Metrics (For Analysis)


| Metric          | Meaning                | Why It Matters                 |
| --------------- | ---------------------- | ------------------------------ |
| **Bandwidth**   | Max data transfer rate | Identify network congestion    |
| **Latency**     | Delay between packets  | Detect performance issues      |
| **Throughput**  | Actual transfer speed  | Monitor during DDoS attacks    |
| **Jitter**      | Variation in latency   | Voice/video quality indicator  |
| **Packet Loss** | Dropped packets        | Sign of interference or attack |




## 🧪 3.10 Network Troubleshooting Commands

# Identify IP and interfaces
ipconfig /all             # Windows
ifconfig / ip addr show   # Linux

# Test connectivity
ping google.com

# Trace path
tracert google.com        # Windows
traceroute google.com     # Linux

# List open ports
netstat -ano              # Windows
ss -tuln                  # Linux

# Scan network
nmap -sS 192.168.1.0/24

# Capture packets
tcpdump -i eth0 port 80 -w capture.pcap


##🧩 3.11 Defense-in-Depth (SOC Strategy)

1.Perimeter Security – Firewalls, IDS/IPS
2.Network Segmentation – VLANs, subnets
3.Access Control – NAC, authentication policies
4.Endpoint Protection – EDR, antivirus
5.Monitoring & Detection – SIEM, log correlation
6.Incident Response – Contain, eradicate, recover

##📘 3.12 Interview Preparation (SOC Analyst Focus)

1.What’s the difference between IDS and IPS?
2.Explain CIA Triad with examples.
3.How does a firewall differ from a proxy?
4.What is a packet capture, and why is it useful?
5.How would you detect a port scan using SIEM logs?
6.What’s the role of VLANs in security?
7.What is SSL inspection, and why is it used?
8.Explain how NAT provides basic security.


##🧠 3.13 Quick Summary

1.Network security ensures CIA (Confidentiality, Integrity, Availability).
2.SOC Analysts monitor and correlate logs from multiple sources.
3.Tools like Wireshark, Nmap, Suricata, and Zeek are your core analysis toolkit.
4.SIEMs help detect patterns from raw network and endpoint logs.
5.Continuous monitoring, patching, and awareness form the backbone of network defense.

