# nmap-network-discovery-tutorial\
By Jessica Canterino
A practical cybersecurity tutorial introducing Nmap, an open-source network discovery and security auditing tool.

## What You'll Learn
- What Nmap does and why it matters
- How to install and verify Nmap
- How to discover hosts and scan TCP ports
- How to identify service versions and estimate operating systems
- How to interpret scan results and save output
- How to follow an example Nmap workflow

## Hacker's Toolbox Part I
[The Hacker's Toolbox Project - Part I_JCanterino (1).pdf](https://github.com/user-attachments/files/33677846/The.Hacker.s.Toolbox.Project.-.Part.I_JCanterino.1.pdf)

## Hacker's Toolbox Part II

[YouTube Demonstration Link](https://youtu.be/YVeD5lrKdHQ)

##
**Installation**
	Nmap has minimal system requirements and runs on virtually all major operating systems, including Linux, Windows, and macOS. It requires very low processing power and memory, making it capable of running smoothly inside virtual machines or lightweight laptop environments. On Linux distributions such as Kali Linux or Ubuntu, installation is completed through the terminal by updating the package manager and running sudo apt update && sudo apt install nmap. On Windows or macOS, users can download the graphical installer or command-line package directly from the official Nmap repository. Initial configuration simply requires opening a terminal window and verifying the installation by typing nmap --version to ensure the binary executes properly and displays the installed version.
<img width="1450" height="940" alt="Installation Verification" src="https://github.com/user-attachments/assets/c0f01af7-6ac4-4f76-962b-332fcaaa1616" />

## Example Commands

```bash
nmap -sn 127.0.0.1
sudo nmap -sS 127.0.0.1
sudo nmap -sV -O -oA audit_results 127.0.0.1
```

These examples use localhost for practice. Results vary based on the operating system and running services.

## Responsible Use

Only scan systems and networks that you own or have explicit permission to assess. Follow the applicable authorization and scope requirements.

---
Cheat Sheet
By Jessica R. J. Canterino  

---
Tool Overview
Nmap (Network Mapper is an open-source security auditing and active network discovery tool. It allows cybersecurity professionals and network administrators to map attack surfaces, discover active network hosts, inspect open TCP/UDP ports, estimate running service versions, and gather remote operating system characteristics.

---
Quick-Reference Command Sequence

Execute this structured 4-step sequence to perform a complete, authorized audit from host discovery to service enumeration and logging:

```bash
# Step 1: Confirm target reachability without port scanning
nmap -sn <authorized-target>

# Step 2: Enumerate top TCP ports using a SYN (half-open) scan
sudo nmap -sS <authorized-target>

# Step 3: Identify running service versions, estimate target OS, and log output
sudo nmap -sV -O -oA audit_results <authorized-target>

# Step 4: Run default NSE scripts for basic service enumeration (if within scope)
sudo nmap -sC -oA script_results <authorized-target>
```

---
Command Switch Reference

| Switch / Flag | Name | Operational Description |
 `-sn` is the host discovery option that determines if hosts appear online using ICMP, TCP, or ARP probes without scanning individual ports. 

 `-sS` is a TCP SYN Scan, which executes a half-open scan using raw TCP SYN packets. Requires elevated privileges (`sudo`). 

 `-sV` is service Detection, which probes open ports to identify running software titles and version numbers. 
 
 `-O`, OS Detection, analyzes network response fingerprints to estimate the remote operating system. 
 
 `-sC` is for Default Scripts, which runs default Nmap Scripting Engine (NSE) scripts to inspect discovered services. 
 
`-oA <prefix>` is for All Output Formats, which automatically saves scan results in Normal (`.nmap`), XML (`.xml`), and Grepable (`.gnmap`) formats.

 `-Pn` is Skip Discovery, which treats all targets as online, bypassing initial host discovery probes (does not bypass firewalls). 

---
Best Practices

1. Explicit Authorization: Perform scans only against systems you own or have explicit, documented authorization to test.
2. Scope Definition: Verify target IP addresses and ranges against your approved Scope of Engagement prior to execution.
3. Audit Logging: Always use `-oA` to maintain verifiable records of scan activities, parameters, and timeframes.
4. Timing Control: Match scan speed templates (`-T0` through `-T5`; default `-T3`) to network capacity and sensitivity to prevent service disruption.
---
References

Aircrack-ng. (2024). Aircrack-ng Wi-Fi security suite. [https://www.aircrack-ng.org/ ](url)
Autopsy. (2024). Autopsy digital forensics platform. https://www.autopsy.com/ 
Carvalho, A. M. (2023). TryHackMe: Metasploit Meterpreter overview. Medium. https://medium.com/@andreyna.m.carvalho/tryhackme-metasploit-meterpreter-14a667408b11
Cmnatic. (2024). Offensive security intro room: Web content scanning with Dirb. TryHackMe. TryHackMe.https://tryhackme.com/room/offensivesecurityintrokKx12 
DarkStar7471. (2020). Nmap room. TryHackMe. https://tryhackme.com/room/furthernmap 
DigiNinja. (2024). CeWl: Custom word list generator [Computer software]. GitHub. https://github.com/digininja/Cewl 
Double Octopus. (2024). Security wiki: Meterpreter. https://doubleoctopus.com/security-wiki/threats-and-tools/meterpreter/ 
Flipper Devices. (2024). Flipper Zero portable micro-server for hardware and wireless security testing. https://flipper.net/ 
Imperva. (2024). Application security: Metasploit framework and payloads. https://www.imperva.com/learn/application-security/metasploit/ 
Kali Linux. (2024a). Bettercap network framework. Kali Linux Documentation. https://www.kali.org/tools/bettercap/ 
Kali Linux. (2024b). Wireshark package overview. Kali Linux Documentation. https://www.kali.org/tools/wireshark/ 
Lyon, G. (2009). Nmap reference guide. Nmap Project. https://nmap.org/book/man.html 
MuirlandOracle. (2024). Introductory networking and basic networking tools room. TryHackMe Documentation. https://tryhackme.com/room/introtonetworking 
ThreatLocker. (2024). WiFi Pineapple hacking: How wireless access points are impersonated. ThreatLocker Blog. https://www.threatlocker.com/blog/wifi-pineapple-hacking-how-hackers-can-infiltrate-your-wifi 
Vectra AI. (2024). Metasploit topics & Meterpreter memory-resident agent architecture. https://www.vectra.ai/topics/metasploit 
