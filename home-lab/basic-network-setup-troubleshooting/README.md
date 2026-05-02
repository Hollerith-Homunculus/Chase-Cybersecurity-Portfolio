# Basic Network Setup & Troubleshooting

**Folder Purpose**  
This folder documents foundational networking projects using my home lab hardware. These exercises build core skills in network configuration, connectivity troubleshooting, and basic security — directly supporting CompTIA A+ Core 2 (Networking & Troubleshooting) and providing the foundation for Security+ and junior SOC Analyst work (network visibility, segmentation, and anomaly detection).

**Lab Hardware Used**
- Ubuntu desktop (server/gateway)
- 2× Windows 11 laptops + 2× Windows 10 laptops (endpoints)
- Raspberry Pi
- MacBook Air
- pfSense (virtualized or dedicated firewall appliance)
- VirtualBox for additional test VMs when needed

## Projects / Documents

| Date       | Project / Topic                        | Key Skills Demonstrated                          | Status      | Link |
|------------|----------------------------------------|--------------------------------------------------|-------------|------|
| 2026-04-xx | pfSense Firewall Installation & Basic Rules | Firewall deployment, NAT, outbound rules        | Complete    | [pfSense-Setup.md](./pfSense-Setup.md) |
| 2026-05-xx | Network Segmentation & VLAN Basics     | Logical separation, inter-VLAN routing          | In Progress | [VLAN-Segmentation.md](./VLAN-Segmentation.md) |
| 2026-05-xx | Wireshark Packet Capture & Analysis    | Traffic inspection, protocol analysis           | Complete    | [Wireshark-Basics.md](./Wireshark-Basics.md) |
| 2026-05-xx | Common Connectivity Troubleshooting    | IP config, DNS, DHCP issues                     | Complete    | [Troubleshooting-Common-Issues.md](./Troubleshooting-Common-Issues.md) |
| ...        | ...                                    | ...                                              | ...         | ... |

*(Keep this table updated as you add more files)*

## Lab Network Architecture Overview
- **Internet/WAN** → pfSense firewall → Internal LAN
- **LAN Segments**: Main trusted network + isolated test segment (for vulnerable VMs or Raspberry Pi)
- **Services**: DHCP & DNS on pfSense or Ubuntu, static IPs for servers
- **Monitoring**: Wireshark captures on key segments + Wazuh network module

**Simple Text Diagram**:
Internet
|
pfSense Firewall (NAT + Rules)
|
├── Trusted LAN (Windows laptops)
├── Test/Isolated Segment (Raspberry Pi + VMs)
└── Management (Ubuntu Server)


## Skills Demonstrated
- Installing and configuring a perimeter firewall (pfSense)
- Basic firewall rules (allow/deny, port forwarding)
- Network troubleshooting methodology (identify, test, resolve, verify)
- Packet analysis with Wireshark (HTTP, DNS, TCP handshakes)
- IP addressing, subnetting, DHCP, DNS resolution
- Basic network hardening and segmentation concepts

## SOC Analyst Relevance
Strong networking fundamentals are essential for SOC roles:
- Understanding normal traffic patterns to spot anomalies
- Investigating network-based alerts
- Implementing basic segmentation to limit lateral movement
- Reading packet captures during incident response
- Collaborating with network teams on firewall changes

These projects reinforce A+ troubleshooting while laying groundwork for Security+ Network Security and CySA+ monitoring domains.

## Tools Used
- pfSense
- Wireshark
- nmap
- ipconfig / ifconfig / ip addr
- ping, traceroute, nslookup
- Wazuh (for network log correlation)

---

**Last Updated**: May 2026  
**Goal**: Document all core A+ networking topics + add SOC-focused scenarios (e.g., detecting port scans or C2 traffic).

See parent folder (`Home-Lab-Projects`) for overall lab context and Wazuh SIEM integration.  
Main portfolio README for HTB, TryHackMe, and CoolUnderFire Cybersecurity LLC work.
