# Risk Management Playbook

**Document ID**: CCF-PBK-001  
**Version**: 1.0  
**Effective Date**: May 2026  
**Owner**: Chase Cooley, CoolUnderFire Cybersecurity LLC  
**Purpose**: Provide a practical framework for identifying, assessing, mitigating, and monitoring risks in the home lab and client environments.

## 1. Introduction
Effective risk management is foundational to cybersecurity. This playbook outlines a simple, repeatable process based on NIST SP 800-30 principles, tailored for small lab and MSP-style operations.

## 2. Risk Management Process

### Step 1: Risk Identification
- Inventory assets (hardware, software, data, people).
- Identify threats (external attackers, insiders, natural disasters, errors).
- Identify vulnerabilities (unpatched systems, weak configurations, human factors).

### Step 2: Risk Assessment
- Evaluate **Likelihood** (Low/Medium/High)
- Evaluate **Impact** (Low/Medium/High)
- Calculate **Risk Score** (Likelihood × Impact)
- Prioritize risks (Critical → High → Medium → Low)

### Step 3: Risk Response
- **Avoid**: Eliminate the risk (e.g., remove unnecessary services).
- **Mitigate**: Implement controls (firewall rules, GPOs, Wazuh monitoring).
- **Transfer**: Use insurance or third-party services.
- **Accept**: Document and monitor low risks.

### Step 4: Monitoring & Review
- Regular scans and log monitoring (Wazuh).
- Quarterly risk register reviews.
- Review after major changes or incidents.

## 3. Home Lab Risk Register Summary
(See `home-lab-risk-assessment/Risk-Register-Example.md` for full table)

**Top Risks & Controls**:
- Credential compromise → Strong GPOs + MFA
- Unpatched systems → Scheduled updates + snapshots
- Lateral movement → VLAN segmentation + pfSense rules
- Detection gaps → Wazuh SIEM monitoring

## 4. Tools & Resources
- **Assessment**: This playbook + risk register
- **Monitoring**: Wazuh SIEM, pfSense logs
- **Controls**: Active Directory GPOs, firewall rules, snapshots
- **Documentation**: Portfolio folder + CoolUnderFire ticket templates

## 5. Roles & Responsibilities
- **Owner**: Overall risk accountability and approval of responses.
- **Technician**: Day-to-day identification, mitigation, and monitoring.
- **Clients (CoolUnderFire)**: Informed of risks and recommended controls.

## 6. Review & Maintenance
- This playbook is reviewed annually or after significant incidents/lab changes.
- All risks are tracked in the risk register.

**Approval**  
Signed: Chase Cooley 
Date: May 2026

---

**Status**: Living Document / Playbook  
**Intended Use**: Guide for lab maintenance, client risk discussions, and portfolio demonstration of risk management skills.
