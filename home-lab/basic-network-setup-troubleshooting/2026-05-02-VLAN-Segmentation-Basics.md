# VLAN Basics & Network Segmentation

**Date**: May 2, 2026  
**Category**: Basic Network Setup & Troubleshooting / Network Security  
**Related To**: CompTIA A+ Core 2 (Networking), Security+ (Network Security & Segmentation), SOC Analyst (containment & least privilege)

## Objective
Configure basic VLANs to logically segment network traffic. This demonstrates network segmentation best practices, reducing broadcast domains and limiting lateral movement — a key defensive control in SOC environments.

## Environment
- **Switch/Router**: pfSense (with VLAN support) or managed switch (e.g., TP-Link or Cisco small business)
- **Devices**:
  - Trusted segment: Windows laptops (main users)
  - Test/Isolated segment: Raspberry Pi + vulnerable VMs
  - Server segment: Ubuntu desktop (Wazuh)
- **Tools**: pfSense web GUI, Wireshark (to verify separation), nmap (to test reachability)

## Step-by-Step Process

### 1. Plan VLAN Scheme
- VLAN 10: Trusted LAN (192.168.10.0/24) – Windows devices
- VLAN 20: Servers (192.168.20.0/24) – Ubuntu/Wazuh
- VLAN 99: Isolated/Test (192.168.99.0/24) – Raspberry Pi & test VMs
- Native VLAN: 1 (management, minimal use)

### 2. Configure VLANs in pfSense
1. Go to **Interfaces → Assignments → VLANs**.
2. Add new VLANs:
   - Parent Interface: LAN NIC
   - VLAN Tag: 10, Description: Trusted
   - VLAN Tag: 20, Description: Servers
   - VLAN Tag: 99, Description: Isolated
3. Create new Interfaces for each VLAN (Interfaces → Assignments).
4. Enable each interface and assign static IP (e.g., 192.168.10.1/24 for VLAN 10).
5. Enable DHCP server on each VLAN interface.

### 3. Configure Firewall Rules per VLAN
- Trusted VLAN: Allow outbound internet + access to Servers VLAN only.
- Servers VLAN: Restrict access from other VLANs.
- Isolated VLAN: Block all outbound except necessary (or internet only for testing).
- Block inter-VLAN traffic by default except explicitly allowed.

### 4. Assign Devices to VLANs
- On managed switch: Assign ports to specific VLANs (access ports).
- On pfSense: Use tagged ports for trunk links if using a real switch.
- Configure static IPs or DHCP reservations on each segment.

### 5. Testing & Verification
- Ping between devices on same VLAN → should work.
- Ping between different VLANs → should be blocked or limited.
- Use Wireshark on each segment to confirm no cross-VLAN leakage.
- Run nmap scans from one segment to another to test isolation.

## Screenshots

![VLAN Configuration in pfSense](screenshots/vlan-setup.png)  
![Interface Assignments](screenshots/vlan-interfaces.png)  
![Firewall Rules per VLAN](screenshots/vlan-firewall-rules.png)  
![Successful Intra-VLAN Ping](screenshots/same-vlan-ping.png)  
![Blocked Inter-VLAN Ping](screenshots/blocked-inter-vlan.png)

*(Upload your actual screenshots to a `screenshots/` subfolder)*

## Challenges & Solutions
- **Challenge**: Devices not getting IP on new VLAN → Solution: Enabled DHCP server on the new interface and checked trunk/access port settings.
- **Challenge**: Inter-VLAN routing still allowed → Solution: Reviewed firewall rules order (block rules first) and interface assignments.
- **Challenge**: Management access lost → Solution: Used console or temporary native VLAN access.

## Lessons Learned
- VLANs provide logical segmentation without extra hardware.
- Proper firewall rules between VLANs are just as important as the VLANs themselves.
- Testing is critical — segmentation only works if rules are enforced.
- Over-segmentation can add complexity; start simple and expand.

## SOC Analyst Relevance
Network segmentation is a core defensive technique:
- Limits lateral movement during breaches
- Contains compromised devices to one VLAN
- Makes monitoring easier (traffic stays segmented)
- Supports zero-trust principles and least privilege
- Helps investigate incidents by reducing noise across segments

This directly supports Security+ architecture and control topics and is highly valued in SOC and MSP environments.

**Next Steps**:
- Add 802.1Q trunking with a managed switch.
- Integrate VLAN logs/alerts with Wazuh.
- Simulate a compromised device and verify containment.

---

**Status**: Complete (Basics)  
**Time Spent**: ~2–3 hours  
**Files/Configs**: Screenshots + exported pfSense VLAN config (anonymized).

**Ties to Certifications**: Reinforces A+ networking and Security+ segmentation/firewall objectives. Excellent real-world skill for CoolUnderFire Cybersecurity support requests.
