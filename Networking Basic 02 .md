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
- ICMPv4 mainly was for error msg ,ping and other importnant function were in seperate protocol ARP, DHCP
- IPv4 need HDCP or manual configuration
- IMPv6 includes that all  instead being a seperate protocols
- IPv6 uses SLAAC stateless address autoconfiguration  so generate its own ipv6 address can work without DHCP.
## IPv4 and IPv6 coexistance
 - IETF - make rules for internet , internet protocols layer3-7
 - IEEE - make rules for network cables and wifi, physical and datalink  standards

 - IETF has make protocols and tools to migrate to ipv6 that technique can can be devided into three
    - 1 dual stack -allows ipv4 and ipv6 operate simultaniously on the same network (2001)
     - Tunneling ipv6 inside ipv4 (2002)
     - Tranlation- NAT64 router-   ipv6 to ipv4 and backword
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
 - omit the leading Zeros
 - ex: 2001:0db8:0000:1111:0000:0000:0000:0200
 - result 2001:dg8:0:1111:0:0:0:200

 - (::) can replace cotiguous strings of non or more 16 bits hextets consisting of all zeros
 - ex:  2001:db8:0:1111::200
 - this :: can only use once in a an address
 - if the address more than one cotiguous string then use this on the longest string if the strings are equal then use :: for the first string
 - 
   
