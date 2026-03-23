# HTB Starting Point Track

**Focus:** Beginner Penetration Testing & Attack Simulation Practice

## Overview
This subfolder documents my progress and write-ups for Hack The Box **Starting Point** machines — guided, beginner-level challenges designed to teach core pentesting skills.  
Each machine simulates real-world vulnerabilities (e.g., weak services, misconfigurations, privilege escalation) in a safe, legal environment.

Goal: Build foundational offensive skills (enumeration, exploitation, post-exploitation) while learning how attackers think — directly relevant to Security+ (vulnerability identification, threat vectors) and Junior SOC Analyst roles (recognizing indicators of compromise, understanding attack chains).

## Environment & Tools
- Platform: Hack The Box (app.hackthebox.com) – Starting Point track
- Access: Free account (no VIP required)
- Local setup: Kali Linux VM in VirtualBox (for tools), or browser-based Pwnbox
- Tools used: nmap, gobuster, enum4linux, smbclient, Metasploit (msfconsole), netcat, Hydra, basic scripts
- Machines completed (as of March 2026): [List them here, e.g., Meow, Fawn, Dancing, etc.]

## Completed Machines & Highlights
(Add one section per machine as you finish — keep them short and factual)

### Meow (Linux – Very Easy)
- Difficulty: Very Easy
- Key skills: Basic enumeration, SSH brute-force, privilege escalation via misconfigured service.
- Steps summary:
  1. Nmap scan: `nmap -sC -sV -p- 10.10.11.x`
  2. Found open SSH (22) and Telnet-like service.
  3. Brute-forced weak credentials with Hydra.
  4. Privilege escalation via sudo misconfiguration.
- Security lesson: Weak/default credentials are a common entry point (Security+ domain: threats & vulnerabilities).

### Fawn (Linux – Easy)
- Difficulty: Easy
- Key skills: FTP enumeration, anonymous login, file transfer, basic reverse shell.
- Steps summary:
  1. Nmap → Open FTP (21).
  2. Anonymous login → Downloaded sensitive file.
  3. Used file contents to gain initial access.
  4. Escalated via SUID binary.
- Lesson: Misconfigured file shares expose sensitive data — relevant to access control policies.

(Add more machines as completed: e.g., Dancing, Archetype, etc. Include one short write-up per machine.)

## Step-by-Step Summary (Example: Generic Starting Point Machine)
1. Initial reconnaissance: Full port scan with nmap (`-sC -sV -p-`).
2. Enumerated services (HTTP, SMB, FTP, SSH).
3. Gained foothold (e.g., weak creds, anonymous access, web vuln).
4. Privilege escalation (SUID, sudo rights, kernel exploit).
5. Proof: Captured flag.txt or system access.
6. Cleaned up: Documented indicators for blue-team perspective.

## Screenshots / Evidence
![Nmap Scan Results](./screenshots/meow-nmap.png)  
![Foothold via FTP](./screenshots/fawn-ftp-anon.png)  
![Privilege Escalation Proof](./screenshots/meow-root-shell.png)  

(Add your actual screenshots here after uploading to a `screenshots/` subfolder inside starting-point/)

## Key Outcomes & Lessons
- Completed X Starting Point machines — built confidence in enumeration and exploitation basics.
- Learned attacker mindset: How common misconfigurations lead to compromise (e.g., open ports, weak auth).
- Demonstrates analytical process: Scan → Enumerate → Exploit → Escalate — transferable to SOC alert triage (spotting IOCs) and Help Desk (understanding why systems break).

## Skills Demonstrated
- **Technical:** Nmap scanning, service enumeration, credential testing, basic exploitation, Linux/Windows internals
- **Security:** Vulnerability identification, privilege escalation techniques, understanding attack vectors
- **Help Desk / SOC:** Systematic problem-solving, documentation of steps/findings, ability to think like both attacker and defender

## Next Steps / Future Improvements
- Complete remaining Starting Point machines.
- Write full detailed write-ups with commands and screenshots for each.
- Map techniques to MITRE ATT&CK framework (e.g., T1078 Valid Accounts).
- Simulate blue-team response: "How would I detect/prevent this attack in a real environment?"
- Add PowerShell or Bash scripts for automation (e.g., basic recon script).

This subfolder is part of my deliberate practice to transition into IT Help Desk / Junior SOC Analyst roles in the Tampa Bay area.
