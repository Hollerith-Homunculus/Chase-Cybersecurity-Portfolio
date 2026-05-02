# HTB Starting Point - [Machine Name] Write-Up

**Date**: May 2026  
**Platform**: Hack The Box – Starting Point Track  
**Difficulty**: Easy  
**Category**: [e.g., Web, Windows, Linux, Crypto]
This template is ready to duplicate for each HTB/THM machine or room you complete.
## Objective
Complete the [Machine Name] machine, documenting enumeration, exploitation, and post-exploitation steps. Focus on defensive takeaways for SOC analysis.

## Environment
- **Target IP**: [redacted or lab IP]
- **Tools**: nmap, Gobuster, Metasploit (where appropriate), LinPEAS/WinPEAS, manual enumeration
- **Methodology**: OSCP-style — enumerate → foothold → privilege escalation → proof

## Step-by-Step Walkthrough

### 1. Enumeration
- Nmap scan:
  ```bash
  nmap -sC -sV -oN nmap.txt [target]

Key findings: [e.g., Open ports 80 (HTTP), 22 (SSH), etc.]
Web enumeration with Gobuster → discovered directories/files.

2. Foothold / Initial Access

Vulnerability exploited: [e.g., SQL injection, weak credentials, known CVE]
Commands used and screenshots of success.

3. Privilege Escalation

Enumeration scripts (LinPEAS/WinPEAS)
Method used: [e.g., Kernel exploit, misconfigured service, password reuse]
Proof of root/system access.

4. Post-Exploitation & Proof

Flags captured (user.txt, root.txt)
Persistence or cleanup notes (for learning purposes).

Screenshots
<img src="screenshots/nmap-scan.png" alt="Nmap Scan Results">
<img src="screenshots/foothold.png" alt="Initial Foothold">
<img src="screenshots/privesc.png" alt="Privilege Escalation">
<img src="screenshots/root-flag.png" alt="Root Flag">
Defensive / SOC Takeaways

This vulnerability highlights the importance of [e.g., input sanitization, patch management, strong credentials].
Detection opportunities: Unusual processes, failed logins, file modifications (Wazuh rules).
Prevention: Regular vulnerability scanning, least privilege, monitoring.

Lessons Learned

Thorough enumeration is 80% of success.
Always think about detection and prevention angles for SOC mindset.


Status: Complete
Time Spent: ~X hours
Machine Rank: [Easy/Medium]
Skills Practiced: Enumeration, exploitation, post-exploitation, defensive analysis.


