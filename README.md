# Virtual-Cybersecurity-Lab
A 3-part cybersecurity project: Building a Virtual Cyber Security Lab, Conducting Android Forensics and Deploying a Firewall to Stimulate an enterprise-grade network Security Environment.
## Part I Virtual Networking
### 🎯 Objective
To configure a virtual network between two VirtualBox virtual machines — Kali Linux and Windows 10 — for secure, isolated communication and penetration testing simulations.

### 💾 Software Used
Oracle VirtualBox 7.1.10
Kali Linux 2025.2 (VirtualBox Image)
Windows 10 ISO or preinstalled image
VC_redist.x64 (to resolve .DLL dependencies)

### 🌐 Virtual Network Configuration Steps
#### 📡 Step 1: VirtualBox Network Setup
Each VM was configured with one network adapter:
Adapter 1: Internal Network (intnet, for VM-to-VM communication only)
The adapter used Intel PRO/1000 MT Desktop adapter type with Promiscuous Mode set to Deny.

#### 🔗 Step 2: IP Address Assignment

Virtual Machine	Interface	IP Address	Network Adapter
*Kali Linux	eth0	192.168.56.30/24	Internal Network*
*Windows 10	Ethernet	192.168.56.40/24	Internal Network*
			
✅ On Kali Linux Terminal:
*sudo ip addr flush dev eth0*
*sudo ip addr add 192.168.56.30/24 dev eth0*
*sudo ip link set eth0 up*
✅ On Windows 10:
Open ncpa.cpl
Right-click the Ethernet adapter
*Set static IP to 192.168.56.40*
*Subnet mask: 255.255.255.0*
*No default gateway needed*

### 🔗 Connectivity Verification
✅ Ping from Kali to Windows:
ping 192.168.56.30

Result: Successful with response times indicating both VMs are connected.
✅ Ping from Windows to Kali:
*Using cmd → ping 192.168.56.40*
Result: Successful.

✅ Nmap Scan from Kali:
*nmap 192.168.56.30*
*I scanned the IP address 192.168.56.30, and Nmap responded with:*

All 1000 scanned ports on 192.168.56.30 are in ignored states.
Not shown: 1000 closed tcp ports (reset)

### 📷 Screenshots
![Running VMs](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/Running%20VMs.png)
![Network Setting For Window](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/Network%20Setting%20for%20Windows%20VM.png)
![Network Setting for Kali](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/Network%20Setting%20for%20Kali%20VM.png)
![Ip Configuration on Kali](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/Ip%20address%20Configuration%20on%20Kali.png)
![Ip Configuration for Windows]( https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/VirtualBox_Windows_25_06_2025_17_24_09.png)
![Connectivity Verification on Kali]( https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/Connectivity%20Verification%20on%20Kali.png)
![Nmap]( https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/NMAP.png)

## 🗒️ Part II - Android Forensics Investigation
This section of the project demonstrates foundational mobile device forensics using a sample forensoc image. The analysis was conducted using Autopsy.
### 🔍 Objectives:
Extracted and analyze:
	- SMS messages
 	- Call logs
  	- Contact lists
   	- Application usage
    	- Deleted files and browser history
     - Generate a formal forensics report with:
     	- Methodology
      	- Screenshots of findings
       	- Key evidence and recommendations
📂 **Download the full report here**: [![Download PDF](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/Android%20Forensic%20Investigation%20-%20Vivian%20Adewale-Abiola.pdf)

This PDF contains all evidence, screenshots and professional conclusions from the forensic analysis.

## Part III - Virtual Firewall Implementation
this repository contains the setup and configuration steps for simulating a basic enterprise firewall environment using **pfSense** within a virtual lab.
## 🧰 Tool Used
	- **VirtualBox** - for virtualizzation
 	- **pfSense ISO** - for firewall deployment
  	- **Kali Linux** (Attacker VM)
   	- **Windows 10** (Target VM)
## 🏵 Setup Overview
- Installed pfSense as a virtual appliance
- Configured: -**WAN Interface** : NAT - **LAN Interface**: Internal Network
- Connected to Kali and Windows to the pfSense LAN
- Verified internal connectivity (ping)
- Applied basic firewall rules to allow/block specific ports
## 🔍 Key Highlights
- Successfully routed all traffic through pfSense
- Block ports to test rule enforcement
- Captured denied traffic logs for validation
## 📷Screenshots
Screenshots of setup and results 
[![Windows LAN](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/LAN%20Network%20setting%20for%20PfSense%20-%20WINDOWS.png)
[![Kali LAN](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/LAN%20Network%20setting%20for%20PfSense%20-%20KALI.png)
[![pfSense](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/LAN%20Network%20Setting%20for%20PfSense.png)
[![ipconfiguration on pfSense](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/pfsense%20IPConfig.png)
[![Firewall ICMP](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/firewal%20icmp.png)
[![Firewall](https://github.com/AAVivian/Virtual-Cybersecurity-Lab/blob/main/firewall.png)
## 🗒️ Summary
This setup simulates a simplified enterprise security environment. It provides hands-on experience in:
- Network segmentation
- Firewall rule configuration
- Traffic routing and logging
