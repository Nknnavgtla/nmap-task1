🛰 Cybersecurity Task 1 – Nmap Network Scan
Hi there! 👋  
This repository contains the results and notes from *Task 1* of my Cyber Security Internship. The goal of this task was to get hands-on with *network scanning* using a tool called *Nmap*.

---

## 🧠 What I Did

I scanned my *local network* to find out:
- Which devices are connected
- What ports are open on those devices
- What kind of services might be running on those ports
- Whether those open ports could be potential security risks

This is a fundamental skill in cybersecurity called *network reconnaissance*.

---

## 🔧 Tools Used

- *Nmap 7.97* – Command-line tool for scanning networks
- *Command Prompt (Windows)* – For running Nmap
- (Optional: Wireshark – not used in this task but useful for future packet analysis)

---

## 📍 My Network Info

- *My IP Address:* 10.159.10.0
- *Subnet Scanned:* 255.255.255.0/24
- *Scan Type:* TCP SYN Scan (-sS)

---

## 💻 Command Used

```bash
nmap -sS 255.255.255.0/24 -oN scan_results.txt
This scanned all 256 IPs in my local network and saved the results to a file.

📄 What I Found
Out of 256 IPs scanned, 2 devices were online. Here's what I learned:

🖥 1. Host: 192.168.120.240
Open Port: 53/tcp → This is commonly used for DNS (Domain Name System)

🧑‍💻 2. My System: 10.159.10.0

Nmap scan report for 192.168.48.1
Host is up (0.0012s latency).
Not shown: 995 closed tcp ports (reset)
PORT    STATE SERVICE
135/tcp open  msrpc
139/tcp open  netbios-ssn
445/tcp open  microsoft-ds
902/tcp open  iss-realsecure
912/tcp open  apex-mesh

# Nmap done at Mon Aug  4 17:44:50 2025 -- 256 IP addresses (2 hosts up) scanned in 82.50 seconds

⚠ Security Observations
Ports 139 and 445 are known for vulnerabilities (e.g., WannaCry ransomware exploited SMB on port 445).

Port 16992 is used by Intel's remote management and should be disabled if not actively used — it could be a serious risk if left open.

DNS (port 53) on another device could be vulnerable if misconfigured or externally exposed.

📁 Files in This Repo
README.md – You’re reading it 😊

scan_results.txt – Raw Nmap scan output

✅ What I Learned
How to use Nmap to explore a network

How to interpret open ports and running services

Why it's important to identify and manage network exposure
```
What are the Problems A Faced During this Task 1
-   1).get_srcaddr: can't connect socket: A socket operation was attempted to an unreachable network.
- 🔍 What’s Causing It?
- You're likely scanning a subnet that:
- Doesn’t exist on your system,
- Or is unreachable (e.g., Wi-Fi disconnected, VPN active),
- Or you're scanning the wrong IP range (not matching your actual network).
- 2).'nmapnmap' is not recognized as an internal or external command, operable program or batch file.
- a)Nmap isn't installed properly, or
- b)You typed the command incorrectly (likely repeated "nmap" by mistake).
