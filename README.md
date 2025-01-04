# NetPlus

Every computer has a IP address that uniquely identifies it in a logical topology.

[alt text]()

The IP address has two parts a Network ID and a Host ID. The Network ID is the number that represents which network the device is a part of and the Host ID represents the unique device among other devices in the same network. Two devices in the same network will have the same Network ID, but they will each have different Host IDs. Devices in different networks will have different Network IDs and therefore can have the same Host IDs without any issues. How do we determine which is the Network ID and which is the Host ID? Subnet Masks! The Subnet Mask is written in the same format as an IP address, but the bits that are "on" (1) represent the bits that we assign to be part of the Network ID while the bits that are "off" (0) represent the bits that we assign to be part of the Host ID. 

A much simpler way to represent the subnet mask is by writting the number of bits that are included in the Host ID. This is called CIDR notation (pronounced "sigh-der"). 

/8, /16, and /24 are the easiest CIDRs because they perfectly represent the 1st, 2nd, and 3rd octets. 

[alt text]()

However, things get tricky when the subnet mask designates a number that is not 255 or 0. This means that the point at which the NID ends and HID starts is within an octet. 
