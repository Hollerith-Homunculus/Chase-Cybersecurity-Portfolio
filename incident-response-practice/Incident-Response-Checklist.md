# Incident Response Checklist

**Date**: May 2026  
**Category**: Incident Response Practice  
**Purpose**: Quick, actionable checklist for use during mock incidents, lab exercises, or real CoolUnderFire support cases.

## 1. Preparation (Before Starting)
- [ ] Confirm tools are ready (Wazuh, Wireshark, Volatility, backups, snapshots)
- [ ] Note current time and start documenting
- [ ] Identify affected system(s) and isolate if possible

## 2. Identification / Detection
- [ ] Review Wazuh / SIEM alerts
- [ ] Check endpoint logs (Event Viewer)
- [ ] Capture network traffic if relevant (Wireshark)
- [ ] Determine scope and severity

## 3. Containment
- [ ] Isolate the system (pfSense rule, VLAN, or disconnect)
- [ ] Preserve volatile data (memory dump)
- [ ] Block malicious indicators (IPs, domains)
- [ ] Prevent lateral movement

## 4. Analysis & Eradication
- [ ] Perform memory forensics (Volatility)
- [ ] Analyze processes, network connections, and files
- [ ] Identify root cause and IOCs
- [ ] Remove malware and persistence mechanisms
- [ ] Reset compromised credentials

## 5. Recovery
- [ ] Restore from clean backup or snapshot
- [ ] Apply patches and updates
- [ ] Verify system is clean (full scan)
- [ ] Monitor for re-infection (24–48 hours)

## 6. Lessons Learned & Reporting
- [ ] Document timeline, actions, and decisions
- [ ] Update detection rules and playbooks
- [ ] Provide client/user recommendations
- [ ] Conduct after-action review

## Quick Tool Reference
- **SIEM/Alerts**: Wazuh Dashboard
- **Network**: Wireshark + pfSense logs
- **Memory**: Volatility (pslist, netscan, malfind)
- **Windows**: Event Viewer, PowerShell, Process Explorer
- **Documentation**: This checklist + ticket template

## SOC / Help Desk Notes
- Prioritize containment to limit damage.
- Document everything — timestamps matter.
- Escalate early if scope is large or data is involved.
- Focus on clear communication with non-technical users.

---

**Last Updated**: May 2026  
Print or keep open during exercises. Customize as you gain more experience.
