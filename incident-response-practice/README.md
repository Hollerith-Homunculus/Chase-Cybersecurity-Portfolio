# Incident Response Practice

**Focus:** SOC Tier 1 Alert Triage + Practical Incident Response Exercises  
**Status:** In Progress (Strong Foundational Coverage)

## Overview
This section documents mock alert triage, mini-incident simulations, and response exercises using my home lab environment (Wazuh SIEM, pfSense, Windows/Linux endpoints, Volatility, etc.).

The projects simulate real SOC workflows — from alert detection to containment, eradication, recovery, and lessons learned — while building skills directly relevant to junior SOC Analyst and help desk roles.

**Goal:** Demonstrate structured, tool-driven incident handling and clear documentation for escalation or client reporting.

## Projects

| Date       | Exercise / Scenario                        | Key Tools                     | Status     | Link |
|------------|--------------------------------------------|-------------------------------|------------|------|
| 2026-05-xx | Wazuh Alert Triage Example                 | Wazuh, Event Viewer           | Complete   | [mock-alert-triage/Wazuh-Alert-Triage-Example-1.md](./mock-alert-triage/Wazuh-Alert-Triage-Example-1.md) |
| 2026-05-xx | False Positive vs True Positive            | Wazuh, Wireshark              | Complete   | [false-positive-vs-true-positive.md](./false-positive-vs-true-positive.md) |
| 2026-05-xx | Suspicious Login Investigation             | AD Logs, Wazuh, Event Viewer  | Complete   | [suspicious-login-investigation.md](./suspicious-login-investigation.md) |
| 2026-05-xx | Simulated Malware Incident Response        | Wazuh, Wireshark, Volatility  | Complete   | [malware-incident-response.md](./malware-incident-response.md) |
| 2026-05-xx | Phishing Email Investigation               | Headers, VirusTotal, Wazuh    | Complete   | [phishing-investigation.md](./phishing-investigation.md) |
| 2026-05-xx | Simulated Ransomware Response              | Wazuh, pfSense, Snapshots     | Complete   | [ransomware-simulation-response.md](./ransomware-simulation-response.md) |
| 2026-05-xx | Basic Memory Forensics with Volatility     | Volatility                    | Complete   | [basic-forensics-volatility.md](./basic-forensics-volatility.md) |
| 2026-05-xx | Incident Escalation & Reporting            | Documentation Templates       | Complete   | [ir-escalation-reporting.md](./ir-escalation-reporting.md) |

## Supporting Documents
- [IR Playbook Template](./IR-Playbook-Template.md)
- [Incident Response Checklist](./Incident-Response-Checklist.md)

## Environment & Tools
- **SIEM**: Wazuh on Ubuntu
- **Network Security**: pfSense firewall + VLANs
- **Analysis**: Wireshark, Volatility, Event Viewer, PowerShell
- **Lab Setup**: Windows 11/10, Ubuntu, isolated segments

## Skills Demonstrated
- Rapid alert triage and prioritization
- Structured incident response (NIST-based)
- Log correlation and tool integration
- Clear documentation and escalation
- Distinguishing noise from real threats

## SOC Analyst Relevance
These exercises mirror daily SOC responsibilities:
- Triaging SIEM alerts
- Investigating suspicious activity
- Containing threats quickly
- Documenting for handoff and lessons learned

Strong foundation for CompTIA CySA+ and real-world SOC work.

## Next Steps / Future Enhancements
- More complex scenarios (lateral movement, data exfiltration)
- Full Wazuh + pfSense log correlation
- Live ticketing integration with CoolUnderFire LLC
- Purple team exercises (attack + defense)

---

**Last Updated**: May 2026  
Part of the broader home lab portfolio showcasing defensive security and SOC readiness. See main portfolio README for links to AD, networking, SIEM setup, HTB/TryHackMe, and other sections.
