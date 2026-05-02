# Wazuh SIEM Server + Agent Deployment

**Date**: May 2, 2026  
**Category**: Home Lab / SOC Monitoring & Detection  
**Related To**: Security+ (Domain 4: Security Operations), SOC Analyst fundamentals (log ingestion, alert triage, SIEM)

## Objective
Deploy a functional open-source SIEM (Wazuh) to centralize logs from multiple Windows endpoints and a Linux server. This creates a realistic small-scale SOC monitoring environment for practicing alert review, threat detection, and basic incident response.

## Environment
- **Wazuh Server**: Ubuntu desktop (main lab server)
- **Agents**:
  - 2× Windows 11 laptops
  - 2× Windows 10 laptops
  - Raspberry Pi (Linux agent)
- **Additional Tools**: Web browser for Wazuh dashboard, optional pfSense for network segmentation
- **Isolation**: All machines on isolated lab network (no production data)

## Step-by-Step Process

### 1. Install Wazuh All-in-One Deployment (on Ubuntu)
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Download and run Wazuh all-in-one installer (as of 2026, check latest at packages.wazuh.com)
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh && bash wazuh-install.sh -a
After installation, note the generated password for the admin user.
**### 2. Access the Wazuh Dashboard**

Open browser on any lab machine → https://<Ubuntu-IP>:5601
Login: admin / [password shown during install]
Change the default password on first login.

3. Add Windows Agents
On each Windows machine:

Download the Wazuh agent MSI from the Wazuh dashboard (Agents → Deploy new agent).
Install the agent (run as Administrator).
During installation, enter the Wazuh server IP and enrollment key (shown in dashboard).
Restart the Wazuh agent service.

PowerShell command (alternative method):
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/wazuh-agent-4.x.msi -OutFile wazuh-agent.msi
msiexec.exe /i wazuh-agent.msi /q WAZUH_MANAGER="<Ubuntu-IP>" WAZUH_REGISTRATION_SERVER="<Ubuntu-IP>"

5. Configure Basic Log Collection

In Wazuh dashboard: Agents → Select agent → Configuration
Enable Sysmon (highly recommended for Windows) via group configuration.
Add custom decoders/rules if needed for specific monitoring.

6. Verify Data Flow

Go to Security Events or Overview in dashboard.
Generate test activity (e.g., failed logins, run whoami in cmd, browse suspicious sites in isolated VM).

Challenges & Solutions

Challenge: Agent enrollment failed on Windows → Solution: Verified firewall allowed port 1514/1515 (UDP/TCP) and used correct server IP + enrollment key.
Challenge: No data appearing in dashboard → Solution: Restarted Wazuh services (sudo systemctl restart wazuh-manager) and checked agent status.
Challenge: High resource usage on Raspberry Pi → Solution: Reduced scan frequency in agent config.

Lessons Learned

Centralized logging with Wazuh makes detection much faster than checking individual machines.
Proper agent enrollment and configuration is critical — small mistakes (wrong IP/key) break visibility.
Sysmon + Wazuh provides rich telemetry for threat hunting.
This setup directly supports real-world SOC tasks like monitoring multiple endpoints and prioritizing alerts.

SOC Analyst Relevance
This project demonstrates core junior SOC skills:

Deploying and maintaining a SIEM platform
Onboarding endpoints across OS types
Understanding log flow and basic alert triage
Building a foundation for incident detection and response workflows

Next Steps:

Enable Sysmon and create custom detection rules.
Simulate a malware incident and document full response.
Integrate with other tools (e.g., Wireshark captures).

Status: Complete (Initial Deployment)
Time Spent: ~2–3 hours
Files/Configs: See wazuh-config/ folder (if you upload any custom YAML files)
Ties to Certifications: Reinforces Security+ monitoring and operations domains. Excellent foundation for CySA+ and real SOC work at CoolUnderFire Cybersecurity LLC.
