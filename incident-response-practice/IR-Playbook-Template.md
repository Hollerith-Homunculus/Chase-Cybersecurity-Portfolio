# Incident Response Playbook Template

**Date**: May 2026  
**Category**: Incident Response Practice  
**Purpose**: Reusable framework for consistent, effective response to security incidents in the home lab and CoolUnderFire support work.

## Core Framework (NIST / SANS Inspired)

### 1. Preparation (Before Incidents)
- Maintain updated toolkits (Wazuh, Wireshark, Volatility, backups, snapshots).
- Define roles, escalation paths, and contact list.
- Keep asset inventory and baseline configurations.
- Regular backup testing and patching.

### 2. Identification / Detection
- Monitor Wazuh dashboard and alerts.
- Correlate logs from endpoints, firewall (pfSense), and network.
- Use tools: Event Viewer, Wireshark, Volatility.
- Determine scope, severity, and type (malware, phishing, brute force, etc.).

### 3. Containment
- **Short-term**: Isolate affected system (pfSense VLAN rule, disable network, or snapshot).
- Preserve volatile evidence (memory dump).
- Block malicious IPs/domains at firewall level.

### 4. Analysis / Eradication
- Identify root cause and IOCs (Indicators of Compromise).
- Remove malware/persistence (Volatility, PowerShell, antivirus).
- Reset credentials and review permissions.

### 5. Recovery
- Restore from clean backup or snapshot.
- Monitor for re-infection (enhanced Wazuh rules).
- Test system functionality and return to normal operations.

### 6. Lessons Learned & Post-Incident
- Conduct review: What worked? What failed?
- Update detection rules, policies, and playbooks.
- Document for portfolio, client report, or management.
- Recommend preventive controls (training, patching, MFA, segmentation).

## Common Incident Playbooks (Quick Reference)

**Phishing / Social Engineering**
- Do not click links → Analyze headers and URLs safely.
- Scan with VirusTotal.
- Advise password change + MFA.

**Malware / Ransomware**
- Immediate isolation.
- Memory forensics with Volatility.
- Restore from backup — never pay ransom.

**Brute Force / Compromised Account**
- Check AD logs and Wazuh.
- Force password reset and review group memberships.
- Enable account lockout policies.

**Data Exfiltration or C2 Communication**
- Analyze Wireshark captures.
- Block C2 IPs/domains.
- Full forensic review.

**Denial of Service / Flood**
- Use pfSense rate limiting and firewall rules.
- Monitor traffic patterns.

## Tools Quick Reference
- **Detection**: Wazuh SIEM
- **Network**: Wireshark, nmap, pfSense logs
- **Memory/Forensics**: Volatility
- **Windows**: Event Viewer, Process Explorer, PowerShell
- **Containment**: pfSense VLANs/firewall, VM snapshots

## Documentation & Communication Tips
- Use the CoolUnderFire ticket template for every incident.
- Include timeline, actions, decisions, and evidence.
- Tailor communication: Technical for SOC team, plain language for clients.
- Always follow "need-to-know" for sensitive details.

## Customization Note
Adapt and expand this playbook as you complete more scenarios. Add new playbooks for emerging threats.

---

**Last Updated**: May 2026  
Living document — update after every major exercise or real support ticket.
