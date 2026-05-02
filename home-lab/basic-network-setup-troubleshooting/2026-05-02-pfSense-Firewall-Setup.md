# pfSense Firewall Installation & Basic Configuration

**Date**: May 2, 2026  
**Category**: Basic Network Setup & Troubleshooting / Perimeter Security  
**Related To**: CompTIA A+ Core 2 (Networking), Security+ (Network Security & Firewalls), SOC Analyst (network visibility & segmentation)

## Objective
Install and configure pfSense as the primary firewall/router for my home lab. This creates a controlled network boundary, enables basic traffic rules, and provides visibility into network activity — foundational for SOC monitoring and defensive security.

## Environment
- **Hardware**: Dedicated mini PC or VirtualBox VM on Ubuntu desktop
- **Interfaces**:
  - WAN: Connected to upstream router/internet (or lab simulation)
  - LAN: Internal trusted network (Windows laptops + servers)
  - OPT1 (optional): Isolated test segment (Raspberry Pi + vulnerable VMs)
- **Downstream**: Ubuntu server (Wazuh), Windows endpoints, Raspberry Pi
- **Monitoring**: Wireshark on key segments + future Wazuh integration

## Step-by-Step Process

### 1. Download & Install pfSense
1. Download latest pfSense ISO from [netgate.com](https://www.netgate.com/pfSense/download).
2. Create bootable USB with Rufus (or burn to disc).
3. Boot the target machine/VM from the USB.
4. Follow installer: Choose full install, set up root password.

### 2. Initial Configuration (Console)
- Assign interfaces (e.g., igb0 = WAN, igb1 = LAN).
- Set LAN IP (default 192.168.1.1) — use a different subnet from upstream if double-NAT.
- Enable DHCP server on LAN.

### 3. Web GUI Setup
1. From a Windows laptop on LAN, open browser → `https://192.168.1.1`
2. Login: `admin` / `pfsense` (change password immediately).
3. Run the setup wizard:
   - Set hostname and domain
   - Configure NTP & Timezone
   - WAN configuration (DHCP or static)
   - Review LAN settings

### 4. Basic Firewall Rules & Hardening
- **LAN → Any**: Allow outbound internet (default).
- **Block unnecessary inbound** on WAN.
- Create alias for lab devices.
- Add simple rules (example):
  - Allow RDP/SSH only from management IP (if needed).
  - Block all inbound on WAN except established connections.
- Enable logging on key rules.

### 5. Additional Features
- Enable DHCP reservations for important devices (Ubuntu server, Raspberry Pi).
- Set up DNS resolver (Unbound).
- Install packages: pfBlockerNG (ad/DNS blocking), Suricata (IDS) if ready for next level.
- Backup config (Diagnostics → Backup/Restore).

### 6. Testing
- Verify internet access from Windows machines.
- Test DNS, ping, speed.
- Capture traffic with Wireshark to confirm NAT and rule enforcement.
- Simulate blocked traffic and check logs.

## Screenshots

![pfSense Dashboard](screenshots/pfsense-dashboard.png)  
![Interface Assignment](screenshots/interface-setup.png)  
![Firewall Rules](screenshots/firewall-rules.png)  
![DHCP Leases](screenshots/dhcp-leases.png)  
![Traffic Graph](screenshots/traffic-graph.png)

*(Upload your actual screenshots to a `screenshots/` subfolder)*

## Challenges & Solutions
- **Challenge**: No internet after install → Solution: Correctly assigned WAN/LAN interfaces and verified upstream connection.
- **Challenge**: Double-NAT issues → Solution: Used different subnet (e.g., 10.0.0.0/24) for lab LAN.
- **Challenge**: Locked myself out → Solution: Console access to reset rules or IP.

## Lessons Learned
- Proper interface assignment and rule order are critical.
- Logging and traffic graphs provide excellent visibility for troubleshooting and monitoring.
- Firewall placement is the first line of defense in any network.
- pfSense is lightweight yet powerful — perfect for home labs and small business setups.

## SOC Analyst Relevance
This project builds essential skills for SOC work:
- Understanding perimeter controls and traffic flow
- Reading firewall logs during investigations
- Implementing basic network segmentation to contain breaches
- Collaborating on rule changes for incident response
- Visualizing traffic patterns to spot anomalies

**Next Steps**:
- Add Suricata IDS rules.
- Integrate pfSense logs with Wazuh.
- Simulate port scans and test blocking/detection.

---

**Status**: Complete (Initial Setup)  
**Time Spent**: ~2 hours  
**Files/Configs**: Exported config backup in this folder (remove sensitive info before public sharing).

**Ties to Certifications**: Directly supports A+ networking/troubleshooting and Security+ firewall & network security objectives. Great foundation for real support tickets at CoolUnderFire Cybersecurity LLC.
