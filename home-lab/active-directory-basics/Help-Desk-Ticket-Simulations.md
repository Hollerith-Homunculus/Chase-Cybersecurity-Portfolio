# Help Desk Ticket Simulations in Active Directory

**Date**: May 2026  
**Category**: Active Directory Basics  
**Related To**: Help Desk / Service Desk, SOC Tier 1, Troubleshooting & Customer Service

## Objective
Simulate real-world help desk tickets involving Active Directory issues. Practice end-to-end resolution, documentation, and communication — key skills for transitioning into IT support and SOC roles.

## Environment
- **Domain**: lab.local (Windows Server 2022 DC)
- **Clients**: Multiple Windows 11 VMs
- **Tools**: AD Users and Computers, Group Policy, Event Viewer, PowerShell, Remote Desktop

## Simulated Tickets & Resolutions

### Ticket 1: "I forgot my password" (Password Reset)
- **Symptoms**: User cannot log in.
- **Actions**:
  1. Verified identity via alternate contact.
  2. Reset password in AD and set "User must change password at next logon".
  3. Documented in ticket system simulation.
- **Prevention**: Self-service password reset (future lab).

### Ticket 2: "Account locked out after vacation"
- **Actions**:
  1. Checked lockout policy.
  2. Unlocked account via AD.
  3. Advised on password best practices.

### Ticket 3: "Cannot access shared department folder"
- **Actions**:
  1. Verified group membership.
  2. Added user to correct security group.
  3. Forced Group Policy update.

### Ticket 4: "New employee needs account created"
- **Actions**:
  1. Created user in correct OU with template.
  2. Added to appropriate groups.
  3. Provided temporary credentials.

## Screenshots

![Simulated Password Reset Ticket](screenshots/ticket-password-reset.png)  
![Account Unlock in AD](screenshots/account-unlock.png)  
![Group Membership Update](screenshots/group-add-ticket.png)  
![Event Viewer Login Events](screenshots/login-events.png)

## Troubleshooting Methodology Used
1. Gather information from "user".
2. Reproduce / verify issue.
3. Apply fix using least privilege.
4. Test resolution.
5. Document and close ticket.

## Lessons Learned
- Clear communication and verification steps prevent repeat tickets.
- Documentation is as important as the technical fix.
- Many issues are permission or policy related.
- Balancing security (strong passwords, lockouts) with user experience is key.

## SOC Analyst / Help Desk Relevance
- Tier 1 SOC analysts handle authentication and access-related tickets daily.
- Strong troubleshooting + documentation skills accelerate promotion to higher tiers.
- Helps understand normal vs. suspicious account activity (e.g., multiple lockouts could indicate brute force).

**Next Steps**: Integrate with a ticketing simulation tool (or Notion), add more complex scenarios (compromised account response), and forward AD logs to Wazuh.

---

**Status**: Complete (Simulations)  
**Time Spent**: ~1 hour

