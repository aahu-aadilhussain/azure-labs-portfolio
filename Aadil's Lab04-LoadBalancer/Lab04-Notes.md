# Lab 04 — Azure Load Balancer
**Name:** Aadil Hussain
**Date Started:** 3 April 2026
**Status:** 🔄 In Progress

---

## What I Am Building
Two Virtual Machines running Nginx web server behind
an Azure Load Balancer. Traffic from the internet gets
distributed evenly between both VMs automatically.
This demonstrates high availability — if one VM fails
the other continues serving traffic with no downtime.

---

## Key Concepts

### What is a Load Balancer
A Load Balancer distributes incoming traffic across
multiple servers. It works at Layer 4 of the OSI model
meaning it routes traffic based on IP and port only
without reading the content of the traffic.

### Why Load Balancing Matters
Single server = single point of failure
If that server goes down — website is down
Load Balancer + 2 servers = high availability
If one server goes down — other continues working

### Key Components
Frontend IP — The public IP users connect to
Backend Pool — The VMs that receive traffic
Health Probe — Checks if each VM is healthy
Load Balancing Rule — Defines how traffic is routed

### How Health Probes Work
The Load Balancer sends a request to each VM every 5 seconds
If a VM does not respond — it is marked unhealthy
Traffic stops going to unhealthy VMs automatically
When VM recovers — traffic resumes automatically

---

## Phase 1 — Resource Group and Network Setup ✅ COMPLETED

### What I Did
- Created resource group rg-lab-loadbalancer-04 in North Europe
- Created Virtual Network vnet-lab-04 with address space 10.0.0.0/16
- Added subnet snet-backend with range 10.0.1.0/24
- This subnet will host both backend VMs

### Settings I Used
| Field | Value |
|---|---|
| Resource group | rg-lab-loadbalancer-04 |
| VNet name | vnet-lab-04 |
| Region | North Europe |
| Address space | 10.0.0.0/16 |
| Subnet name | snet-backend |
| Subnet range | 10.0.1.0/24 |

### Why One Subnet This Time
In Lab 03 we had public and private subnets.
In Lab 04 both VMs are in the same subnet because
they both serve the same purpose — web servers.
The Load Balancer sits in front of them handling
the public traffic separation.

### What I Learned
- Load Balancer architecture needs VMs in same subnet
- Backend pool VMs share the same network segment
- VNet setup is the foundation for every Azure lab
- Same CIDR concepts from Lab 03 apply here

### Screenshots
![Resource Group Created](screenshots/01-resource-group-created.png)
![VNet Created](screenshots/02-vnet-created.png)

---

## Phase 2 — Create Two Virtual Machines
🔄 Not started yet

---

## Phase 3 — Create the Load Balancer
🔄 Not started yet

---

## Phase 4 — Test Load Balancing
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
Fill at the end

---

## Cost Tracking
| Resource | Cost |
|---|---|
| VM 1 Standard_B2ts_v2 | ~$0.01/hr |
| VM 2 Standard_B2ts_v2 | ~$0.01/hr |
| Load Balancer Standard | ~$0.025/hr |
| Public IP | ~$0.004/hr |
| Total for 2 hr lab | ~$0.10 |

---

## My Confidence Rating After This Lab
| Skill | Before | After |
|---|---|---|
| Understanding load balancing | 1 | fill in |
| Creating Azure Load Balancer | 1 | fill in |
| Configuring backend pools | 1 | fill in |
| Setting up health probes | 1 | fill in |
| High availability concepts | 1 | fill in |

---

## What I Would Do Differently Next Time
Fill at the end