Task 1: Scan Your Local Network for Open Ports
The objective is to perform network reconnaissance on a local network to identify open ports on devices. This process helps understand network service exposure and related cybersecurity risks.

--> Tools Used
Nmap: Core tool for port scanning and OS detection

arp-scan: Used for discovering live hosts on the network

Wireshark: Optional, for analyzing network traffic during scans

ping: To verify basic connectivity

--> Task Steps & Process
Identified local IP and subnet with ifconfig (example: 192.168.119.129)

Discovered active hosts via arp-scan (including VMware virtual machines)

Scanned hosts with Nmap (TCP SYN scan, OS detection):

bash
sudo nmap -sS -O <target-ip>
Documented findings in text files (e.g., os_report.txt)

Observed packet data with Wireshark

-->Key Findings & Analysis
Host 192.168.119.2: Open port 53/tcp (DNS service)

Host 192.168.119.1: Open ports 135/tcp (MSRPC), 445/tcp (SMB)

 --->Security Risks Identified
Open Port 53 (DNS): Risk of DNS tunneling, DDoS amplification

Open Ports 135 (MSRPC) & 445 (SMB): Targeted by malware and ransomware (such as WannaCry), and potential for lateral movement or remote code execution by attackers
