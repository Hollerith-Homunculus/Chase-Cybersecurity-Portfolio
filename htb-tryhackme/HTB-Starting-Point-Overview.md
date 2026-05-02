# HTB Starting Point - [Machine Name] Write-Up

**Date**: May 2026  
**Platform**: Hack The Box – Starting Point Track  
**Difficulty**: Easy  
**Category**: [e.g., Web, Windows, Linux, Crypto]

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
