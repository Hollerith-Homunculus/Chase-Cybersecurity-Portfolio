# Basic Group Policy Objects (GPOs) Configuration

**Date**: May 2026  
**Category**: Active Directory Basics  
**Related To**: Security+ (Identity & Access Management, Policies), Help Desk & Compliance

## Objective
Create and apply basic Group Policy Objects to enforce security settings such as password requirements, account lockout, and screen lock timeouts across domain users.

## Environment
- **Domain Controller**: Windows Server 2022 (lab.local)
- **Clients**: Windows 11 joined to the domain
- **Tools**: Group Policy Management Console (`gpmc.msc`), Group Policy Object Editor

## Step-by-Step Process

### 1. Open Group Policy Management
- Run `gpmc.msc` on the Domain Controller.

### 2. Create and Link GPOs
1. Right-click **Group Policy Objects** → New.
2. Name examples:
   - `Password Policy`
   - `Account Lockout Policy`
   - `Workstation Security`

### 3. Configure Password Policy GPO
- Edit the GPO → Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies → Password Policy.
- Settings:
  - Minimum password length: **12 characters**
  - Password must meet complexity requirements: **Enabled**
  - Enforce password history: **24 passwords remembered**
  - Maximum password age: **90 days**

### 4. Configure Account Lockout Policy
- Account Lockout Threshold: **5 invalid attempts**
- Account Lockout Duration: **15 minutes**
- Reset account lockout counter after: **15 minutes**

### 5. Configure Additional Workstation Settings
- Under User Configuration → Administrative Templates → Control Panel → Personalization:
  - Screen saver timeout + password protect.
- Link the GPO to the appropriate OU (e.g., Users OU).
- Force update with `gpupdate /force` on client.

### 6. Verification
- Log in as test user on client.
- Attempt to change password to a weak one.
- Test lockout after failed attempts.
- Verify screen lock behavior.

## Screenshots

![GPMC Console](screenshots/gpmc-overview.png)  
![Password Policy Settings](screenshots/password-policy-gpo.png)  
![Account Lockout Settings](screenshots/lockout-policy.png)  
![gpupdate Command](screenshots/gpupdate.png)  
![Policy Applied on Client](screenshots/client-policy-applied.png)

## Challenges & Solutions
- **Challenge**: GPO not applying → Solution: Used `gpupdate /force`, checked OU linking, and ran `gpresult /r` to verify.
- **Challenge**: Conflicts with domain default policy → Solution: Ensured the new GPO had higher precedence (link order).
- **Challenge**: Client not receiving updates → Solution: Verified client was joined to domain and DNS pointed to DC.

## Lessons Learned
- Group Policy is a powerful centralized management tool.
- Order of GPO application and inheritance matters (LSDOU: Local, Site, Domain, OU).
- Security policies must balance usability and protection.

## SOC Analyst / Help Desk Relevance
- GPOs enforce security baselines across the organization.
- SOC analysts review GPO changes during investigations (who changed what?).
- Helps enforce compliance (password policies, lockouts) and reduce attack surface.
- Understanding GPOs aids in detecting policy tampering by attackers.

**Next Steps**: Advanced GPOs (USB restrictions, software restriction) and AD logging to SIEM.

---

**Status**: Complete  
**Time Spent**: ~1.5 hours
