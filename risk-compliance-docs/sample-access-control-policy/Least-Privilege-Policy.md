# Least Privilege Policy

**Document ID**: CCF-POL-003  
**Version**: 1.0  
**Effective Date**: May 2026  
**Owner**: Chase Cooley, CoolUnderFire Cybersecurity LLC  
**Purpose**: Ensure users, processes, and systems are granted only the minimum permissions necessary to perform their functions, reducing the attack surface and limiting potential damage from compromise.

## 1. Scope
This policy applies to all users, service accounts, applications, and systems in the lab environment and CoolUnderFire client support engagements.

## 2. Policy Statements

### 2.1 Principle of Least Privilege
- Access rights are granted based on job function or specific task requirements.
- Default access is **deny** unless explicitly approved.
- Permissions are reviewed at least quarterly or upon role/employment change.

### 2.2 Role-Based Access Control (RBAC)
- Use roles and groups instead of individual user permissions where possible.
- Examples:
  - Standard User: Basic productivity applications only
  - Help Desk: Password reset + read-only monitoring
  - Administrator: Full rights (time-limited and logged when possible)

### 2.3 Account Types & Privileges
- **Standard User Accounts**: No administrative rights.
- **Administrator Accounts**: Separate from daily use accounts; used only when necessary.
- **Service Accounts**: Restricted to specific services, with long complex passwords and minimal rights.
- **Temporary/Elevated Access**: Time-limited (e.g., 8 hours) with approval and logging.

### 2.4 Just-In-Time (JIT) Access (Where Feasible)
- Use privileged access management tools or manual approval processes for elevated rights.
- All elevated sessions must be logged.

### 2.5 Monitoring & Auditing
- All privilege use and access changes are logged via Wazuh / AD auditing.
- Anomalous privilege escalation triggers alerts.

### 2.6 Review & Revocation
- Access reviews conducted quarterly.
- Immediate revocation upon role change or termination.

## 3. Responsibilities
- **System Owners/Admins**: Implement and enforce least privilege.
- **Users**: Request only necessary access and report misuse.
- **CoolUnderFire Support**: Apply least privilege in all client recommendations and configurations.

## 4. Enforcement
- Technical controls: Group Policy, firewall rules, application whitelisting.
- Violations: Reviewed case-by-case; may result in access revocation or disciplinary action.

## 5. Exceptions
- Documented exceptions require business justification, compensating controls, and time limits.

## 6. References
- NIST SP 800-53 (AC-6 Least Privilege)
- Principle of Least Privilege (industry best practice)
- Security+ Domain 5 (Identity and Access Management)

**Approval**  
Signed: Chase Cooley 
Date: May 2026

---

**Status**: Sample / Draft Policy  
**Intended Use**: Template for lab enforcement, client engagements, and portfolio demonstration. Enforce via Active Directory groups and GPOs where applicable.
