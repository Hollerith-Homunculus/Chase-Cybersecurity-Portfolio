# Wireshark Basics: Packet Capture & Analysis

**Date**: May 2, 2026  
**Category**: Basic Network Setup & Troubleshooting / Traffic Analysis  
**Related To**: CompTIA A+ Core 2 (Networking & Troubleshooting), Security+ (Network Security), SOC Analyst (alert investigation & packet-level analysis)

## Objective
Install Wireshark, perform basic packet captures, and analyze common protocols. This builds foundational skills for understanding normal network traffic and identifying anomalies — critical for SOC monitoring and incident response.

## Environment
- **Capture Machine**: Ubuntu desktop or Windows 11 laptop (with admin rights)
- **Network**: Connected to pfSense LAN or main lab network
- **Traffic Sources**: Windows laptops, Raspberry Pi, Ubuntu server, browsing, DNS queries, etc.
- **Tools**: Wireshark, terminal commands (ping, nslookup, curl)

## Step-by-Step Process

### 1. Installation
- **Windows**: Download from [wireshark.org](https://www.wireshark.org/download.html) and install (include Npcap).
- **Ubuntu**:
  ```bash
  sudo apt update
  sudo apt install wireshark -y
  # Allow non-root capture if prompted
  sudo usermod -aG wireshark $USER

  Log out and back in.
2. First Capture

Open Wireshark → Select the active network interface (e.g., Ethernet or Wi-Fi).
Click the blue shark-fin Start button.
Generate traffic:
Open browser and visit a few sites.
Run ping 8.8.8.8 and nslookup google.com.
Use curl or file downloads.

Click the red square to Stop the capture.
Save the capture file (.pcapng).

3. Basic Analysis Techniques

Filter bar examples:
http — HTTP traffic only
dns — DNS queries/responses
tcp.port == 443 — HTTPS traffic
ip.addr == 192.168.1.100 — Specific IP

Statistics:
Statistics → Conversations (top talkers)
Statistics → Protocol Hierarchy
Statistics → TCP Stream Graphs

Follow TCP Stream: Right-click a packet → Follow → TCP Stream (see full conversation).
Coloring Rules: Use default rules or customize for suspicious traffic.

4. Common Protocol Deep Dives

DNS: Queries, responses, resolution process.
TCP: Handshake (SYN, SYN-ACK, ACK), data transfer.
HTTP vs HTTPS: Visible vs encrypted payloads.
ICMP: Ping requests/replies.

5. Export & Reporting

Export objects (e.g., downloaded files).
Save filtered captures.
Add display filters and comments for documentation.

Screenshots
<img src="screenshots/wireshark-interface.png" alt="Wireshark Interface Selection">
<img src="screenshots/dns-capture.png" alt="DNS Query Capture">
<img src="screenshots/tcp-handshake.png" alt="TCP Handshake">
<img src="screenshots/follow-tcp-stream.png" alt="Follow TCP Stream">
<img src="screenshots/protocol-hierarchy.png" alt="Protocol Hierarchy">
(Upload your actual screenshots to a screenshots/ subfolder)
Challenges & Solutions

Challenge: No packets captured → Solution: Selected correct interface and ensured promiscuous mode was enabled.
Challenge: Too much noise → Solution: Used capture filters (not broadcast and not multicast) or display filters.
Challenge: Encrypted traffic hard to read → Solution: Focused on metadata (IPs, ports, timing) and TLS handshake details.

Lessons Learned

Wireshark reveals what’s really happening on the wire beyond what applications show.
Understanding normal traffic patterns is essential before spotting malicious activity.
Proper filtering prevents overwhelm in real investigations.
Combining Wireshark with firewall logs (pfSense) and SIEM (Wazuh) gives powerful visibility.

SOC Analyst Relevance
Packet analysis is a core SOC skill:

Investigating network alerts from Wazuh/SIEM
Confirming C2 communication or data exfiltration
Reconstructing incidents from captures
Validating firewall rules and segmentation
Supporting forensic investigations

This directly supports Security+ network security and prepares for CySA+ behavioral analytics.
Next Steps:

Capture and analyze a port scan (nmap).
Examine HTTPS handshake and certificate details.
Integrate captures with Wazuh alerts.


Status: Complete (Basics)
Time Spent: ~1.5–2 hours
Files: Sample capture files (.pcapng) saved in this folder (small, filtered ones only for GitHub).
Ties to Certifications: Reinforces A+ troubleshooting and Security+ monitoring objectives. Valuable for real support work at CoolUnderFire Cybersecurity LLC.
