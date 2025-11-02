# 🌐 Chapter 1: Network Fundamentals

A beginner-friendly yet detailed guide to understanding how computer networks work — from bits to global-scale communication.

---

## 🧩 1.1 What is Networking?

**Networking** is the process of connecting two or more devices (computers, servers, IoT, etc.) to share data and resources (like files, printers, or internet access).  
These devices communicate using protocols and follow a structured model called **OSI** or **TCP/IP model**.

---

## 🔌 1.2 Types of Networks

| Type | Range | Example |
|-------|--------|----------|
| **PAN (Personal Area Network)** | Few meters | Bluetooth, Hotspot |
| **LAN (Local Area Network)** | Within building | Office or Home Network |
| **MAN (Metropolitan Area Network)** | City-wide | Cable TV Network |
| **WAN (Wide Area Network)** | Country/Global | Internet |
| **SAN (Storage Area Network)** | Data centers | High-speed storage sharing |
| **CAN (Campus Area Network)** | University/Corporate campus | College Wi-Fi |

---

## 🧱 1.3 Network Devices

| Device | Function |
|--------|-----------|
| **Hub** | Broadcasts data to all devices (Layer 1). |
| **Switch** | Forwards packets based on MAC addresses (Layer 2). |
| **Router** | Routes data between networks (Layer 3). |
| **Modem** | Converts digital to analog signals for internet access. |
| **Access Point (AP)** | Connects wireless devices to wired networks. |
| **Firewall** | Controls incoming and outgoing traffic based on rules. |
| **Gateway** | Connects different network types (e.g., LAN ↔ Internet). |

---

## 🧩 1.4 OSI Model (7 Layers)

| Layer | Name | Function | Example Protocols |
|--------|-------|-----------|-------------------|
| 7 | Application | User interface, app services | HTTP, FTP, DNS, SMTP |
| 6 | Presentation | Data encryption, compression | SSL/TLS, JPEG |
| 5 | Session | Connection management | RPC, NetBIOS |
| 4 | Transport | Reliable delivery (segments) | TCP, UDP |
| 3 | Network | Routing and addressing | IP, ICMP |
| 2 | Data Link | Error detection, MAC addressing | Ethernet, ARP |
| 1 | Physical | Transmission of bits | Cables, NIC |

🧠 **Tip:** Remember it as — *“Please Do Not Throw Sausage Pizza Away”*

---

## 🖧 1.5 TCP/IP Model

| Layer | Function | Example Protocols |
|--------|-----------|-------------------|
| Application | User interface and app protocols | HTTP, DNS, SMTP |
| Transport | End-to-end communication | TCP, UDP |
| Internet | Logical addressing and routing | IP, ICMP |
| Network Access | Physical data transmission | Ethernet, ARP, Wi-Fi |

---

## ⚙️ 1.6 IP Addressing

### IPv4
- 32-bit address → `192.168.1.1`
- Private Ranges:
  - 10.0.0.0 – 10.255.255.255  
  - 172.16.0.0 – 172.31.255.255  
  - 192.168.0.0 – 192.168.255.255

### IPv6
- 128-bit address → `2001:0db8:85a3::8a2e:0370:7334`
- Provides larger address space and better security.

---

## 📡 1.7 Subnetting Basics

| Class | Range | Default Subnet Mask | Use |
|--------|--------|----------------------|------|
| A | 1.0.0.0 – 126.0.0.0 | 255.0.0.0 | Large networks |
| B | 128.0.0.0 – 191.255.0.0 | 255.255.0.0 | Medium networks |
| C | 192.0.0.0 – 223.255.255.0 | 255.255.255.0 | Small networks |

🧮 **CIDR Notation:** `/24` → 255.255.255.0 → 256 IPs

---

## 💬 1.8 Basic Network Commands

```bash
ping google.com        # Test connectivity
tracert google.com     # Windows route tracing
traceroute google.com  # Linux route tracing
ipconfig / ifconfig    # Show IP configuration
netstat -ano           # Show active connections
nslookup example.com   # DNS lookup
