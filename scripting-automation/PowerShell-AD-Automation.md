# PowerShell Active Directory Automation Examples

**Date**: May 2026  
**Category**: Scripting & Automation  
**Related To**: Active Directory Basics, Help Desk Efficiency, SOC Automation

## Objective
Automate common Active Directory tasks (user creation, group management, reporting) to improve efficiency and reduce errors in lab and support environments.

## Environment
- **Domain**: lab.local (Windows Server 2022 DC)
- **Tools**: PowerShell with ActiveDirectory module (RSAT installed)

## Key Scripts & Examples

### 1. Bulk User Creation from CSV
```powershell
Import-Csv -Path "C:\new-users.csv" | ForEach-Object {
    New-ADUser -Name $_.Name `
               -SamAccountName $_.SamAccountName `
               -UserPrincipalName "$($_.SamAccountName)@lab.local" `
               -AccountPassword (ConvertTo-SecureString $_.Password -AsPlainText -Force) `
               -Enabled $true `
               -Path "OU=Users,DC=lab,DC=local" `
               -ChangePasswordAtLogon $true
    Write-Output "Created user: $($_.Name)"
}

2. Add Users to Security Group
PowerShell
Add-ADGroupMember -Identity "Help Desk Team" -Members "testuser1","jdoe"

3. Generate User Report
PowerShell
Get-ADUser -Filter * -Properties LastLogonDate,Enabled | 
    Select Name, SamAccountName, Enabled, LastLogonDate | 
    Export-Csv "AD-User-Report.csv" -NoTypeInformation

4. Unlock Multiple Accounts
PowerShell
Get-ADUser -Filter {LockedOut -eq $true} | Unlock-ADAccount

Screenshots
<img src="screenshots/powershell-bulk-create.png" alt="PowerShell User Creation Output">
<img src="screenshots/user-report-csv.png" alt="AD User Report CSV">
<img src="screenshots/group-add-script.png" alt="Group Membership Script">

Lessons Learned

PowerShell significantly speeds up repetitive tasks.
Always test scripts in a lab environment first.
Combining scripts with Group Policy creates powerful automation.

SOC Analyst Relevance

Automation is essential for scaling SOC operations (user provisioning, reporting, alert enrichment).
Understanding PowerShell helps detect malicious scripts during investigations.

Next Steps: Expand to full user lifecycle script (create → add to groups → send welcome email simulation) and integrate with ticketing.

Status: Complete (Examples)
Time Spent: ~1 hour
This gives you a solid, usable starting point for the scripting folder.

