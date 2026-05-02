# User & Group Management in Active Directory

**Date**: May 2026  
**Category**: Active Directory Basics  
**Related To**: Help Desk Operations, Security+ (Identity & Access Management), Least Privilege Principle

## Objective
Create and manage users, Organizational Units (OUs), and security groups in Active Directory. Perform common help desk tasks such as account creation, password resets, and group membership changes.

## Environment
- **Domain Controller**: Windows Server 2022 (lab.local)
- **Clients**: Windows 11 joined to the domain
- **Tools**: Active Directory Users and Computers (`dsa.msc`), PowerShell, AD Administrative Center

## Step-by-Step Process

### 1. Create Organizational Units (OUs)
1. Open **Active Directory Users and Computers**.
2. Right-click domain → New → Organizational Unit.
3. Create: `Users`, `Groups`, `Computers`, `Service Accounts`.

### 2. Create Test Users
- Right-click Users OU → New → User.
- Examples:
  - `testuser1` (regular user)
  - `helpdeskadmin` (for simulated help desk account)
- Set strong initial passwords and require change at next logon.

### 3. Create Security Groups
- New → Group.
- Examples:
  - `Help Desk Team` (Security Group, Global scope)
  - `IT Administrators`
- Add users to groups.

### 4. Common Help Desk Tasks
- **Password Reset**: Right-click user → Reset Password.
- **Unlock Account**: Right-click user → Enable Account (after lockout).
- **Group Membership**: Add/remove users via Member Of tab.
- **Disable Account**: For offboarding simulation.

### 5. Basic PowerShell Examples
```powershell
# Create user
New-ADUser -Name "testuser2" -AccountPassword (ConvertTo-SecureString "P@ssw0rd123!" -AsPlainText -Force) -Enabled $true -Path "OU=Users,DC=lab,DC=local"

# Add to group
Add-ADGroupMember -Identity "Help Desk Team" -Members "testuser1"

Screenshots
<img src="screenshots/ous-structure.png" alt="Organizational Units Structure">
<img src="screenshots/new-user.png" alt="User Creation Dialog">
<img src="screenshots/group-membership.png" alt="Security Group Membership">
<img src="screenshots/password-reset.png" alt="Password Reset">
<img src="screenshots/powershell-aduser.png" alt="PowerShell User Creation">
Challenges & Solutions

Challenge: Users unable to log in after creation → Solution: Ensured "Password never expires" was off and required change at next logon.
Challenge: Delegation confusion → Solution: Used separate OUs for better organization.
Challenge: PowerShell module not loaded → Solution: Ran Import-Module ActiveDirectory.

Lessons Learned

Proper OU structure makes management and Group Policy application much easier.
Strong password policies and regular audits prevent common security issues.
Automating with PowerShell saves time on repetitive tasks.

SOC Analyst / Help Desk Relevance

Help Desk tasks are daily SOC Tier 1 work (account issues, access requests).
Understanding group nesting and permissions helps investigate privilege escalation attempts.
Logging of account changes is critical for detecting insider threats or compromised accounts.

Next Steps: Configure Group Policy Objects and simulate help desk tickets.

Status: Complete
Time Spent: ~1–1.5 hours
