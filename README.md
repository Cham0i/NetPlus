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


# PORTS AND PROTOCOLS

Link Aggregation Control Protocol (LACP): NIC Teaming with Cisco switches  IEEE 802.3ad  

# TERMINOLOGY

Cycle Redundancy Check Error : The check for redundancy tested false meaning data was corrupted or changed without permission.

Neighbor Discovery Protocol: The Ipv6 version of ARP

Tx means Transmission and Rx means Reception

Carrier Sense Multiple Access/ Collision Detection (CSMA/CD): A method of exchanging data commonly used in BUS coaxial networks. It ensures that data isn't bumping into each other by designating specific times for data to be transmitted between devices. 

Medium Dependant Interface vs MDIX (crossover): A MDI NIC has pins 1 and 2 for Tx and 3, 6 Rx. A MDIX NIC has 1, 2 Rx and 3, 4 Tx. Typically end devices have MDI NICs and switches have MDIX NICs. This is the reason why ethernet cables don't need to have A code and B code ends (crossover cables). A crossover cable would be required in order to make end devices (which both use MDI NICs) communicate with each other.

IP Scanner:  It gathers information about their hostnames, IP addresses, MAC addresses, ping, ports, and NETBios information

Common Vulnerabilities and Exposures (CVE): Database of vulnerabilities operated by the MITRE corp.
