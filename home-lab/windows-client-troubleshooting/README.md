# Windows Client Troubleshooting Lab

**Focus:** Entry-Level Help Desk / Service Desk Troubleshooting

## Overview
This lab simulates common end-user issues on Windows 10/11 clients in a VirtualBox environment.  
It builds core skills for Tier 1 support tickets: identifying symptoms, basic diagnosis, and resolution using built-in tools — directly aligned with CompTIA A+ troubleshooting methodology and real MSP/help desk workflows.

Goal: Practice "identify → test → resolve → document" process for 5 common scenarios.

## Environment & Tools
- Virtualization: VirtualBox (latest version)
- OS: Windows 11 (or Windows 10) evaluation ISO from Microsoft
- Network: NAT or Host-Only adapter (isolated)
- Tools: Event Viewer, Task Manager, Device Manager, ipconfig, sfc /scannow, msconfig, Control Panel, PowerShell basics
- Snapshots: Use VirtualBox snapshots before/after each scenario for safe testing

## What I Did
Simulated and resolved these common help desk scenarios (inspired by CompTIA A+ 220-1201/1202 and Professor Messer videos):

1. **No Internet Connectivity**  
   - Symptoms: Cannot browse web, ping fails.  
   - Resolved: Checked cable/Adapter settings → ipconfig /release & /renew → flushed DNS → restarted adapter.

2. **Slow Performance / High Resource Usage**  
   - Symptoms: Lag, apps freeze.  
   - Resolved: Used Task Manager to identify CPU/RAM hogs → ended unnecessary processes → ran Disk Cleanup → disabled startup items in msconfig.

3. **Printer Not Printing / Offline**  
   - Symptoms: Printer shows offline or jobs stuck in queue.  
   - Resolved: Cleared print spooler (services.msc → Print Spooler restart) → removed/re-added printer → checked drivers.

4. **Application Crashes or Won't Launch**  
   - Symptoms: App closes immediately or error message.  
   - Resolved: Ran as administrator → compatibility mode → sfc /scannow & DISM repair → reinstalled app.

5. **Blue Screen of Death (BSOD) or Boot Failure**  
   - Symptoms: Stop error or automatic restart.  
   - Resolved: Booted to Safe Mode → checked Event Viewer for error code → rolled back recent driver/update → ran Startup Repair.

## Step-by-Step Summary (Example: No Internet Scenario)
1. User reports "No internet" — gathered info (recent changes? Wi-Fi or Ethernet?).
2. Verified symptoms: ping 8.8.8.8 fails, ipconfig shows no IP.
3. Tested theory: Restarted network adapter (Device Manager → disable/enable).
4. Fixed: ipconfig /flushdns → netsh int ip reset → restart PC.
5. Verified: Successful ping and browsing.
6. Documented: Screenshot of ipconfig before/after.

(Repeat pattern for other scenarios — always document before/after states.)

## Screenshots / Evidence
![No Internet - ipconfig before fix](./screenshots/no-internet-before.png)  
![No Internet - resolution steps](./screenshots/no-internet-fix.png)  
![Printer Spooler restart](./screenshots/printer-spooler.png)  
![Task Manager high CPU](./screenshots/task-manager-slow.png)  
(Add your actual screenshots here after uploading them to a `screenshots/` subfolder inside this directory.)

## Key Outcomes & Lessons
- Resolved 5 common tickets end-to-end — mirrors 80% of entry-level help desk calls.
- Learned systematic approach: Identify problem → Establish theory → Test → Plan action → Implement → Verify → Document (CompTIA troubleshooting model).
- Demonstrates calm, methodical support under pressure — transferable to Service Desk roles.

## Skills Demonstrated
- **Technical:** Windows OS troubleshooting, built-in utilities (Event Viewer, Task Manager, ipconfig, sfc), driver management
- **Help Desk:** Symptom gathering, first-call resolution, clear documentation for ticket closure
- **Security Tie-In:** Recognized how misconfigurations (e.g., weak drivers) create vulnerabilities — links to Security+ and Master's policy/risk topics

## Next Steps / Future Improvements
- Add more scenarios: BSOD with specific error codes, malware symptoms (e.g., fake antivirus popups).
- Integrate remote tools simulation (e.g., TeamViewer/AnyDesk basics).
- Create mock help desk tickets: "User ticket #123 – no internet – resolve and close."
- Automate basic checks with PowerShell scripts (e.g., network reset script).

This lab is part of my deliberate practice for entry-level IT Help Desk / Service Desk Technician roles in Tampa Bay.
