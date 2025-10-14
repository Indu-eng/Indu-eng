# Azure-Region
60+region over 140 counries
## Availability Zones-(seperated data centers in a single region)
- Protection against downtime
- all connected through private fiber-optic network
- equiped with indipendent cooling ,power, networks
## Azure Sovereign Regions
### (US government services)
- Seperated instance  of Azure and physically isolated
- accessible for only authorized personnels
### Azure china
-built through the collaboration between Microsoft and 21Vianet
## Resource group
- like a folder , a container where manage the resorces
- resource can only exist in one resource group
- can exist in different regions
- resource can moove to different groups
- application can utilize multiple resorce group
## Azure subcriptions
## Management group
## Azure compute services
- Virtual Machine
  - can create VM scale sets this provide load balancing service
  - vailability sets update domain (UD)
      - when software maitenance happen other machines are available
  - and fault domain(FD)
      - keep the VMs in different FD so they all not depend on same hardware
  - Azure Virtual Desktop
  # Azure region pairs and benifits
  - Microsoft associate some azure region with another region in same geography
  - These regions support geo-replication and geo-redundency also in disaster recovery
  - but many regions are not paired and use availability zones as their primary means of redundancy.also many asuure service support geo-redundancy whether paired or not
  ## - Benifits
  - Region recovery sequence- in a outage,recovery of one region is prioratize
  - Sequential updates- strives to do  planned updates one region first and wait until stable and then after the other
  - data redundancy- to meet data redundancy requirement.
     -  paired mean it doesnt provide automatic protect,azure provide us toolsand paired region stucture but we are responsible for our own recovery plan
  
##  | Term                           | Meaning                                                                 | Who’s Responsible          |
| ------------------------------ | ----------------------------------------------------------------------- | -------------------------- |
| **Paired Region**              | Two Azure regions linked for recovery                                   | Microsoft (infrastructure) |
| **High Availability (HA)**     | Keep apps running during small outages                                  | You                        |
| **Disaster Recovery (DR)**     | Recover from large outages (region loss)                                | You                        |
| **Microsoft-managed failover** | Only for certain services (like GRS Storage), and only in extreme cases | Microsoft                  |
| **Your HA/DR Plan**            | How to replicate, back up, fail over, and recover                       | You                        |

    
   
