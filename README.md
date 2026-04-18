# ☁️ Azure Cloud Portfolio
### Aadil Hussain | Cloud Engineer in Training | Doha, Qatar 🇶🇦

[![AZ-900 In Progress](https://img.shields.io/badge/AZ--900-In%20Progress-0078D4?style=flat-square&logo=microsoftazure)](https://learn.microsoft.com/en-us/certifications/azure-fundamentals/)
[![Labs](https://img.shields.io/badge/Labs%20Completed-8%20of%208-brightgreen?style=flat-square)]()
[![GitHub Profile](https://img.shields.io/badge/GitHub-aahu--aadilhussain-181717?style=flat-square&logo=github)](https://github.com/aahu-aadilhussain)

---

## What Is This Portfolio

This repository documents **8 hands-on Microsoft Azure projects**
completed during a structured 30-day self-study program using
a **real live Azure subscription** — not simulations or sandboxes.

### What Makes This Different
Most beginners follow tutorials and watch videos.
This portfolio shows **real infrastructure built and destroyed**
with real problems encountered and real solutions applied.

Every lab folder contains:
- 📋 Complete step-by-step notes in Markdown
- 📸 Screenshots from Azure Portal at every stage
- ⚠️ Real problems faced and exactly how they were solved
- 💡 Key concepts explained in plain English
- 💰 Cost tracking for every resource created

---

## Projects Overview

### 💻 Compute

**Lab 01 — Linux Virtual Machine**
Deployed Ubuntu Server 22.04 on Azure, configured SSH key
authentication, installed Nginx web server and served a live
custom website accessible from anywhere in the world.

Key skills: VM deployment · SSH keys · NSG rules · Linux commands · Nginx

**Lab 02 — Azure App Service**
Deployed a PHP web application using Azure App Service PaaS.
Used Kudu ZIP deployment after VS Code extension failed —
demonstrating real troubleshooting ability.

Key skills: PaaS deployment · App Service plans · Kudu · Environment variables

---

### 🌐 Networking

**Lab 03 — Virtual Network Architecture**
Built a segmented network with public and private subnets,
attached Network Security Groups to control traffic flow
between tiers — simulating real production architecture.

Key skills: VNet · CIDR addressing · NSG rules · Network Watcher · Defence in depth

**Lab 04 — High Availability Load Balancer**
Deployed two VMs behind a Standard Load Balancer with health
probes. Demonstrated automatic failover by stopping one VM
and confirming all traffic switched to the healthy VM.

Key skills: Load Balancer · Backend pools · Health probes · Availability Sets · Failover

---

### 🗄️ Storage and Databases

**Lab 05 — Blob Storage and Static Website**
Created storage containers with different access levels,
generated SAS tokens for time-limited secure file sharing,
and hosted a static website directly from Blob Storage.

Key skills: Blob Storage · SAS tokens · Access tiers · Static website hosting

**Lab 06 — Azure SQL Database**
Provisioned a managed SQL Database using the free offer,
created tables, inserted data and ran queries including
SELECT WHERE GROUP BY JOIN and UPDATE operations.

Key skills: Azure SQL · T-SQL · Query Editor · Firewall rules · Connection strings

---

### 🔐 Security and Identity

**Lab 07 — RBAC and Identity Management**
Created test users in Microsoft Entra ID, assigned Reader
and Contributor roles at different scopes, and verified the
principle of least privilege by signing in as the test user.

Key skills: Microsoft Entra ID · RBAC · Role assignments · Least privilege · IAM

**Lab 08 — Azure Key Vault**
Created a Key Vault with RBAC permission model, stored
database passwords API keys and connection strings as secrets,
managed secret versions and configured access for test users.

Key skills: Key Vault · Secrets management · Access policies · Soft delete · Versioning

---

## Skills Demonstrated
Compute      Azure VMs · App Service · Ubuntu Linux · Nginx · SSH
Networking   VNet · Subnets · NSG · Load Balancer · High Availability
Storage      Blob Storage · SAS Tokens · Access Tiers · Static Hosting
Database     Azure SQL · T-SQL · Query Editor · Firewall Rules
Security     Entra ID · RBAC · Key Vault · Least Privilege
DevOps       Git · GitHub · Markdown · VS Code · Azure Portal
---

## Certifications in Progress

| Exam | Name | Status |
|---|---|---|
| AZ-900 | Azure Fundamentals | 🎯 Studying |
| AZ-104 | Azure Administrator | 📅 Planned |

---

## Repository Structure
azure-labs-portfolio/
├── Aadil's Lab01-VirtualMachine/
│   ├── Lab01-Notes.md
│   └── screenshots/
├── Aadil's Lab02-AppService/
│   ├── Lab02-Notes.md
│   └── screenshots/
├── Aadil's Lab03-Networking/
│   ├── Lab03-Notes.md
│   └── screenshots/
├── Aadil's Lab04-LoadBalancer/
│   ├── Lab04-Notes.md
│   └── screenshots/
├── Aadil's Lab05-BlobStorage/
│   ├── Lab05-Notes.md
│   └── screenshots/
├── Aadil's Lab06-SQLDatabase/
│   ├── Lab06-Notes.md
│   └── screenshots/
├── Aadil's Lab07-RBAC/
│   ├── Lab07-Notes.md
│   └── screenshots/
└── Aadil's Lab08-KeyVault/
├── Lab08-Notes.md
└── screenshots/
---

## About the Author

**Aadil Hussain**
Doha, Qatar 🇶🇦
Open to cloud engineer and IT infrastructure roles in Qatar and GCC

[GitHub Profile](https://github.com/aahu-aadilhussain) •
[LinkedIn](www.linkedin.com/in/aadil-hussain-aahu974)

---

*Built on a real Microsoft Azure subscription — every resource created, configured, tested and documented from scratch*
