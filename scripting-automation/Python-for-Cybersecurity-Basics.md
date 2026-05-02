# Python for Cybersecurity Basics

**Date**: May 2026  
**Category**: Scripting & Automation  
**Related To**: *Python for Cybersecurity* book, SOC Automation, Log Analysis

## Objective
Build foundational Python skills for cybersecurity tasks such as log parsing, basic network scripting, and automation.

## Environment
- **OS**: Ubuntu desktop or Windows with Python installed
- **Libraries**: Standard library + `requests`, `scapy` (optional), `pandas` for log analysis

## Key Scripts & Examples

### 1. Simple Log Parser
```python
with open('auth.log', 'r') as f:
    for line in f:
        if 'Failed password' in line:
            print(f"Failed login attempt: {line.strip()}")

2. Basic Port Scanner
Python
import socket

target = "192.168.1.100"
for port in range(1, 100):
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(1)
    result = sock.connect_ex((target, port))
    if result == 0:
        print(f"Port {port} is open")
    sock.close()

3. Wazuh / Log Analysis Example
Python
import json

with open('wazuh-alerts.json') as f:
    alerts = json.load(f)
    for alert in alerts:
        if alert.get('rule', {}).get('level', 0) >= 7:
            print(f"High severity alert: {alert.get('rule', {}).get('description')}")

Screenshots / Evidence
<img src="screenshots/python-log-parser.png" alt="Python Log Parser Output">
<img src="screenshots/python-port-scanner.png" alt="Port Scanner Results">
<img src="screenshots/python-cyber-script.png" alt="Simple Script Execution">
Lessons Learned

Python is excellent for quick automation and data analysis in cybersecurity.
Start simple — standard library is often sufficient.
Combine with tools like Wazuh for powerful log processing.

SOC Analyst Relevance

SOC analysts use Python for alert enrichment, custom scripts, and reporting.
Understanding scripting helps detect malicious Python/PowerShell code.

Next Steps: Expand to full Wazuh alert parser, network scanner with Scapy, and integration with ticketing.

Status: Complete (Basics)
Time Spent: ~1–1.5 hours
