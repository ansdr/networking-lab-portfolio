### **Objective:**

Enable Layer 3 connectivity between two customer sites using BGP.

### **Topology Overview**
- Customer: DELL
- Sites: Two
    - Site-1: CE-1 (R6), LAN 10.1.1.0/24; CE-1 peers with PE-1 via eBGP.
    - Site-2: CE-2 (R7), LAN 20.1.1.0/24; CE-2 peers with PE-2 via eBGP.
- ISP Network:
    - Provider Edge (PE): PE-1 (R1, Lo0=1.1.1.1) and PE-2 (R3, Lo0=3.3.3.3), with iBGP between them.
    - Provider (P): R4 (P1), R2 (P2), R5 (P3).
    - IGP: OSPF across all 5 ISP routers with full reachability.
    - MPLS: Enabled on the P routers.
