To setup DHCP Relay Agent feature on the network

In this experiment:

- **R1** is set up as a DHCP relay agent (with no local DHCP pool), forwarding DHCP requests from its LAN clients to another router.
- **R2** acts as the network’s DHCP server, serving IP addresses to devices in R1’s LAN.
- Connected PCs or end devices receive IP addresses from R2, even though they're directly attached to R1.
