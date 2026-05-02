# Home Lab Risk Register Example

**Date**: May 2026  
**Category**: Risk & Compliance  
**Related To**: Master's Cybersecurity Management & Policy, NIST Risk Management, SOC Risk Prioritization

## Overview
This risk register documents key risks in my home lab environment, their assessed levels, and current controls. It serves as a living document for ongoing risk management practice.

## Risk Register

| Risk ID | Risk Description                          | Asset Affected              | Likelihood | Impact | Risk Score | Owner      | Current Controls                          | Residual Risk | Status    | Last Reviewed |
|---------|-------------------------------------------|-----------------------------|------------|--------|------------|------------|-------------------------------------------|---------------|-----------|---------------|
| R-01    | Weak or compromised AD credentials        | Domain Controller, Clients  | Medium     | High   | High       | Chase      | GPO password policy, account lockout      | Medium        | Monitored | May 2026     |
| R-02    | Unpatched vulnerabilities on endpoints    | Windows laptops, Ubuntu     | High       | High   | Critical   | Chase      | Manual patching schedule, snapshots       | Medium        | Active    | May 2026     |
| R-03    | Unauthorized network access / lateral movement | Entire lab network     | Medium     | High   | High       | Chase      | pfSense firewall rules + VLAN segmentation| Low           | Monitored | May 2026     |
| R-04    | Malware introduction during testing       | Test VMs / endpoints        | Medium     | Medium | Medium     | Chase      | Wazuh monitoring, isolated test VLAN      | Low           | Monitored | May 2026     |
| R-05    | Data loss from lab incidents or failures  | All systems                 | Low        | Medium | Medium     | Chase      | Regular VM snapshots + external backups   | Low           | Monitored | May 2026     |
| R-06    | Misconfiguration of Wazuh SIEM            | Monitoring infrastructure   | Low        | High   | Medium     | Chase      | Configuration reviews, test alerts        | Low           | Monitored | May 2026     |

**Risk Scoring Legend**  
- **Likelihood / Impact**: Low / Medium / High  
- **Risk Score**: Low = Low×Low to Low×Medium; Medium = Medium×Medium; High/Critical = anything involving High Impact + Medium+ Likelihood

## Key Insights
- Highest risks center around patching and credential hygiene — common real-world issues.
- Strong controls (segmentation, monitoring, snapshots) significantly reduce residual risk.
- Regular review of this register will be part of quarterly lab maintenance.

## Recommendations & Action Plan
- Implement automated patching where possible.
- Expand Wazuh rules for AD logon anomalies.
- Add physical security considerations (lab hardware location).
- Review register after any major lab change.

## Screenshots / Evidence

![Risk Register Table View](screenshots/risk-register-table.png)  
![Wazuh Coverage Supporting Control](screenshots/wazuh-risk-mitigation.png)  
![pfSense VLAN Segmentation](screenshots/vlan-risk-control.png)

## SOC Analyst / GRC Relevance
Maintaining a risk register demonstrates proactive risk-based thinking — exactly what SOC teams and compliance roles require for prioritizing threats and recommending controls.

---

**Status**: Complete (Example)  
**Next Review**: Quarterly or after significant lab changes  
**Owner**: Chase Chase
