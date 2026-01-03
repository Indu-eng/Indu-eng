 # Internet protocols

## IPv4 address
      - this is the logical network address that every host need to participate in internet and almost all LANs.must be unique and configure properly to communicate remortly.
      - ipv4 address asigned to your LAN devices automatically by router it has DHCP sever .
      - also we assign manual IP which does not change, to servers ,printers, cctv and network devices.
      - ip address contain 32 bits  
### ipv4 address structure
      - includes network portion and host portion which is unique 
### networks and hosts
   - subnet mask: 225.225.225.0 used to identif the network on which the host is connected 
   - 10.0.0.0/8  subnet mask : 225.0.0.0
        - CIDR (network size)   subnet mask
        -/8                     255.0.0.0
        -/16                    225.225.0.0
        -/24                    225.225.225.0
        - network to communicate to another network needs to go through the router
# ipv4 and network segmentation
   ### unicast
      - one to one communication 
      - unicast host address range 1.1.1.1 to 223.255.255.255.
   ### broadcast 
      - range 255.255.255.255
      - one to all communication
      - no broadcast packet in ipv6 
   ### multicast
      - one to selected group
      -ipv4 has recerved 224.0.0.0 to 239.255.255.255 address as multicast addresses
      - routing protocols such as OSPF: open shortest parth first use multicast transmission 
      - to be a multicast client need to subscribe the multicast group( ex.224.10.10.5 each multicast group represented by a single ipv4 address )
   ### experimental
   - range 240.0.0.0- 255.255.255.255
   ### public and private ipv4 address
   #### RFC 1918 private address range
   - 10.0.0.0/8         10.0.0.0. - 10.255.255.255
   - 172.16.0.0/12      172.16.0.0 - 172.31.255.255
   - 192.168.0.0/16     192.168.0.0 - 192.168.255.255
   
