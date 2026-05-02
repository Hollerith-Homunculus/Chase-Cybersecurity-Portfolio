# Access Control Policy

**Document ID**: CCF-POL-001  
**Version**: 1.0  
**Effective Date**: May 2026  
**Owner**: Chase [Last Name], CoolUnderFire Cybersecurity LLC  
**Purpose**: Define rules for granting, managing, and revoking access to systems and data to ensure confidentiality, integrity, and availability.

## 1. Scope
This policy applies to all users, systems, and data within the CoolUnderFire lab environment, client support engagements, and personal cybersecurity practice. It covers physical, logical, and remote access.

## 2. Policy Statements

### 2.1 Least Privilege
- Users and processes are granted only the minimum permissions required to perform their duties.
- Access is reviewed quarterly or upon role change.

### 2.2 Role-Based Access Control (RBAC)
- Access is assigned based on job function or project role.
- Examples:
  - Help Desk: Read-only monitoring + password reset rights
  - SOC Analyst: Alert triage, log access, containment tools
  - Administrator: Full rights (with approval and logging)

### 2.3 Authentication Requirements
- Strong passwords (minimum 12 characters, complexity enabled, history remembered).
- Multi-Factor Authentication (MFA) required for all administrative and remote access where supported.
- Account lockout after 5 failed attempts (15-minute duration).

### 2.4 Account Lifecycle
- New accounts: Approved by owner, created with temporary password (must change on first use).
- Role changes: Access reviewed and adjusted within 24 hours.
- Offboarding: Immediate account disablement + removal within 48 hours.

### 2.5 Remote Access
- All remote access via VPN or secure RDP/SSH with MFA.
- Session timeouts after 15 minutes of inactivity.
- Logging of all remote sessions.

### 2.6 Monitoring & Auditing
- All access attempts logged via Wazuh / AD auditing.
- Suspicious activity (failed logins, off-hours access) triggers alerts.
- Quarterly access reviews conducted.

### 2.7 Exceptions
- Any exception requires written approval from the owner and must be time-limited with compensating controls.

## 3. Responsibilities
- **Owner/Administrator**: Policy enforcement, reviews, approvals.
- **Users**: Comply with policy, report suspicious activity immediately.
- **CoolUnderFire Support Clients**: Informed of applicable controls during engagements.

## 4. Enforcement & Violations
- Violations may result in access revocation and/or disciplinary action.
- All access is monitored; misuse will be investigated.

## 5. Review & Revision
- This policy is reviewed annually or after significant incidents/changes.
- Last Reviewed: May 2026

## 6. References
- NIST SP 800-53 (Access Control Family)
- Security+ Domain 5 (Identity and Access Management)
- Company Master’s policy coursework and best practices

**Approval**  
Signed: Chase Cooley 
Date: May 2026

---

**Status**: Draft / Sample Policy  
**Intended Use**: Living document for lab, portfolio, and CoolUnderFire client engagements. Customize per client needs.
