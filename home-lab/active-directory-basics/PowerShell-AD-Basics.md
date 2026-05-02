# PowerShell Basics for Active Directory Management

**Date**: May 2026  
**Category**: Active Directory Basics  
**Related To**: Automation, Help Desk Efficiency, Security+ (IAM), SOC Scripting Skills

## Objective
Use PowerShell to automate common Active Directory tasks such as user creation, group management, and reporting. This demonstrates efficiency beyond GUI tools and is highly valued in modern IT/SOC environments.

## Environment
- **Domain Controller**: Windows Server 2022 (lab.local)
- **Tools**: PowerShell (with ActiveDirectory module), RSAT tools on Windows 11 client or DC
- **Prerequisites**: `Import-Module ActiveDirectory`

## Key Commands & Examples

### 1. Loading the Module & Basic Queries
```powershell
Import-Module ActiveDirectory
Get-ADDomain
Get-ADUser -Filter * | Select Name, SamAccountName, Enabled

2. Creating Users
PowerShell
New-ADUser -Name "jdoe" `
           -SamAccountName "jdoe" `
           -UserPrincipalName "jdoe@lab.local" `
           -AccountPassword (ConvertTo-SecureString "SecureP@ss123!" -AsPlainText -Force) `
           -Enabled $true `
           -Path "OU=Users,DC=lab,DC=local" `
           -ChangePasswordAtLogon $true

3. Group Management
PowerShell
New-ADGroup -Name "SOC Analysts" -GroupScope Global -Path "OU=Groups,DC=lab,DC=local"
Add-ADGroupMember -Identity "SOC Analysts" -Members "jdoe"
Get-ADGroupMember -Identity "SOC Analysts"

4. Bulk Operations & Reporting
PowerShell
# Bulk user creation from CSV (example)
Import-Csv -Path "C:\users.csv" | ForEach-Object { New-ADUser ... }

# Report of all users
Get-ADUser -Filter * -Properties LastLogonDate | Select Name, LastLogonDate | Export-Csv "user-report.csv"

5. Common Help Desk Scripts
Unlock account: Unlock-ADAccount -Identity jdoe
Reset password: Set-ADAccountPassword -Identity jdoe -NewPassword (ConvertTo-SecureString "NewPass123!" -AsPlainText -Force)

Screenshots
<img src="screenshots/powershell-import-module.png" alt="PowerShell Importing AD Module">
<img src="screenshots/new-aduser-powershell.png" alt="New-ADUser Command Execution">
<img src="screenshots/group-members-powershell.png" alt="Get-ADGroupMember Output">
<img src="screenshots/user-report-csv.png" alt="User Report CSV Export">

Challenges & Solutions

Challenge: ActiveDirectory module not available → Solution: Installed RSAT tools on client or ran on DC.
Challenge: Permission errors → Solution: Ran PowerShell as Domain Admin.
Challenge: Complex password handling → Solution: Used ConvertTo-SecureString correctly.

Lessons Learned

PowerShell is much faster for repetitive tasks than the GUI.
Scripting reduces human error in user provisioning/offboarding.
Always test scripts in a lab before production use.
Combining PowerShell with Group Policy creates powerful automation.

SOC Analyst / Help Desk Relevance
Automation skills are increasingly required in SOCs for efficient user management and response.
PowerShell is commonly used (and abused) by attackers — understanding it helps detect malicious scripts.
Enables quick reporting for audits and investigations.

Next Steps: Create a full user provisioning script and simulate help desk tickets with automation.

Status: Complete
Time Spent: ~1–1.5 hours

