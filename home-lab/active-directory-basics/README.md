# Active Directory Basics Lab

**Focus:** Help Desk / Service Desk Support + Identity & Access Management (IAM) Practice  
**Status:** Complete (Core Foundations)

## Overview
This lab demonstrates foundational Active Directory Domain Services (AD DS) setup and management using a Windows Server domain controller and client VMs.  

These skills are essential for entry-level IT Help Desk, System Administrator, and junior SOC Analyst roles (user provisioning, access control, Group Policy, and basic troubleshooting). It also reinforces Security+ Domain 5 (Identity and Access Management) and concepts from the Master’s program.

**Goal:** Simulate Tier 1 support tasks while applying security best practices such as least privilege and strong password policies.

## Environment & Tools
- **Virtualization**: VirtualBox
- **Server**: Windows Server 2022 Evaluation (Domain Controller)
- **Clients**: Windows 11 Evaluation VMs
- **Tools**: Active Directory Users and Computers, Group Policy Management, PowerShell, Event Viewer
- **Network**: Isolated lab network (pfSense or Host-Only)

**Simple Architecture**:
Internet / pfSense
|
Windows Server 2022 DC (lab.local)
|
├── OU=Users
├── OU=Groups
├── Windows 11 Clients
└── Integration: Future Wazuh logging


## Projects / Documents

| Date       | Topic                              | Key Skills Demonstrated                     | Status     | Link |
|------------|------------------------------------|---------------------------------------------|------------|------|
| 2026-05-xx | Domain Controller Setup             | DC promotion, forest creation                    | Complete  | [Domain-Setup.md](./Domain-Setup.md) |
| 2026-05-xx | User & Group Management             | OUs, users, groups, password resets              | Complete  | [User-Management.md](./User-Management.md) |
| 2026-05-xx | Basic Group Policy Objects          | Password & lockout policies, workstation settings| Complete  | [Basic-GPOs.md](./Basic-GPOs.md) |
| 2026-05-xx | Domain Join Troubleshooting         | Common join issues, DNS, connectivity            | Complete  | [Domain-Join-Troubleshooting.md](./Domain-Join-Troubleshooting.md) |
| 2026-05-xx | PowerShell AD Basics                | Automation, scripting for users & groups         | Complete  | [PowerShell-AD-Basics.md](./PowerShell-AD-Basics.md) |
| 2026-05-xx | Help Desk Ticket Simulations        | End-to-end ticket resolution & documentation     | Complete  | [Help-Desk-Ticket-Simulations.md](./Help-Desk-Ticket-Simulations.md) |

## What I Did (Summary)
- Promoted Windows Server to Domain Controller (`lab.local`)
- Joined Windows 11 client to the domain
- Created OUs, test users, security groups
- Configured basic GPOs (password complexity, account lockout)
- Performed common help desk tasks (password reset, unlock, group membership)

## Skills Demonstrated
- **Technical**: AD DS installation, user/group/OUs management, GPO configuration, domain joining, PowerShell automation
- **Help Desk**: Password resets, account lockouts, troubleshooting, ticket handling
- **Security**: Least privilege, strong password policies, audit awareness, segmentation concepts
- **Soft Skills**: Clear documentation and structured troubleshooting
  
## SOC Analyst Relevance
ctive Directory is the backbone of identity in most organizations. These labs provide:
- Understanding of authentication flows and common attack vectors (e.g., password spraying, privilege escalation)
- Ability to investigate logon events and access issues
- Foundation for monitoring AD with SIEM (future Wazuh integration)
- Practical experience with access control and compliance

## Screenshots / Evidence
(See individual project files for detailed screenshots. Main folder contains a `screenshots/` subfolder with key visuals.)

![Domain Controller Promotion](screenshots/dc-promotion.png)  
![AD Users and Computers](screenshots/ad-users.png)  
![Group Policy Password Settings](screenshots/gpo-password-policy.png)  
![Client Joined to Domain](screenshots/domain-joined-client.png)

## Key Outcomes & Lessons
- Built a fully functional domain from scratch.
- Learned how weak configurations create real security risks.
- Gained confidence performing routine IAM tasks efficiently and securely.
- Automation (PowerShell) and proper troubleshooting methodology save significant time.


## Next Steps / Future Labs
- Advanced GPOs (USB restrictions, login scripts)
- AD logging and integration with Wazuh SIEM
- Simulate attack scenarios (e.g., password spraying awareness)
- Full user lifecycle automation script
- Integration with CoolUnderFire Cybersecurity LLC support processes
---

**Last Updated**: May 2026  
This lab is part of deliberate practice transitioning customer service experience into cybersecurity / IT support roles.
