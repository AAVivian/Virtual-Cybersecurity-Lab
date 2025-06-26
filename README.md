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

