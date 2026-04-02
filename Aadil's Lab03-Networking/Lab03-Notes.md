# Lab 03 — Azure Networking — VNet and NSGs
**Name:** Aadil Hussain
**Date Started:** 2 April 2026
**Status:** 🔄 In Progress

---

## What I Am Building
A Virtual Network with two subnets — one public and one
private — with Network Security Groups controlling traffic
between them. This simulates a real production network
architecture separating web servers from databases.

---

## Key Concepts

### Virtual Network
A VNet is a private isolated network in Azure.
It is like your own office LAN but in the cloud.
Resources inside a VNet can communicate with each
other privately without going through the internet.

### Subnets
Subnets divide a VNet into smaller segments.
Public subnet hosts internet facing resources.
Private subnet hosts backend resources like databases.
This separation improves security significantly.

### CIDR Notation
10.0.0.0/16 = Entire VNet — 65536 IP addresses
10.0.1.0/24 = Public subnet — 256 IP addresses
10.0.2.0/24 = Private subnet — 256 IP addresses
Azure reserves 5 IPs per subnet automatically.

### Network Security Group
NSG is Azure's virtual firewall.
It controls inbound and outbound traffic.
Rules have priority — lower number checked first.
Each rule allows or denies specific traffic.

---

## Phase 1 — Resource Group and VNet ✅ COMPLETED

### What I Did
- Searched for Resource Groups in Azure Portal
- Created rg-lab-network-03 in North Europe
- Navigated to Virtual Networks and clicked Create
- Named the VNet vnet-lab-03
- Left IP address space as 10.0.0.0/16
- Deleted the default subnet
- Added snet-public with range 10.0.1.0/24
- Added snet-private with range 10.0.2.0/24
- Reviewed settings and clicked Create
- Waited 1 minute for deployment
- Verified both subnets visible in VNet Subnets page

### Settings I Used
| Field | Value |
|---|---|
| Resource group | rg-lab-network-03 |
| VNet name | vnet-lab-03 |
| Region | North Europe |
| Address space | 10.0.0.0/16 |
| Public subnet name | snet-public |
| Public subnet range | 10.0.1.0/24 |
| Private subnet name | snet-private |
| Private subnet range | 10.0.2.0/24 |

### Why These IP Ranges
10.0.0.0/16 gives the VNet 65536 IP addresses total.
Splitting into /24 subnets gives 256 IPs each.
Azure reserves 5 IPs per subnet leaving 251 usable.
Using 10.0.1.x for public and 10.0.2.x for private
makes the architecture easy to read and understand.

### What I Learned
- VNet is Azure's private isolated network
- Address space defines the total IP pool for the VNet
- Subnets segment the VNet into logical zones
- Public subnet is for resources facing the internet
- Private subnet is for backend resources like databases
- CIDR /16 gives 65536 addresses
- CIDR /24 gives 256 addresses per subnet
- Azure always reserves 5 IP addresses per subnet
- VNet creation is completely free in Azure

### Screenshots
![Resource Group Created](screenshots/01-resource-group-created.png)
![VNet Subnets Configured](screenshots/02-vnet-subnets-configured.png)
![VNet Validation](screenshots/03-vnet-validation.png)
![VNet Created](screenshots/04-vnet-created.png)
![Subnets Verified](screenshots/05-vnet-subnets-verified.png)

---

## Phase 2 — Network Security Groups
🔄 Not started yet

---

## Phase 3 — Associate NSGs to Subnets
🔄 Not started yet

---

## Phase 4 — Verify and Test
🔄 Not started yet

---

## Phase 5 — Cleanup
🔄 Not started yet

---

## Problems I Faced
| Problem | What I Tried | How I Fixed It |
|---|---|---|
| Write here | Write here | Write here |

---

## What I Learned
Fill at the end of the lab

---

## Cost Tracking
| Resource | Cost |
|---|---|
| Virtual Network | Free |
| Subnets | Free |
| NSGs | Free |
| Total | $0.00 |

---

## My Confidence Rating After This Lab
| Skill | Before | After |
|---|---|---|
| Understanding VNets | 1 | fill in |
| Configuring subnets | 1 | fill in |
| Creating NSG rules | 1 | fill in |
| Understanding CIDR | 1 | fill in |
| Network security concepts | 1 | fill in |

---

## What I Would Do Differently Next Time
Fill at the end of the lab