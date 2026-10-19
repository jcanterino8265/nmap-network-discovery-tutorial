# nmap-network-discovery-tutorial
A practical Nmap tutorial for network discovery, port scanning, and security auditing.
[The Hacker's Toolbox Project - Part II - JCanterino.pptx](https://github.com/user-attachments/files/33648095/The.Hacker.s.Toolbox.Project.-.Part.II.-.JCanterino.pptx)

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
| `-sn` | Host Discovery | Determines if hosts appear online using ICMP, TCP, or ARP probes without scanning individual ports. |
| `-sS` | TCP SYN Scan | Executes a half-open scan using raw TCP SYN packets. Requires elevated privileges (`sudo`). |
| `-sV` | Service Detection | Probes open ports to identify running software titles and version numbers. |
| `-O` | OS Detection | Analyzes network response fingerprints to estimate the remote operating system. |
| `-sC` | Default Scripts | Runs default Nmap Scripting Engine (NSE) scripts to inspect discovered services. |
| `-oA <prefix>` | All Output Formats | Automatically saves scan results in Normal (`.nmap`), XML (`.xml`), and Grepable (`.gnmap`) formats. |
| `-Pn` | Skip Discovery | Treats all targets as online, bypassing initial host discovery probes (does not bypass firewalls). |

---
Best Practices

1. Explicit Authorization: Perform scans only against systems you own or have explicit, documented authorization to test.
2. Scope Definition: Verify target IP addresses and ranges against your approved Scope of Engagement prior to execution.
3. Audit Logging: Always use `-oA` to maintain verifiable records of scan activities, parameters, and timeframes.
4. Timing Control: Match scan speed templates (`-T0` through `-T5`; default `-T3`) to network capacity and sensitivity to prevent service disruption.
---
