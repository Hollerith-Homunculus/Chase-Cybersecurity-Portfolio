# Active Directory Basics Lab

**Focus:** Help Desk / Service Desk Support + Identity & Access Management (IAM) Practice  
**Status:** In Progress (Core Setup Complete)

## Overview
This lab demonstrates foundational Active Directory Domain Services (AD DS) setup and management using a Windows Server domain controller and client VMs.  

These skills are essential for entry-level IT Help Desk, System Administrator, and junior SOC Analyst roles (user provisioning, access control, Group Policy, and basic troubleshooting). It also reinforces Security+ Domain 5 (Identity and Access Management) and concepts from the Master’s program.

**Goal:** Simulate Tier 1 support tasks while applying security best practices such as least privilege and strong password policies.

## Environment & Tools
- **Virtualization**: VirtualBox
- **Server**: Windows Server 2022 (evaluation)
- **Clients**: Windows 11 (evaluation)
- **Tools**: Active Directory Users and Computers (`dsa.msc`), Group Policy Management (`gpmc.msc`), PowerShell, RSAT tools
- **Network**: Isolated Host-Only or pfSense internal network

**Simple Architecture**:
Windows Server 2022 (DC) - lab.local
|
Windows 11 Clients
|
Organizational Units (OUs) + Security Groups


## Projects / Documents

| Date       | Topic                              | Key Skills Demonstrated                     | Status     | Link |
|------------|------------------------------------|---------------------------------------------|------------|------|
| 2026-04-24 | AD Domain Controller Setup         | DC promotion, domain creation               | Complete   | [Domain-Setup.md](./Domain-Setup.md) |
| 2026-05-01 | User & Group Management            | OUs, users, groups, password resets         | Complete   | [User-Management.md](./User-Management.md) |
| 2026-05-02 | Basic Group Policy Objects         | Password policy, lockout, screen timeout    | Complete   | [Basic-GPOs.md](./Basic-GPOs.md) |
| ...        | ...                                | ...                                         | ...        | ... |

## What I Did (Summary)
- Promoted Windows Server to Domain Controller (`lab.local`)
- Joined Windows 11 client to the domain
- Created OUs, test users, security groups
- Configured basic GPOs (password complexity, account lockout)
- Performed common help desk tasks (password reset, unlock, group membership)

## Skills Demonstrated
- **Technical**: AD DS installation, domain joining, user/group/OUs management, GPO creation, basic PowerShell (`New-ADUser`, `Add-ADGroupMember`)
- **Help Desk**: Account lifecycle, troubleshooting login issues
- **Security**: Least privilege, password policies, audit basics (ties to Security+ and Master’s policy coursework)

## SOC Analyst Relevance
Understanding Active Directory is critical in SOC environments because:
- Most organizations use AD for identity
- Attackers frequently target AD (Kerberoasting, Golden Ticket, etc.)
- SOC analysts review AD logs for suspicious logons and permission changes
- Helps with access control investigations and incident response

## Screenshots / Evidence
(Upload to a `screenshots/` subfolder)

![Domain Controller Promotion](screenshots/dc-promotion.png)  
![AD Users and Computers](screenshots/ad-users.png)  
![Group Policy Password Settings](screenshots/gpo-password-policy.png)  
![Client Joined to Domain](screenshots/domain-joined-client.png)

## Key Outcomes & Lessons
- Successfully built a functional domain from scratch — mirrors real MSP/help desk environments.
- Learned how weak policies create real security risks.
- Gained confidence performing routine IAM tasks accurately and securely.

## Next Steps / Future Labs
- Advanced GPOs (USB restrictions, login scripts)
- AD logging & integration with Wazuh SIEM
- Simulate help desk tickets and compromised accounts
- PowerShell automation for user provisioning
- Basic AD attack/defense exercises (e.g., password spraying awareness)

---

**Last Updated**: May 2026  
This lab is part of deliberate practice transitioning customer service experience into cybersecurity / IT support roles.
