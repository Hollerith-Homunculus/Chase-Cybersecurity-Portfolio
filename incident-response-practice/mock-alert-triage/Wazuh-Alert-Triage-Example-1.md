# Mock Alert Triage - Wazuh Dashboard Example 1

**Date**: May 2026  
**Category**: Incident Response Practice / SOC Tier 1  
**Related To**: Security+ (Monitoring & Detection), CompTIA CySA+

## Objective
Triage and investigate a sample alert from Wazuh SIEM. Determine if it is a true positive, false positive, or requires escalation, and document the full process.

## Environment
- **SIEM**: Wazuh on Ubuntu desktop
- **Endpoints**: Windows 11/10 laptops
- **Tools**: Wazuh dashboard, Event Viewer, Wireshark, PowerShell

## Alert Details
- **Alert Type**: Multiple failed logins / Potential brute force
- **Source**: Windows 11 client (IP 192.168.10.50)
- **Severity**: Medium
- **Rule**: Wazuh rule for authentication failures

## Triage Steps (NIST-inspired)

1. **Detection**  
   Alert appeared in Wazuh dashboard under Security Events.

2. **Initial Analysis**  
   - Reviewed alert details and correlated logs.
   - Checked source IP (internal lab machine).
   - Examined Windows Security Event Logs for Event ID 4625 (failed logon).

3. **Investigation**  
   - Ran `net user` and reviewed recent logons.
   - Used Wireshark to capture traffic from the endpoint (no suspicious outbound).
   - Confirmed it was a user typing the wrong password (lab testing).

4. **Containment / Remediation**  
   - No containment needed (false positive).
   - Advised user on password practices.

5. **Eradication & Recovery**  
   - N/A (false positive).

6. **Lessons Learned**  
   - Correlating SIEM alerts with endpoint logs is critical to avoid alert fatigue.

## Screenshots

![Wazuh Alert in Dashboard](screenshots/wazuh-bruteforce-alert.png)  
![Windows Event ID 4625](screenshots/event-id-4625.png)  
![Wireshark Capture During Alert](screenshots/wireshark-during-alert.png)  
![Resolution Notes](screenshots/triage-resolution.png)

## Challenges & Solutions
- **Challenge**: High volume of similar alerts → Solution: Tuned Wazuh rules for lab environment and created filters.
- **Challenge**: Limited context in raw alert → Solution: Pivoted to endpoint logs and packet captures.

## SOC Analyst Relevance
This simulates daily Tier 1 work: prioritizing alerts, reducing false positives, and clear documentation for escalation or handoff.

**Outcome**: Classified as false positive. No further action required.

---

**Status**: Complete  
**Time Spent**: ~45 minutes
