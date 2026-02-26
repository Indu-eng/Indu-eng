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

  ### Routing to the internet
   ### private ipv4 address and network addres  translation
    - private ipv4 address will be translated to public ipv4 address using NAT brfore routing to the internet
 ### Special use ipv4 address 
   ### loopback address 
   - 127.0.0.0 /8 or 127.0.0.1 to 127.225.225.254   more commenly identify as 127.0.0.1
   - ping command use to test connections to other hosts but it can also use to test your own device
   - ex: ping 127.0.0.1
   - this means the localhost
  ### link local address(APIPA)
  - range 169.254.0.1 to 169.254.255.254
  - this is call automatic private ip addressing this can happen in many situations like DHCP no replying , router is down etc
  - then the device randomly assigned an ip from this range
  - here no internet cant reach outside the local network
  - this only allow local communication, like 2 connected PC
  - windows uses APIPA by default
### legacy classful addressing
  - in 1981 RFC 790 defined classful addressing  to assingn ipv4 address
  -  Classs A  range (0.0.0.0/8  to 127.0.0.0/8)for extreme large network of 16 million hosts
  -  Class B range (128.0.0.0/16 to 191.255.0.0/16)for mediume network hosts more thatn 65000 per network
  -  Class C range(192.0.0.0/24 to 223.255.255.0/24) network for max 254 hosts
  -  there is also malticast as D class and experiment address E class
  -  in 1990 classful aressing replaced with classless addressing
  -  in classless addressing CIDR (this is the modern way) thsi is what we use
### RIR receive IPs from IANA to allocate to ISPs and some organizations
# IPv6 addressing format and rules
- IPv6 designed to be the successor to IPv4 it has larger 128 bit address space
- in IPv4, ICMPv4 mainly was for error msg ,ping and other importnant function were in seperate protocol ARP-address resolution , DHCP-address configuration
- IPv4 need DHCP or manual configuration
- IMPv6 includes that all  instead being a seperate protocols
- IPv6 uses SLAAC stateless address autoconfiguration  so generate its own ipv6 address can work without DHCP.
## IPv4 and IPv6 coexistance
 - IETF - make rules for internet , internet protocols layer3-7
 - IEEE - make rules for network cables and wifi, physical and datalink  standards

 - IETF has make protocols and tools to migrate to ipv6 that technique can can be devided into three
    - 1 dual stack -allows ipv4 and ipv6 operate simultaniously on the same network or devices (2001)
     - Tunneling ipv6 inside ipv4 (2002)
     - Tranlation- use NAT64 router-  translate ipv6 to ipv4 and backword
 -  goal is native ipv6 communication from sourse to destination ,so dual stack is good
## IPv6 addressing
 - providing 340 undecillion pocible address
 - x:x:x:x:x:x:x:x:
 - represented using hexadecimal numbers
 - from 0-9 and A-F not case sensitive
 - Ipv6 address are 128 bit long
 - 128/4 =16
 - bit 16 represented in one 4 hexadecimal digits
 - X: include= 4 hexadecimal digits =16 bits or we can call this hextet
 - one hexadecimal = 4 bits
### preferred format rules
 - rule 1
 - omit the leading Zeros
 - ex: 2001:0db8:0000:1111:0000:0000:0000:0200
 - result 2001:dg8:0:1111:0:0:0:200

 - rule 2
 -  (::) can replace cotiguous strings of non or more 16 bits hextets consisting of all zeros
 - ex:  2001:db8:0:1111::200
 - this :: can only use once in a an address
 - if the address more than one cotiguous string then use this on the longest string if the strings are equal then use :: for the first string
## Dynamic Addressing with DHCP-dynamic hosts confuguration protocol
### Static and dynamic addressing
   Static addressing
 - network administrator should manually confugiur network information for hosts
 - incliding following 3
 - ip address
 - subnet mask
 - default gate way- if host needs to access internet or remort network ,thisis what important
 - DNS 
 -  some devices like printers also servers firewalls routers and swiches need permenent address if that change that will not be accessible
 -  be care full and keep accurate records of which ip belongs to which host
 -  otherwise it conflict
 -  errors are more likely to ocurr

 Dynamic addressing
 - DHCP dynamic host configuration protocol is is important when users change frequently it easier to assign IPv4 address automatically
 - it automatically assign ipv4 address, subnet mask,DNS server ,default gate way and all
 - suitable for large networks with many hosts , no neeed to do mannually it prevents errors

 - DHCP server can bemany devices like a router in a home network and also
 - for enterprices, can have their own local dhcp server 
## DHCPv4 Configuration
- DHCP is a software and also DNS server also can run in any capable system linux server or windows server
- host send the broadcast 225.225.225.225. to find the DHCP, we call it DHCP discover,and it containes the MAC address as well
- then recieve DHCP offer from the DHCP server which include ip, subnet mask,default gateway
- then sends back Dhcp request to inform accept the offer
- last DHCP ACK that sent to confirm that now your mac is set to the ip

  
- so when a host start to boots after 2 week break it first send broad cast to find the DHCP server IP, so destination ip  is 225.225.225.225. and destination MAC address is FF:FF:FF:FF:FF:FF:
# Gateways to Other networks
- router provide the gateway through which host can communicate with host on a different network(internet)
- for that hosts must know the router interface ip address of where host attached
- this call default gateway
- can be configured statically or received dynamically by DHCP
- wireless router is configured to be the  DHCP server on a local network
- it automatically send the correct interface address to the its hosts as default gateway
- most Dhcp servers are configured to assing private address to the host on a internal network
- router works as the DHCP client when it connect to the IPS to obtain Public ip address.
- router receive A public IP address and Subnet mask, Default gateway, DNS servers from the IPS
- proces used to convert private IP address to internet routable Ip address call NAT 
 ## Network addresss translation
 - wireless router receives a public address from the ISP , which allows it to send and receive packets in the internet.
 - it , in turn provide private address to the local network clients.
##  The ARP Process
### same network
 - hosts need to send messsage to destination but it knows only the IP of the destination so in that case,need to usr ARPto  find the MAC adddress of the destination 
 - if the source and destination are in the same LAN, the Ethernet frame contains the source MAC and the destination MAC
 - ARP is performed by the source host to map the destination IP address to a MAC address. The source then creates an IP packet and encapsulates it inside an Ethernet frame.
 - The switch forwards the Ethernet frame based on MAC addresses only.
 - The Layer 3 IP packet contains the source IPv4 address and the destination IPv4 address.
### destination on remote network
 - when the destination on another network destination mac address will be the default gateway
 - when router receives the ethernet frame it decapsulate layer 2 information , using the destination ip4 address deside the next hop device and encapsulate nest ipv4 address in a new data link frame
 - so new destination mac would be another router mac address
 - when send data over network  layer 3- network layer contains  source ip and destination ip but ip packet can not travet directly in wire so they need to be wrape inside  layer 2 frame like ethernet.we call it as encapsulation. 
 - IP Packet → wrapped inside → Ethernet Frame
 - IP address = used to route across networks (end-to-end)
 - MAC address = used to deliver inside a local network (hop-to-hop)
### broadcast containment
 - ethernet broadcast MAC address is 48 bit address made up of ones.
 - broad cast MAC in hexadecimal notation FFFF.FFFF.FFFF
 - a sending host can use IPV4 protocole called ARP - address resolution protocol to discover a Mac address of any host on the same local network
 - IPV6 use method call neighbor discovery. (ND)
 - we use ARP when we know ip address of the receiver but dont know their MAC. we need to know the MAC to encapsulate ipv4 in a ethernet frame.
 - 1.so first PC1 send ARP request(a broadcast frame)
 - 2.then PC2 reply with ARP reply
 - 3.then pc1 store the received MAC along with their IP in a ARP table
## Routing between networks
### the needs for routing
 - limit the broad cast traffic
 - security -we dont need defferent department to access a printer in another dipartment
 - when we moving (geograpically segment)

### ip packet encapsulate in an Ethernet Frame
- most situations we want to connect with remote hosts- like other homes, business, and internet
- router connect multiple layyer 3 ,Ip networks
- swiches are based on layer 2 MAC address
- any time if the networkportion of the ip address of the sourse and destination do not match, router must be used to forward the message. then  router decapsulate the ethernet frame and read the destination address in the ip packet. then determine where to forward the message . then re encapsulate the packet back into new frame and forward
### how a message travel between a network and a within a network
- first to send in the same network,the source, build the ipv4 packet containnig the source ip address and the destination ip v 4 address
- then source check are we on same network using the subnet mask
- if yes that mean they can send the packet directly and no need to send to the default gateway
- then source going to create ethernet frame with own mac address and want to know the destination mac address asociate with the destination ip adress
-  Now source check for the ARP table, if it was not there do the ARP request and add to the ARP table.
-  then sent to the destination
-  what happen in remote destination?
-  check the ip and determine weather it is on a different network by using subnet mask
-  so then it send to default gateway
-  what is the MAC address of default gateway
-  For that check the ARP table
-  then forward the ethernet packet to the router
-  router receive tha packet and remove the ithernet header(frame) informations(source and destination mac)
-  NOW the routerdoes it job call layer 3 forwording which is routing
-  first look for the destination ip v 4 address, then look at the routing table and find ethernet to reach the address  
-  now encapsulate the frame with new ethernet frame, so the sourse mac Address will be the mac address of routher's interface card
-  this is ethernet layer 2 is for network interface card
-  now need to know the destination MAC for that check the ARP table
-  then send
### routing table 
- routing tables are not concerned with individual address of host, it contains the addresses of the networks, and the best path to reach those networks
- routing table can dynamically updated by the infor receive from other routers ,also can manually entered by the network administrator
- if a router cannot determine where to forward, it will drop it, so network admin configure a static default route that place it to the routing table ,so that packet will not be droped due to destination network not being in the routing table.
- A default route is the interface which the touter forward unknown destination ip network address.
- default route usually conencts to another router that can forwards its final destination network
### default gateway
- when a host qants send a packet to a remote network that use the default gate way, router
- a host is given the ipv4 address of the router through the default gate way address configured in its TCP/IP settings
- and use ARP to determine tha MAC address of the router
### create a LAN
- all the local networks within a LAN are under one administrative control.typically use ethernet or wireless protocols
- intranet refers to a private LAN of an organisation
### local and remote network segments
- in  a LAN  it is possible to place all the hosts underin a one local networkand or devide them up between multiple networks connections connected by a distributionlayer device
- when all the hosts are in one segment,
- Advantages of a single local segment:

  - Appropriate for simpler networks
  - Less complexity and lower network cost
  - Allows devices to be "seen" by other devices
  - Faster data transfer - more direct communication
  - Ease of device access
  - Disadvantages of a single local segment:

  - All hosts are in one broadcast domain which causes more traffic on the segment and may slow network performance
  - Harder to implement QoS
  - Harder to implement security
 
 - when placing additional hosts on a remote network
 - Advantages:
  - More appropriate for larger, more complex networks
  - Splits up broadcast domains and decreases traffic
  - Can improve performance on each segment
  - Makes the machines invisible to those on other local network segments
  - Can provide increased security
  - Can improve network organization
- Disadvantages:
  - Requires the use of routing (distribution layer)
  - Router can slow traffic between segments
  - More complexity and expense (requires a router)
### create a LAN

- ipconfig /all	  Your PC’s MAC address
- arp -a	         MAC addresses of other devices (like default gateway)
- tracert         command uses ICMP to return information about the routers that are passed as packets go from the source PC to the destination.
- Trace to a remote destination by going to one of the PCs and entering tracert followed by the URL of the web server.
