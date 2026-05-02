# Common Connectivity Troubleshooting

**Date**: May 2, 2026  
**Category**: Basic Network Setup & Troubleshooting  
**Related To**: CompTIA A+ Core 2 (Networking & Operational Procedures), Security+ (Troubleshooting & Diagnostics), SOC Analyst (initial incident triage & network visibility)

## Objective
Systematically troubleshoot and resolve common network connectivity issues in a multi-device lab environment. This builds a repeatable troubleshooting methodology essential for help desk, SOC, and general IT support roles.

## Environment
- **Devices**: Windows 11/10 laptops, Ubuntu desktop (Wazuh), Raspberry Pi, MacBook Air
- **Network**: pfSense firewall/router with VLANs, multiple subnets
- **Tools**: ipconfig / ifconfig / ip, ping, traceroute, nslookup, Wireshark, pfSense dashboard, Event Viewer

## Step-by-Step Troubleshooting Methodology (Follow this order)

### 1. Identify the Problem
- Document symptoms: No internet? Can’t reach specific device? Intermittent?
- Affected devices? All or specific?

### 2. Common Issues & Resolution Steps

**Issue 1: No Connectivity (Link Layer)**
- Check physical cables / Wi-Fi association.
- Verify interface status in pfSense and on device.
- Command: `ip link show` (Linux) or `ipconfig /all` (Windows).

**Issue 2: IP Configuration Problems**
- Run `ipconfig /release` then `ipconfig /renew` (Windows).
- Check for APIPA address (169.254.x.x) → indicates DHCP failure.
- Solution: Restart DHCP service on pfSense or check reservations.

**Issue 3: DNS Resolution Failures**
- Test: `ping 8.8.8.8` (IP works but name doesn’t).
- Commands: `nslookup google.com`, `ipconfig /flushdns`.
- Solution: Change DNS to 1.1.1.1 or pfSense DNS resolver.

**Issue 4: Firewall / Rule Blocking**
- Test from different VLANs.
- Check pfSense firewall logs (Status → System Logs → Firewall).
- Solution: Adjust rules or temporarily disable for testing.

**Issue 5: Routing / Gateway Issues**
- Verify default gateway with `ipconfig` or `ip route`.
- Use `traceroute 8.8.8.8` (Linux/Mac) or `tracert 8.8.8.8` (Windows).

**Issue 6: Inter-VLAN or Inter-Device Communication**
- Test same VLAN vs different VLAN.
- Verify firewall rules between segments.

### 3. Advanced Diagnostics
- Wireshark capture during failure.
- Check Windows Event Viewer (System logs).
- Review Wazuh alerts if integrated.
- Test with different devices to isolate issue.

### 4. Verify & Document
- Confirm fix with multiple tests.
- Document steps taken, commands, and resolution.

## Screenshots / Evidence

![ipconfig Showing Good Configuration](screenshots/ipconfig-good.png)  
![APIPA Address Example](screenshots/apipa-example.png)  
![pfSense Firewall Logs](screenshots/firewall-logs.png)  
![Successful Ping After Fix](screenshots/ping-after-fix.png)  
![Wireshark DNS Query Failure](screenshots/wireshark-dns-fail.png)

*(Upload your actual troubleshooting screenshots)*

## Challenges & Solutions (Real Examples from Lab)
- **Challenge**: Windows laptop got APIPA address → Solution: Renewed DHCP lease and restarted pfSense DHCP service.
- **Challenge**: Could reach gateway but not internet → Solution: Fixed upstream WAN link on pfSense and flushed DNS.
- **Challenge**: Inter-VLAN ping failed → Solution: Added explicit allow rule between Trusted and Servers VLAN.

## Lessons Learned
- Always follow a structured methodology (identify → theory → test → verify).
- Start with the simplest layer (physical → data link → network → transport).
- Documentation during troubleshooting saves huge time later.
- Many “connectivity” issues are actually DNS or firewall related.
- Testing from multiple devices helps isolate the problem.

## SOC Analyst Relevance
Troubleshooting skills are used daily in SOCs:
- Investigating why an endpoint stopped sending logs to SIEM
- Triaging network-based alerts
- Helping isolate compromised devices
- Verifying segmentation works during incidents
- Collaborating with network teams during outages

These skills transfer directly to real support tickets at CoolUnderFire Cybersecurity LLC.

**Next Steps**:
- Create a reusable troubleshooting checklist.
- Simulate more complex issues (e.g., DNS poisoning, blocked ports).
- Integrate troubleshooting with Wazuh alerts.

---

**Status**: Complete (Methodology + Common Fixes)  
**Time Spent**: ~2 hours  
**Files**: Screenshots + any exported logs.

**Ties to Certifications**: Perfect reinforcement of A+ Core 2 troubleshooting domain and Security+ operational procedures. Highly practical for entry-level SOC and support roles.
