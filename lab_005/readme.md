This project builds on previous DHCP relay concepts by introducing VLANs for network segmentation:

- Created VLANs 10 (STAFF) and 20 (GUEST), 30 (SERVERS) on the switch
- Configured Router R1 with subinterfaces for each VLAN to route traffic and relay DHCP requests.
- Set Router R2 as the DHCP server with distinct address pools for each VLAN.
- Verified that devices in different VLANs obtain appropriate IP addresses and communicate across VLANs via inter-VLAN routing.
