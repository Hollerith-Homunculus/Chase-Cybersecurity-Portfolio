# Simulated Ransomware Response Exercise

**Date**: May 2026  
**Category**: Incident Response Practice / SOC Tier 2  
**Related To**: Security+ (Incident Response & Recovery), Ransomware Defense

## Objective
Simulate a ransomware attack in the lab, practice containment, recovery, and post-incident steps without paying any ransom.

## Scenario
A Windows endpoint showed encrypted files with ransom note. Wazuh alerted on mass file modifications and suspicious processes.

## Environment
- **Affected Host**: Windows 11 VM (snapshot taken beforehand)
- **Tools**: Wazuh, pfSense, Volatility, Windows Backup, Wireshark

## Response Steps (NIST IR)

### 1. Identification
- Wazuh alert: High volume of file modifications + ransom note creation.
- Confirmed via file extensions changed to .locked or similar.

### 2. Containment (Immediate)
- Isolated the machine (pfSense VLAN or network disable).
- Killed ransomware process via Task Manager / PowerShell.
- Prevented lateral movement by checking other lab machines.

### 3. Analysis
- Memory dump with Volatility → identified ransomware process and C2 connections.
- Reviewed Wazuh logs for initial infection vector (e.g., phishing or RDP).
- Checked backup integrity.

### 4. Eradication
- Removed malware and persistence (registry, scheduled tasks).
- Scanned all systems with updated antivirus.

### 5. Recovery
- Restored files from clean backup/snapshot.
- Changed all passwords and enabled MFA where possible.
- Verified system integrity.

### 6. Lessons Learned & Post-Incident
- Backups are critical — test restores regularly.
- Air-gapped or immutable backups are best defense.
- User training on phishing reduced risk.
- Improved detection rules in Wazuh for file change anomalies.

## Screenshots

![Wazuh Ransomware File Modification Alert](screenshots/ransomware-alert.png)  
![Encrypted Files & Ransom Note](screenshots/ransom-note.png)  
![Volatility Analysis](screenshots/volatility-ransomware.png)  
![Clean Restore Verification](screenshots/restore-success.png)

## Challenges & Solutions
- **Challenge**: Encryption happened quickly → Solution: Fast containment via network isolation.
- **Challenge**: No recent backup → Solution: Used VM snapshot for recovery (real-world lesson on backup hygiene).

## SOC Analyst Relevance
Ransomware is a top threat. This exercise practices:
- Rapid containment to limit damage
- Forensic analysis without disrupting business
- Recovery and communication best practices
- Post-incident improvements to prevention

**Outcome**: Attack contained. Systems restored from backup. No ransom paid. Detection rules strengthened.

---

**Status**: Complete (Simulated)  
**Time Spent**: ~2 hours
