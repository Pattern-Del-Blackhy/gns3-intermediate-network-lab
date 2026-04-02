# gns3-intermediate-network-lab
Networking Lab Project – Intermediate GNS3 Topology with Real Network Integration

## Overview
This repository contains a fully documented **intermediate networking lab** built in **GNS3**, integrating simulated devices with a real network. The lab demonstrates practical networking concepts and allows hands-on verification of connectivity, NAT, and DNS using **Wireshark**.

The topology consists of **6 VPCS**, **2 default switches**, a **Cisco 7200 router (c7200-adventerprisek9)**, and a **Cloud node** connecting to the real network. The lab validates **inter-VLAN routing**, **DHCP**, **NAT**, and **DNS resolution**.

---

## Topology & Features

- **Devices:**
  - 6 Virtual PCs (VPCS) across 2 VLANs
  - 2 Default Switches
  - Cisco 7200 Router (c7200-adventerprisek9)
  - Cloud Node connected to real network

- **Router Configuration:**
  - DHCP Server
  - NAT Overload (PAT) for internet access
  - Inter-VLAN Routing
  - DNS Proxy / Forwarding

- **Real Network Integration:**
  - VPCS can access the internet through the router and Cloud node
  - Verified by pinging external domains:
    - `Google.com`
    - `ait.edu.gh`

- **Traffic Analysis:**
  - Captured packets using **Wireshark**
  - Verified:
    - NAT translations (inside local IP → outside global IP)
    - DNS query and response
    - ICMP traffic to external IPs

---

## Learning Outcomes

This lab demonstrates practical skills including:

- VLAN configuration and inter-VLAN communication
- DHCP setup and dynamic IP allocation
- NAT configuration for internet access
- DNS forwarding and verification
- Traffic capture and analysis with Wireshark
- Bridging simulated networks with real-world networks

---

## Usage Instructions

1. Open the topology in **GNS3**.
2. Ensure each VPCS has IP addresses assigned via DHCP or manually:
   - VLAN1: `192.168.10.0/24`
   - VLAN2: `192.168.20.0/24`
3. Confirm default gateways:
   - VLAN1 PCs → `192.168.10.1`
   - VLAN2 PCs → `192.168.20.1`
4. Set DNS for each VPCS to point to the router:
   ```bash
   ip dns 192.168.10.1   # VLAN1
   ip dns 192.168.20.1   # VLAN2
