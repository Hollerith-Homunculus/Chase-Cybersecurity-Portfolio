# False Positive vs True Positive Alert Triage

**Date**: May 2026  
**Category**: Incident Response Practice / SOC Tier 1  
**Related To**: Security+ (Monitoring & Analysis), Alert Fatigue Reduction

## Objective
Compare and contrast a false positive and a true positive alert in Wazuh, demonstrating how to differentiate them and reduce noise in a SOC environment.

## Environment
- **SIEM**: Wazuh on Ubuntu
- **Endpoints**: Windows 11 lab machines
- **Tools**: Wazuh dashboard, Event Viewer, Wireshark

## Scenario 1: False Positive
- **Alert**: Multiple failed logins on a domain account.
- **Investigation**:
  - Source IP = internal trusted machine.
  - User confirmed typing wrong password after vacation.
  - No unusual processes or network activity.
- **Classification**: False Positive (benign user error).
- **Action**: Educated user + tuned rule sensitivity.

## Scenario 2: True Positive
- **Alert**: Failed logins followed by successful login from unusual IP + suspicious process start.
- **Investigation**:
  - Source IP external or unexpected.
  - Volatility showed anomalous process.
  - Wireshark showed C2-like traffic.
- **Classification**: True Positive (potential compromise).
- **Action**: Isolated system, password reset, full scan, and escalation.

## Key Differentiation Techniques
- Source IP reputation and geolocation
- Correlation with endpoint logs and behavior
- Time of day and user patterns
- Presence of additional IOCs (malware, exfil)

## Screenshots

![False Positive Alert Details](screenshots/false-positive-alert.png)  
![True Positive with Malicious Process](screenshots/true-positive-alert.png)  
![Wireshark Comparison](screenshots/traffic-comparison.png)  
![Triage Decision Notes](screenshots/triage-decision.png)

## Lessons Learned
- Alert volume can cause fatigue — proper tuning and correlation are essential.
- Context is everything: one alert alone is rarely conclusive.
- Documenting false positives helps improve future detection rules.

## SOC Analyst Relevance
Distinguishing false positives from real threats is a daily SOC skill that directly impacts efficiency and security. This exercise shows structured analysis and decision-making under realistic conditions.

**Outcome**: Improved ability to prioritize alerts and reduce noise while catching genuine threats.

---

**Status**: Complete  
**Time Spent**: ~1 hour
