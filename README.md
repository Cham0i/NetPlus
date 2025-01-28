# NetPlus

1) SUBNETTING
2) NETWORK OPERATIONS
3) PORTS
4) TERMINOLOGY

# SUBNETTING

Every computer has a IP address that uniquely identifies it in a logical topology.

[alt text]()

The IP address has two parts a Network ID and a Host ID. The Network ID is the number that represents which network the device is a part of and the Host ID represents the unique device among other devices in the same network. Two devices in the same network will have the same Network ID, but they will each have different Host IDs. Devices in different networks will have different Network IDs and therefore can have the same Host IDs without any issues. How do we determine which is the Network ID and which is the Host ID? Subnet Masks! The Subnet Mask is written in the same format as an IP address, but the bits that are "on" (1) represent the bits that we assign to be part of the Network ID while the bits that are "off" (0) represent the bits that we assign to be part of the Host ID. 

A much simpler way to represent the subnet mask is by writting the number of bits that are included in the Host ID. This is called CIDR notation (pronounced "sigh-der"). 

/8, /16, and /24 are the easiest CIDRs because they perfectly represent the 1st, 2nd, and 3rd octets. 

[alt text]()

However, things get tricky when the subnet mask designates a number that is not 255 or 0. This means that the point at which the NID ends and HID starts is within an octet. 

# NETWORK OPERATIONS

communications within a LAN

communications between networks

RARP (Reverse Address Resolution Protocol) Maps a MAC to an IP address. This is the oppossite of ARP which maps a IP address to a MAC. Both work by broadcasting and listening to a response by the device that matches the MAC or IP.

Network auxiliaries
NIC Teaming: It allows multiple NICs to operate as a single virtual NIC. It is used as a way to load balance traffic and provide redundancy
Content Delivery Network: The use of edge servers that have a cache of the information stored in the original server in order to improve delivery speed. Basically if you live in the south you will connect to the U.S south server instead of the Taiwan server.

## Routing Technology

[Administrative distance, Measurement used by protocol]

Distance vector routing constantly advertise their routing tables, while Linked state routing only advertises changes to their tables.

Routine Information Protocol (RIP): [120/hop] Distance vector. Uses the number of nodes between the Tx and Rx, or hop count, to determine favorability.
Open Shortest Path First (OSPF): [110,X] Link state. Uses Dijkstra algorithim to determine favorability
Enhanced Interior Gateway Routing Protocol (EIGRP): [90/x] Distance vector and linked state routing hybrid.
Border Gateway Protocol (BGP): Path vector protocol. Used between different autonomous systems on the internet???
Intermediate System to Intermediate System (IS-IS): Linked state. Mostly used between ISPs.

## Network Topologies

Hub and spoke/ Star. Everything is connected to one source and only that source.
Ad Hoc/ P2P. Connections are decentralized
Mesh. Everything is connected to everything else
Point to point is direct conection between two computers
Tree/ Hierarchy. self explanitory

https://www.geeksforgeeks.org/simple-network-management-protocol-snmp/

Channels 1, 6, and 11 are the only channels that don't overlap in WAPs.





# PORTS AND PROTOCOLS

Link Aggregation Control Protocol (LACP): NIC Teaming with Cisco switches  IEEE 802.3ad  

Spanning Tree Protocol is used to create a topology without loops.

# TERMINOLOGY

Cycle Redundancy Check Error : The check for redundancy tested false meaning data was corrupted or changed without permission.

Neighbor Discovery Protocol: The Ipv6 version of ARP

Tx means Transmission and Rx means Reception

Carrier Sense Multiple Access/ Collision Detection (CSMA/CD): A method of exchanging data commonly used in BUS coaxial networks. It ensures that data isn't bumping into each other by designating specific times for data to be transmitted between devices. 

Medium Dependant Interface vs MDIX (crossover): A MDI NIC has pins 1 and 2 for Tx and 3, 6 Rx. A MDIX NIC has 1, 2 Rx and 3, 4 Tx. Typically end devices have MDI NICs and switches have MDIX NICs. This is the reason why ethernet cables don't need to have A code and B code ends (crossover cables). A crossover cable would be required in order to make end devices (which both use MDI NICs) communicate with each other.

IP Scanner:  It gathers information about their hostnames, IP addresses, MAC addresses, ping, ports, and NETBios information

Common Vulnerabilities and Exposures (CVE): Database of vulnerabilities operated by the MITRE corp.

Port mirroring: Copies packets and sends the copy for its contents to be investigated.

Split Tunnel VPN only route packets that are within the subnet. While full tunnel VPN have every packet sent through the VPN
