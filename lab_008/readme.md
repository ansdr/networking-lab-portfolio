Lab_008 Using VRFs to support multi-tenancy across sites

### Usecase:

Two Enterprise clients - Cisco and Dell connect to their branch offices using the same Service Provider(SP) network. The enterprises use the same subnets within their enterprise and are going to use the same SP network. So the requirement is to segment these L3 networks and also to keep each of the enterprises’ routing table secure. 

### Solution:

This is a classic use case of using VRF within the SP network on the PE routers. Here, I have created two VRFs on the PE routers - VRF CISCO and VRF DELL. The Cisco sites and the Dell sites are now able to connect to the overlapping subnets on their respective branches all the while keeping the entire traffic - data and control plane separate, thereby ensuring segmentation and security as well.

### Configurations:

The Cisco Sites use the RIP protocol to advertise the routes across the branches.

The Dell Sites use the EIGRP protocol to advertise their routes.

The SP Provider Edges use both RIP And EIGRP for advertisements. The routing tables are maintained separately for the clients using VRF.
