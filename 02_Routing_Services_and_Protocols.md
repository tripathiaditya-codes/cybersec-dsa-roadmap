
---

## 📘 Chapter 2 — `02_Routing_Services_and_Protocols.md`

```markdown
# 🚦 Chapter 2: Routing, Services, and Protocols

This chapter focuses on how data moves across networks and the protocols that enable communication.

---

## 🌍 2.1 Routing Basics

| Term | Description |
|------|--------------|
| **Routing** | The process of selecting a path for traffic in a network. |
| **Static Routing** | Manually configured routes — used in small networks. |
| **Dynamic Routing** | Automatically adjusts routes using protocols. |
| **Default Route** | Route used when no other matches (0.0.0.0/0). |
| **Hop** | Each router a packet passes through. |

---

## 🔁 2.2 Routing Protocols

| Type | Example | Description |
|-------|----------|--------------|
| **Interior Gateway Protocols (IGP)** | RIP, OSPF, EIGRP | Used within an organization. |
| **Exterior Gateway Protocols (EGP)** | BGP | Used between ISPs and large networks. |

🧠 **Key Idea:**  
- RIP → Uses hop count  
- OSPF → Uses link cost (faster, more scalable)  
- BGP → Backbone of the Internet  

---

## 📨 2.3 Core Network Protocols

| Protocol | Port | Function |
|-----------|------|-----------|
| **HTTP / HTTPS** | 80 / 443 | Web browsing |
| **FTP / SFTP** | 21 / 22 | File transfer |
| **SSH** | 22 | Secure remote access |
| **DNS** | 53 | Domain name to IP resolution |
| **DHCP** | 67-68 | Assigns IPs dynamically |
| **SNMP** | 161 | Network device monitoring |
| **ICMP** | N/A | Error reporting (used by ping) |
| **SMTP / POP3 / IMAP** | 25 / 110 / 143 | Email communication |

---

## 🧩 2.4 Network Address Translation (NAT)

| Type | Description |
|------|--------------|
| **Static NAT** | One private ↔ one public IP mapping |
| **Dynamic NAT** | Private IPs share a pool of public IPs |
| **PAT (Port Address Translation)** | Many private IPs share one public IP (home routers use this) |

📖 **SOC Note:** NAT hides internal IPs — useful for anonymity and defense.

---

## ⚙️ 2.5 VLANs (Virtual LANs)

- Logical segmentation of a network to isolate devices.  
- Reduces broadcast traffic and enhances security.  
- Configured on switches.  
- Example:  
  - VLAN 10 – HR  
  - VLAN 20 – IT  
  - VLAN 30 – Finance

---

## 📡 2.6 DNS and DHCP in Action

- **DNS:** Translates domain → IP.  
- **DHCP:** Automatically assigns IPs to devices.  

Example flow:
1. Client sends DHCP Discover  
2. Server responds with DHCP Offer  
3. Client sends DHCP Request  
4. Server sends DHCP Acknowledge  

---

## 🧠 2.7 Common Network Troubleshooting

| Problem | Tool | Command |
|----------|------|----------|
| Connectivity | `ping` | `ping 8.8.8.8` |
| DNS issue | `nslookup` | `nslookup google.com` |
| Routing | `traceroute` | `traceroute 8.8.8.8` |
| Port check | `nmap` | `nmap <ip>` |

---

## 🧩 2.8 Key Interview Questions

- Difference between static and dynamic routing?  
- What is DNS and how does it work?  
- Explain the difference between NAT and PAT.  
- What are the uses of VLANs?  
- What ports do HTTP and HTTPS use?  
- What is DHCP lease time?

---
