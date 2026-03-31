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

## Problems I Faced
| Problem | What I Tried | How I Fixed It |

| Free F1 not available in North Europe | Tried West Europe too | Changed region to East Asia and it worked |
---

## Phase 2 — Create Web App ✅ COMPLETED

### What I Did
- Navigated to App Services in Azure Portal
- Clicked Create then Web App
- Filled in all settings on the Basics tab
- Left all other tabs as default
- Clicked Review + create
- Clicked Create and waited 2 minutes for deployment
- Clicked Go to resource and explored the Web App overview
- Visited the default domain URL and saw 502 error
- 502 error is normal — means app is live but no code deployed yet

### Settings I Used
| Field | Value |
|---|---|
| Subscription | Azure subscription 1 |
| Resource group | rg-lab-appservice-02 |
| App name | aadil-azure-lab02 |
| Publish | Code |
| Runtime stack | PHP 8.2 |
| Operating System | Linux |
| Region | East Asia |
| App Service Plan | plan-lab-free-02 |
| Pricing tier | Free F1 |

### My Web App URL
https://aadil-azure-lab02-caaehya6c9e6gsch.eastasia-01.azurewebsites.net

### What the 502 Error Means
A 502 error at this stage is completely normal and expected.
It means the App Service is running and responding but has
no code inside it yet. Once we deploy our HTML code in
Phase 3 the 502 will disappear and our custom page will
show instead.

### Key Difference From Lab 1
| | Lab 1 VM | Lab 2 App Service |
|---|---|---|
| Access method | Public IP address | Domain name URL |
| Server setup | Manual SSH and Nginx | Automatic by Azure |
| OS management | Done by me | Done by Azure |
| Code deployment | nano editor via SSH | Azure deployment tools |
| Time to deploy | 30 minutes | 5 minutes |

### What I Learned
- Web App name must be globally unique across all Azure customers
- Azure automatically provides a free azurewebsites.net subdomain
- Runtime stack defines what programming language the app uses
- App Service Plan and Web App must be in the same region
- PaaS requires zero server management compared to IaaS
- A 502 error means the server is running but has no code yet
- No SSH no Nginx installation no Linux commands needed
- App Service is much faster to set up than a Virtual Machine

### Problems I Faced
| Problem | What I Tried | How I Fixed It |
|---|---|---|
| Missed validation and deployment screenshots | Could not go back | Noted in documentation and will not miss next time |
| 502 error on URL | Checked Azure Portal | Normal — no code deployed yet — fixed in Phase 3 |

### Screenshots
### Screenshots
![Web App Validation](screenshots/03-web-app-validation.png)
— Note: Missed this screenshot during creation —
![Web App Deployed](screenshots/04-web-app-deployed.png)
![Web App Overview](screenshots/05-web-app-overview.png)
![Default Page Live](screenshots/06-default-page-live.png)

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


## What I Learned


---

## Cost Tracking

---