# Wazuh Alert Scripting Example

**Date**: May 2026  
**Category**: Scripting & Automation  
**Related To**: Wazuh SIEM, SOC Automation, Python for Cybersecurity

## Objective
Create a simple Python script to parse and enrich Wazuh alerts, demonstrating automation that can be used in SOC workflows for faster triage and reporting.

## Environment
- **SIEM**: Wazuh (JSON alert export)
- **Language**: Python 3
- **Libraries**: Standard library (json, csv)

## Script Example: Basic Wazuh Alert Parser

```python
import json
import csv
from datetime import datetime

def parse_wazuh_alerts(json_file, output_csv="alert_report.csv"):
    with open(json_file, 'r') as f:
        alerts = json.load(f)
    
    report = []
    for alert in alerts:
        entry = {
            'Timestamp': alert.get('timestamp', 'N/A'),
            'Rule Description': alert.get('rule', {}).get('description', 'N/A'),
            'Severity': alert.get('rule', {}).get('level', 'N/A'),
            'Source IP': alert.get('data', {}).get('srcip', 'N/A'),
            'Agent Name': alert.get('agent', {}).get('name', 'N/A'),
            'Status': 'High' if alert.get('rule', {}).get('level', 0) >= 7 else 'Medium/Low'
        }
        report.append(entry)
    
    # Write to CSV
    with open(output_csv, 'w', newline='') as f:
        writer = csv.DictWriter(f, fieldnames=report[0].keys())
        writer.writeheader()
        writer.writerows(report)
    
    print(f"Report generated with {len(report)} alerts: {output_csv}")

# Usage
if __name__ == "__main__":
    parse_wazuh_alerts('wazuh-alerts.json')

How to Use

Export alerts from Wazuh dashboard or API as JSON.
Run the script: python wazuh-alert-parser.py
Review the generated CSV report for triage.

Screenshots / Evidence
<img src="screenshots/wazuh-json-export.png" alt="Wazuh Alert JSON Export">
<img src="screenshots/python-wazuh-script-run.png" alt="Python Script Execution">
<img src="screenshots/alert-report-csv.png" alt="Generated CSV Report">
Lessons Learned

Scripting turns raw SIEM data into actionable reports.
Filtering by severity helps prioritize real threats.
Easy to extend with email alerts or ticketing integration.

SOC Analyst Relevance

SOC teams automate alert enrichment and reporting to handle volume efficiently.
This type of scripting reduces manual work and improves response time.

Next Steps: Add email notification, integrate with ticket system, or expand to full threat hunting script.

Status: Complete (Example)
Time Spent: ~1 hour

This gives you a practical, ready-to-use scripting example tied to your Wazuh work.
