# Basic Memory Forensics with Volatility

**Date**: May 2026  
**Category**: Incident Response Practice / Forensics  
**Related To**: Security+ (Forensics & Incident Response), CompTIA CySA+

## Objective
Perform basic memory forensics on a potentially compromised Windows system using Volatility to identify malicious processes, network connections, and artifacts.

## Environment
- **Target**: Windows 11 VM with simulated malware
- **Tool**: Volatility 3 (standalone or via Python)
- **Memory Dump**: Acquired with tools like DumpIt or WinPMEM (lab safe method)

## Step-by-Step Process

### 1. Acquire Memory Dump
- Run memory acquisition tool on the "compromised" VM.
- Save as `.raw` or `.mem` file.

### 2. Identify Profile / Image Info
```bash
vol.py -f memory.dump windows.info

3. Key Volatility Commands Used
# List processes
vol.py -f memory.dump windows.pslist

# Network connections
vol.py -f memory.dump windows.netscan

# DLLs and injected code
vol.py -f memory.dump windows.dlllist

# Scan for malware signatures / hidden processes
vol.py -f memory.dump windows.psscan
vol.py -f memory.dump windows.malfind

4. Analysis & Findings

Identified suspicious process (e.g., svchost.exe with unusual parent or high memory).
Found anomalous network connections to external IPs.
Detected injected code or hollowed processes.

5. Documentation & Remediation

Noted IOCs (Indicators of Compromise).
Recommended full disk imaging and rebuild if needed.

Screenshots
<img src="screenshots/volatility-pslist.png" alt="Volatility PSList Output">
<img src="screenshots/volatility-netscan.png" alt="Netscan Suspicious Connections">
<img src="screenshots/volatility-malfind.png" alt="Malfind Injected Code">
<img src="screenshots/process-tree.png" alt="Process Tree Analysis">
Challenges & Solutions

Challenge: Wrong profile → Solution: Used windows.info to identify correct Windows version.
Challenge: Large memory dump → Solution: Focused on high-value plugins first (pslist, netscan).

Lessons Learned

Memory forensics captures volatile data that disk forensics misses.
Combining Volatility with Wazuh/SIEM and Wireshark gives a complete picture.
Practice on known samples builds speed for real incidents.

SOC Analyst Relevance
Memory forensics is a valuable skill for deeper investigation of alerts. It helps confirm malware presence, understand attacker techniques, and support forensic reporting.
Outcome: Malicious process identified and IOCs documented for blocking and future detection.

Status: Complete (Basic)
Time Spent: ~1.5–2 hours

