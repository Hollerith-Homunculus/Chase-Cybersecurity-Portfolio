# Incident Response Practice

**Focus:** SOC Tier 1 Alert Triage + Mini-Incident Response Scenarios  
**Status:** In Progress (Foundational Mock Exercises)

## Overview
This folder documents mock alert triage and small-scale incident response exercises using my home lab (Windows, Ubuntu, Wazuh, pfSense, etc.).  

These projects simulate real SOC workflows: detecting, investigating, containing, and documenting security events. They build practical skills in log analysis, tool usage, and structured response while tying into Security+ and CompTIA CySA+ concepts.

**Goal:** Demonstrate SOC readiness through documented triage and response activities.

## Projects

| Date       | Scenario / Exercise                     | Tools Used                     | Status     | Link |
|------------|-----------------------------------------|--------------------------------|------------|------|
| 2026-05-xx | Mock Alert Triage (Wazuh Dashboard)    | Wazuh, Event Viewer            | Complete   | [mock-alert-triage/](./mock-alert-triage/) |
| 2026-05-xx | Simulated Malware Incident Response    | Wireshark, Volatility, PowerShell | In Progress | [malware-incident.md](./malware-incident.md) |
| 2026-05-xx | Phishing / Suspicious Login Investigation | AD Logs, Wireshark           | Planned    | [phishing-investigation.md](./phishing-investigation.md) |
| ...        | ...                                     | ...                            | ...        | ... |

## Environment & Tools
- **Lab**: Windows 11/10 endpoints, Ubuntu (Wazuh), pfSense, Raspberry Pi
- **Core Tools**: Wazuh SIEM, Wireshark, Event Viewer, PowerShell, Volatility
- **Methodology**: Follow NIST IR phases (Preparation, Detection, Analysis, Containment, Eradication, Recovery, Lessons Learned)

## Skills Demonstrated
- Alert triage and prioritization
- Log analysis and correlation
- Containment and basic forensics
- Clear incident documentation
- Use of multiple tools for investigation

## SOC Analyst Relevance
These exercises mirror daily SOC responsibilities:
- Triaging Wazuh/SIEM alerts
- Investigating suspicious activity
- Documenting incidents for handoff or reporting
- Applying structured response frameworks

## Next Steps / Future Improvements
- Add more complex scenarios (ransomware simulation, lateral movement)
- Integrate full Wazuh + pfSense log correlation
- Create a simple IR Playbook markdown
- Simulate chain-of-custody and reporting

---

**Last Updated**: May 2026  
Part of the broader home lab portfolio demonstrating hands-on defensive security skills.
