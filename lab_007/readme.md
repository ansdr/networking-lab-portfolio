# Lab_007: Wireless LAN with APs and WLC – README

Welcome to **Lab_007: Wireless LAN using APs and WLC**!  
In this project, I designed, configured, and troubleshooted a secure, multi-VLAN wireless network using Lightweight APs, a Wireless LAN Controller (WLC), trunked switching, VLANs, and centralized DHCP—mimicking a real enterprise campus environment.

---

## 📝 Overview

I deployed a Wi-Fi network where:

- Management and client (staff, guest) networks are logically separated by VLANs.
- Access Points (APs) joined a WLC via a Management VLAN.
- SSIDs were mapped to client VLANs and properly tagged across trunks.
- DHCP was delivered through central relay for all VLANs.
- Switch trunking, router-on-a-stick, and AP/WLC concepts were configured and validated.

---

## 🏗️ Topology

This setup included:

- A **Router** performing router-on-a-stick with subinterfaces for each VLAN.
- A **Layer 2 Switch** with trunk ports connecting to AP, WLC, and router; access ports for management devices.
- A **WLC** configured with management and dynamic interfaces.
- **Lightweight APs** connected via management VLAN and serving multiple VLANs on Wi-Fi.
- A **DHCP Server** located in the management VLAN, serving IPs to all VLANs via relay.
- End-user devices connecting wirelessly using SSIDs.

---

## 🌐 VLAN Plan

| VLAN | Name        | Purpose                | Subnet            |
|------|-------------|------------------------|-------------------|
| 99   | MGMT_VLAN   | WLC, APs, IT devices   | 10.99.0.0/16      |
| 10   | STAFF       | SSID 'STAFF'           | 192.168.10.0/24   |
| 20   | GUEST       | SSID 'GUEST'           | 192.168.20.0/24   |

---

## ⚙️ Configuration Highlights

### Switch Trunks

- Configured all trunk ports (towards APs, WLC, and router) with native VLAN 99.
- Allowed VLANs 10, 20, 30, and 99 on trunks.
- Ensured trunks used 802.1Q encapsulation.

### Router 'on a Stick'

- Created subinterfaces for VLANs 10, 20, and 99.
- Configured encapsulation dot1Q with VLAN IDs.
- Assigned IP addresses on each subinterface corresponding to VLAN subnets.
- Applied `ip helper-address` on client VLAN interfaces pointing to DHCP server IP in mgmt VLAN.

### DHCP Server

- Connected as an access port in VLAN 99.
- Configured DHCP pools for management, staff, and guest networks.

### WLC Configuration

- Set management interface in VLAN 99.
- Created dynamic interfaces for VLAN 10 (STAFF) and VLAN 20 (GUEST).
- Mapped SSIDs to their respective VLAN dynamic interfaces (no SSIDs were mapped to management VLAN).

### AP Configuration

- Verified APs obtained IP addresses from management VLAN DHCP pool.
- Confirmed AP uplinks were trunk ports carrying all required VLANs.
- Ensured client wireless traffic was tagged properly according to mapped VLANs.

---

## 🚦 Validation and Testing

- Confirmed wireless clients connecting to the STAFF SSID were assigned IP addresses in the 192.168.10.x subnet.
- Verified APs and the WLC had IP addresses in the 10.99.x.x management subnet.
- Ensured wireless client traffic remained segregated from management traffic.
- Validated router subinterfaces were up and forwarding traffic correctly.
- Tested DHCP relay functionality and address assignment across VLANs.
- Used Packet Tracer tools to simulate roaming and verify trunk/tagging behavior.

---

## 🛡️ Key Lessons Learned

- Keeping management VLAN separate from client VLANs is essential for security.
- Proper trunk port configuration and VLAN allowance are critical for wireless segmentation.
- SSID-to-VLAN mapping on the WLC ensures client traffic is tagged and routed correctly.
- DHCP relay configuration on router subinterfaces enables centralized IP management.
- Packet Tracer limitations require attention but the fundamental concepts translate to real hardware.

---

This lab solidified my understanding of enterprise wireless LAN design, VLAN-based segmentation, and the integration of APs and WLC with central DHCP support. I am now confident in setting up and troubleshooting similar wireless network scenarios in real environments.
