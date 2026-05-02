# AD Domain Controller Setup

**Date**: May 2026  
**Category**: Active Directory Basics  
**Related To**: CompTIA A+ / Security+ (Identity & Access Management), Help Desk Operations

## Objective
Install and promote a Windows Server VM to a Domain Controller, creating a functional Active Directory domain (lab.local). This establishes the foundation for user management, Group Policy, and access control in a lab environment.

## Environment
- **Virtualization**: VirtualBox
- **Server VM**: Windows Server 2022 Evaluation (2 vCPU, 4GB RAM recommended)
- **Network**: Host-Only or internal pfSense network with static IP
- **Tools**: Server Manager, PowerShell, dcpromo (legacy) or Active Directory Domain Services configuration wizard

## Step-by-Step Process

### 1. Prepare the Windows Server VM
- Install Windows Server 2022.
- Set static IP (e.g., 192.168.10.10).
- Rename computer and restart.

### 2. Install Active Directory Domain Services Role
1. Open **Server Manager** → Add Roles and Features.
2. Select **Active Directory Domain Services**.
3. Complete the wizard and install.

### 3. Promote to Domain Controller
1. Click the notification flag in Server Manager → **Promote this server to a domain controller**.
2. Choose **Add a new forest** → Root domain name: `lab.local`.
3. Set Directory Services Restore Mode password.
4. Complete the wizard (DNS will be installed automatically).
5. Server will restart.

### 4. Post-Promotion Verification
- Login with domain admin account (`lab\Administrator`).
- Open **Active Directory Users and Computers** (`dsa.msc`) to confirm the domain.
- Verify DNS records in DNS Manager.

## Screenshots

![Server Manager Role Installation](screenshots/role-installation.png)  
![Promotion Wizard - New Forest](screenshots/promotion-wizard.png)  
![AD Users and Computers - Domain Root](screenshots/ad-root.png)  
![Server Properties Post-Promotion](screenshots/dc-properties.png)

## Challenges & Solutions
- **Challenge**: DNS issues after promotion → Solution: Ensured the server pointed to its own IP for DNS.
- **Challenge**: Insufficient RAM during promotion → Solution: Increased VM RAM to 4–6 GB.
- **Challenge**: Time sync errors → Solution: Configured NTP in pfSense or on the DC.

## Lessons Learned
- A clean, static IP configuration is critical before promotion.
- The domain controller becomes the source of truth for identity in the environment.
- Proper planning of domain name and forest structure prevents future headaches.

## SOC Analyst / Help Desk Relevance
- Understanding AD setup helps investigate authentication issues and logon events.
- Domain controllers are high-value targets — knowledge of baseline setup aids in detecting anomalies.
- Foundation for access control, auditing, and Group Policy enforcement.

**Next Steps**: Join clients, create users/groups, configure GPOs.

---

**Status**: Complete  
**Time Spent**: ~1.5–2 hours
