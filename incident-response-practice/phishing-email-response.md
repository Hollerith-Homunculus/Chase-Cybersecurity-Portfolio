# Phishing Email Investigation & Response

**Date**: May 2026  
**Category**: Incident Response Practice / SOC Tier 1  
**Related To**: Security+ (Threats & Vulnerabilities), User Awareness, Email Security

## Objective
Simulate receipt of a phishing email, investigate indicators of compromise, contain any risk, and document the response.

## Scenario
User reported a suspicious email claiming account suspension with a malicious link. Goal: Analyze without clicking, determine risk, and respond appropriately.

## Environment
- **Tools**: Microsoft Outlook / webmail, VirusTotal, URL scanners, Wazuh (if link was clicked in lab), Wireshark
- **Lab Simulation**: Safe environment with isolated VM

## Investigation Steps

### 1. Initial Triage (Non-Destructive)
- Reviewed email headers for spoofed sender.
- Checked sender domain vs legitimate one.
- Hovered (did not click) links to reveal true destination.
- Scanned attachments/URLs with VirusTotal.

### 2. Technical Analysis
- If link was safely opened in sandbox: Observed redirect and payload attempt.
- Checked for common phishing indicators (urgent language, poor grammar, mismatched URLs).
- Searched Wazuh / endpoint logs for any related activity.

### 3. Containment
- Blocked the malicious domain in pfSense.
- Advised user to change password and enable MFA.
- Scanned affected system.

### 4. Eradication & Recovery
- Removed any downloaded files.
- Educated user on reporting suspicious emails.

### 5. Reporting & Lessons
- Documented indicators for future detection rules.
- Recommended domain-wide phishing awareness training.

## Screenshots

![Suspicious Email Headers](screenshots/phishing-headers.png)  
![VirusTotal URL Scan](screenshots/virustotal-result.png)  
![Wireshark if Link Clicked](screenshots/phishing-traffic.png)  
![User Notification Example](screenshots/user-advisory.png)

## Challenges & Solutions
- **Challenge**: User almost clicked link → Solution: Emphasized "hover don't click" rule and reporting process.
- **Challenge**: Obfuscated URL → Solution: Used URL decoding tools and sandbox analysis.

## Lessons Learned
- Human element is the weakest link — training and quick reporting are critical.
- Header analysis and URL inspection prevent most phishing success.
- Fast containment limits damage.

## SOC Analyst Relevance
Phishing is one of the most common initial access vectors. This exercise practices:
- Rapid email triage
- Indicator extraction for blocking
- User communication
- Integration with SIEM for broader detection

**Outcome**: Phishing attempt identified and neutralized before compromise. User educated.

---

**Status**: Complete (Simulated)  
**Time Spent**: ~1 hour
