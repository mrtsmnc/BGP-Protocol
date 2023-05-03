# BGP-Protocol
**BGP (Border Gateway Protocol) is an advanced routing protocol used by internet service providers. In BGP, autonomous system numbers are assigned to routers. The autonomous system number ranges from 1 to 65535. Numbers from 64512 to 65535 are reserved for private use and can be used by anyone. When calculating metrics to build the routing table, BGP takes into account the number of autonomous systems passed through to reach the destination. This indicates that BGP uses the Distance Vector algorithm. Unlike routing protocols that work based on autonomous systems, such as EIGRP and IGRP, BGP can also operate between routers belonging to different autonomous systems. An autonomous system number is added to the BGP update packet leaving the autonomous system. This prevents the update packet from re-entering the same autonomous system and creating a loop.


**Features of BGP:

BGP supports Classless Inter-Domain Routing (CIDR), which allows IP addresses to be summarized.
BGP uses TCP port 179 for communication.
A 19-byte packet is sent every 60 seconds using TCP port 179.
Since BGP uses TCP, authentication is not performed like in other routing protocols.
Only the changed routes are sent in update packets.
To ensure the security of the connection, access authorization is provided using Message Digest algorithm 5 (MD5).


**BGP is divided into two categories based on whether it operates within or outside of an autonomous system:

EBGP (Exterior Border Gateway Protocol)
EBGP, Exterior Border Gateway Protocol, is used for neighboring routers located in different autonomous systems to establish a connection. Network information learned from neighbors through this protocol is added to the routing table with an administrative distance value of 20.
IBGP (Interior Border Gateway Protocol)
IBGP, Interior Border Gateway Protocol, is used for neighboring routers located within the same autonomous system to establish a connection. Network information learned from neighbors through this protocol is added to the routing table with an administrative distance value of 200.

**BGP route selection is based on the following criteria:

If the next hop is unreachable, the route is discarded.
The route with the highest weight is selected.
If route weights are equal, the route with the highest local preference value is selected.
If local preference values are equal, the route with the lowest origin code is selected.
If origin codes are equal, the route is selected based on its origin, with the route learned from inside the local AS being preferred, followed by routes learned from outside the local AS, and finally routes with an unknown origin.
If the routes being selected have no origin, the route with the lowest Multi-Exit Discriminator (MED) value is selected.
If MED values are equal, routes with an external origin are preferred over routes with an internal origin.
If the selected routes have the same origin, the route closest to the IBGP neighbor is selected.
The route with the smallest IP address specified by the router ID is preferred.





