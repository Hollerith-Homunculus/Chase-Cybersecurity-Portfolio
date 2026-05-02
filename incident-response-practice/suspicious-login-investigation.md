# Suspicious Login Investigation

**Date**: May 2026  
**Category**: Incident Response Practice / SOC Tier 1  
**Related To**: Security+ (Access Control & Monitoring), AD Log Analysis

## Objective
Investigate a suspicious login alert, determine if it is legitimate or malicious, and respond appropriately.

## Scenario
Wazuh alert triggered for multiple failed logins followed by a successful login from an unusual location or time on a domain-joined Windows machine.

## Environment
- **Domain**: lab.local
- **Tools**: Wazuh SIEM, Active Directory logs, Event Viewer (Event ID 4624/4625), PowerShell, Wireshark

## Investigation Steps

### 1. Alert Triage
- Reviewed Wazuh alert details (source IP, username, timestamp).
- Correlated with Windows Security Event Logs.

### 2. Key Checks Performed
- Verified source IP (internal vs external).
- Checked user account history and group memberships.
- Reviewed recent AD changes.
- Used `Get-ADUser` and Event Viewer for logon details.
- Captured network traffic if remote access was involved.

### 3. Findings
- Determined it was [example: legitimate user traveling OR simulated brute force followed by successful credential use].
- No evidence of compromise (or confirmed compromise and escalated).

### 4. Response Actions
- Forced password reset if suspicious.
- Reviewed and tightened account lockout policies.
- Added monitoring rules for future similar alerts.

## Screenshots

![Wazuh Suspicious Login Alert](screenshots/suspicious-login-alert.png)  
![Windows Event ID 4624 Successful Logon](screenshots/event-4624.png)  
![AD User Properties](screenshots/ad-user-properties.png)  
![Investigation Notes](screenshots/login-investigation-summary.png)

## Challenges & Solutions
- **Challenge**: High noise from normal failed logins → Solution: Tuned Wazuh rules for geography/time-based anomalies.
- **Challenge**: Distinguishing legitimate vs malicious → Solution: Correlated with user behavior and IP reputation.

## Lessons Learned
- Baseline normal login patterns are essential for spotting anomalies.
- Multi-factor authentication (MFA) would prevent most unauthorized access.
- Fast investigation limits potential damage from compromised credentials.

## SOC Analyst Relevance
Suspicious logins are among the most common alerts in SOC environments. This exercise practices:
- Rapid log correlation
- Distinguishing noise from real threats
- Appropriate escalation and remediation

**Outcome**: Login activity classified and remediated. Enhanced monitoring rules implemented.

---

**Status**: Complete (Simulated)  
**Time Spent**: ~1 hour
