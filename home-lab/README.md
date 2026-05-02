# Home Lab Projects

This folder documents my hands-on home lab environment and SOC-focused projects. The lab simulates a small enterprise environment for practicing monitoring, log analysis, incident response, and defensive security operations.

**Lab Hardware Overview** (as of May 2026):
- **Endpoints**: 2× Windows 11 laptops, 2× Windows 10 laptops, MacBook Air
- **Servers/SIEM**: Ubuntu desktop (primary server), Raspberry Pi
- **Networking/Security Tools**: pfSense (firewall), Wazuh (XDR/SIEM), Wireshark, nmap, Volatility
- **Purpose**: Practice real SOC Analyst workflows — log ingestion, alert triage, threat detection, incident response, and basic hardening.

## Projects

| Date       | Project Name                          | Key Skills Demonstrated                          | Status     | Link |
|------------|---------------------------------------|--------------------------------------------------|------------|------|
| 2026-04-xx | Wazuh SIEM Server + Agent Deployment | SIEM setup, log collection, dashboard monitoring | Complete   | [Wazuh-Setup.md](./Wazuh-Setup.md) |
| 2026-05-xx | Windows Event Log Analysis & Sysmon   | Threat hunting, log parsing with Wazuh           | In Progress| [Windows-Logging.md](./Windows-Logging.md) |
| ...        | ...                                   | ...                                              | ...        | ... |


## Lab Architecture Summary
- **Central SIEM**: Wazuh on Ubuntu desktop ingesting logs from all Windows machines and Raspberry Pi.
- **Monitoring Focus**: Windows Security Events, Sysmon, file integrity, network traffic.
- **Incident Simulation**: Malware execution, brute-force attempts, lateral movement practice.
- **Defensive Tools**: pfSense firewall rules, basic EDR-like capabilities with Wazuh.

## SOC Analyst Relevance
These projects directly support junior SOC roles by demonstrating:
- Ability to deploy and maintain monitoring tools
- Log analysis and alert triage
- Incident response process (detection → investigation → documentation)
- Integration of multiple OS environments (Windows, Linux)
- Practical application of Security+ concepts (monitoring, vulnerabilities, incident response)

All projects include:
- Step-by-step setup commands
- Screenshots of dashboards/alerts
- Challenges encountered and solutions
- Lessons learned and ties to certifications/policy

## Tools Used (from my resource list)
- Wazuh (primary SIEM/XDR)
- Wireshark, nmap
- Volatility (memory forensics)
- Portainer (Docker management)
- Python scripting for log parsing (see *Python for Cybersecurity* book)

---

**Last Updated**: May 2026  
**Goal**: 8–12 well-documented projects by graduation (August 2026) to show employers I can operate in a real SOC environment.

See the main repo README for overall portfolio and links to HTB / TryHackMe / CoolUnderFire Cybersecurity LLC.
