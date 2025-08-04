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
nmap -sS 192.168.120.0/24 -oN scan_results.txt
This scanned all 256 IPs in my local network and saved the results to a file.

📄 What I Found
Out of 256 IPs scanned, 2 devices were online. Here's what I learned:

🖥 1. Host: 192.168.120.240
Open Port: 53/tcp → This is commonly used for DNS (Domain Name System)

🧑‍💻 2. My System: 192.168.120.227
Open Ports:
- 135/tcp – Microsoft RPC (Remote Procedure Call)

- 139/tcp – NetBIOS Session Service (used for file sharing)

- 445/tcp – SMB (also used for file and printer sharing)

- 5357/tcp – Web Services for Devices (used by Windows)

- 16992/tcp – Intel AMT (remote management interface)

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
