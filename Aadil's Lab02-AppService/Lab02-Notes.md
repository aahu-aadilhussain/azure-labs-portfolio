# Lab 02 — Azure App Service
**Name:** Aadil Hussain
**Date Started:** 31 March 2026
**Status:** 🔄 In Progress

---

## What I Am Building
A web application deployed on Azure App Service without
managing any servers or operating systems. The app will
be live at a free azurewebsites.net domain automatically
provided by Azure.

---

## Key Concepts

### IaaS vs PaaS
- Lab 1 was IaaS — I managed the VM, OS, and web server myself
- Lab 2 is PaaS — Azure manages everything, I just deploy code
- PaaS is faster, easier, and preferred for most web applications

### App Service Plan
- The compute resource that powers the web app
- Like choosing a VM size but for App Service
- Free F1 tier gives 60 minutes compute per day at zero cost
- Multiple web apps can share one App Service Plan

---

## Phase 1 — Resource Group and App Service Plan ✅

### What I Did
- Created resource group rg-lab-appservice-02 in East Asia
- Navigated to App Service Plans
- Created plan-lab-free-02 using Free F1 pricing tier
- Selected Linux as operating system

### Settings I Used
| Field | Value |
|  ---  |  ---  |
| Resource group | rg-lab-appservice-02 |
| Plan name | plan-lab-free-02 |
| Operating system | Linux |
| Region | East Asia |
| Pricing tier | Free F1 |

### What I Learned
- App Service Plan is the container for web apps
- Free F1 tier is completely free — no credit used
- Linux plans are cheaper than Windows plans
- One plan can host multiple web apps

### Screenshots
![Resource Group Created](screenshots/01-resource-group-created.png)
![App Service Plan Created](screenshots/02-app-service-plan-created.png)

---

## Phase 2 — Create Web App
🔄 Not started yet

---

## Phase 3 — Deploy Code
🔄 Not started yet

---

## Phase 4 — Configure Settings
🔄 Not started yet

---

## Phase 5 — Cleanup
🔄 Not started yet

---

## Problems I Faced
| Problem | What I Tried | How I Fixed It |

| Free F1 not available in North Europe | Tried West Europe too | Changed region to East Asia and it worked |
---

## What I Learned


---

## Cost Tracking

---