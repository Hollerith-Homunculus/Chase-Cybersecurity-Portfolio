# Active Directory Basics Lab

**Focus:** Help Desk / Service Desk Support + Basic Access Control Practice

## Overview
This lab demonstrates foundational Active Directory (AD) setup and management using a Windows Server domain controller and client VMs.  
These skills are core for entry-level IT Help Desk roles (e.g., user account creation, password resets, group management) and provide a foundation for understanding access control and least-privilege principles in cybersecurity.

Goal: Simulate common Tier 1 support tasks while applying basic security best practices.

## Environment & Tools
- Virtualization: VirtualBox
- Server: Windows Server 2022 (evaluation ISO)
- Client: Windows 11 (evaluation ISO)
- Tools: Active Directory Users and Computers (dsa.msc), Group Policy Management (gpmc.msc), PowerShell (basic commands)
- Network: Host-Only adapter (isolated lab network)

## What I Did
- Promoted Windows Server VM to a domain controller (created domain: lab.local).
- Joined a Windows 11 client VM to the domain.
- Created user accounts, security groups, and organizational units (OUs).
- Configured basic Group Policy Objects (GPOs) for password policy and account lockout.
- Performed common support tasks: password reset, user lock/unlock, group membership changes.

## Step-by-Step Summary
1. Installed Windows Server 2022 in a VM and configured static IP.
2. Installed Active Directory Domain Services role → Promoted to domain controller (dcpromo wizard).
3. Created domain: lab.local.
4. Joined Windows 11 client to domain via System Properties → Change settings.
5. In AD Users and Computers:
   - Created OU: "Users"
   - Created test users (e.g., testuser1, helpdeskadmin)
   - Created security group: "Help Desk Team"
   - Added users to group
6. Created GPO: "Password Policy" – enforced minimum length 12 characters, complexity enabled.
7. Tested: Reset password for testuser1 from client VM, verified lockout after failed attempts.

## Screenshots / Evidence
![Domain Controller Promotion](./screenshots/domain-controller-setup.png)  
![User and Group Creation](./screenshots/ad-users-groups.png)  
![Group Policy Editor](./screenshots/gpo-password-policy.png)  
![Client Joined to Domain](./screenshots/client-domain-join.png)

(Add more screenshots as you complete labs – upload them to a `screenshots/` subfolder inside active-directory-basics/)

## Key Outcomes & Lessons
- Successfully built a functional AD domain from scratch – mirrors real-world MSP/help desk environments.
- Learned how weak password policies create security risks (e.g., easy guessing) – ties to Security+ access control and identity management topics.
- Demonstrates ability to perform routine user administration tasks calmly and accurately – essential for Service Desk roles.

## Skills Demonstrated
- **Technical:** Active Directory administration, user/group management, Group Policy configuration, domain joining, basic PowerShell (e.g., `New-ADUser`)
- **Help Desk:** Troubleshooting login issues, password resets, account lockouts
- **Security/Compliance:** Applying least-privilege access, enforcing password complexity (links to Master's policy coursework and PCI DSS-like controls from Chargebacks911 experience)

## Next Steps / Future Improvements
- Add more advanced GPOs (e.g., restrict USB devices, enforce screen lock timeout).
- Integrate with security tools (e.g., forward AD logs to a SIEM in a future lab).
- Simulate a help desk ticket: "User locked out – resolve and document."
- Automate user creation with PowerShell scripts.

This lab is part of ongoing deliberate practice to transition from customer service to IT support / cybersecurity roles.
