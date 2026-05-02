# Home Lab Risk Assessment

**Date**: May 2026  
**Category**: Risk & Compliance  
**Related To**: Master's in Cybersecurity Management & Policy, Security+, SOC Risk-Based Thinking

## Objective
Perform a structured risk assessment of my home lab environment to identify threats, vulnerabilities, and mitigation controls. This demonstrates practical risk management skills applicable to SOC Analyst and GRC roles.

## Scope
- Assets: Windows 11/10 laptops, Ubuntu desktop (Wazuh), Raspberry Pi, pfSense firewall, VirtualBox VMs
- Environment: Isolated lab network with internet access for testing
- Frameworks Used: NIST SP 800-30 basics, qualitative risk scoring (Likelihood × Impact)

## Asset Inventory (Key Items)
- Domain Controller (Windows Server 2022)
- Wazuh SIEM Server
- Multiple Windows client endpoints
- pfSense perimeter firewall
- Raspberry Pi test devices

## Risk Assessment Table (Qualitative)

| Risk ID | Threat / Vulnerability                  | Likelihood | Impact | Risk Level | Mitigation / Control                  | Residual Risk |
|---------|-----------------------------------------|------------|--------|------------|---------------------------------------|---------------|
| R-01    | Weak password policies on AD            | Medium     | High   | High       | Enforced GPOs (12+ chars, complexity) | Low           |
| R-02    | Unpatched systems / outdated software   | High       | High   | Critical   | Regular patching schedule + snapshots | Medium        |
| R-03    | Unauthorized access via exposed services| Low        | High   | Medium     | pfSense firewall rules + VLANs        | Low           |
| R-04    | Malware introduction via testing        | Medium     | Medium | Medium     | Isolated VLANs + Wazuh monitoring     | Low           |
| R-05    | Data loss from lab incidents            | Medium     | Medium | Medium     | Regular VM snapshots & backups        | Low           |

## Key Findings & Recommendations
- **High Priority**: Strengthen password policies and implement regular vulnerability scanning.
- **Monitoring**: Wazuh provides excellent visibility — expand rules for AD events and file changes.
- **Segmentation**: VLANs and pfSense rules effectively limit lateral movement.
- **Documentation**: Maintain this assessment and review quarterly.

## Screenshots / Evidence

![Sample Risk Register Table](screenshots/risk-register.png)  
![Wazuh Monitoring Coverage](screenshots/wazuh-coverage.png)  
![pfSense Firewall Rules](screenshots/pfsense-segmentation.png)  
![AD Group Policy Password Settings](screenshots/gpo-risk-control.png)

## Lessons Learned
- Risk assessment is iterative — regular reviews are essential.
- Technical controls (firewall, SIEM, GPOs) must be paired with policy and process.
- Home lab serves as an excellent sandbox for practicing real-world risk management.

## SOC Analyst / GRC Relevance
- SOC analysts use risk-based thinking to prioritize alerts and recommend controls.
- Demonstrates ability to assess environments, document risks, and propose mitigations — valuable for compliance-heavy MSPs and enterprise roles.

**Overall Lab Risk Post-Mitigation**: Low to Medium (well-segmented and monitored).

---

**Status**: Complete  
**Time Spent**: ~2 hours  
**Next Review**: Quarterly or after major lab changes.
