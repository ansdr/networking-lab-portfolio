
## File Descriptions

### lab_004_VLAN_IntervlanRouting.pkt  
- Basic VLAN segmentation and router-on-a-stick inter-VLAN routing with VLANs 10 and 20.
- Includes configuration of switch VLANs, trunk port, router subinterfaces, and static IP PCs.

### lab_004_VLAN_Scaling.pkt  
- Added VLAN 30 and VLAN 40 to extend segmentation.
- Configured additional switch ports and router subinterfaces for new VLANs.

### lab_004_acl.pkt  
- Implemented Access Control Lists (ACLs) on router to restrict traffic.
- Example: Blocked VLAN 20 from accessing VLAN 10 while allowing other traffic.

### lab_004_routing.pkt  
- Introduced a third router linked to Lab_004 network for expanded subnet routing.
- Configured static routes on both routers for cross-network communication.

### lab_004_server.pkt  
- Connected a server in VLAN 10 hosting network services (e.g., HTTP).
- Validated access from other VLANs and tested connectivity restrictions.

---

## Usage Notes

- Open the `.pkt` files in Cisco Packet Tracer to explore configurations.
- Review router and switch CLI for commands related to VLANs, ACLs, routing, and DHCP (if applicable).
- Use ping and traceroute commands between devices to verify connectivity and policies.
