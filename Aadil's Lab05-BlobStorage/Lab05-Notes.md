# Lab 05 — Azure Blob Storage
**Name:** Aadil Hussain
**Date Started:** 9 April 2026
**Status:** 🔄 In Progress

---

## What I Am Building
An Azure Storage Account with Blob Storage containers
to store files securely in the cloud. I will upload
files, configure access levels, generate SAS tokens
for secure sharing, and host a static website directly
from Azure Blob Storage.

---

## Key Concepts

### What is Azure Blob Storage
Blob stands for Binary Large Object.
It stores unstructured data like images, videos,
documents, backups, and log files.
It is object storage — not a file system.
Files are stored as objects with metadata and a URL.
It is one of the cheapest storage options in Azure.

### Storage Account
The top level container for all Azure storage services.
One storage account can have multiple containers.
Storage account name must be globally unique.
Think of it like a hard drive in the cloud.

### Containers
A container is like a folder inside the storage account.
Each container holds blobs — the actual files.
Containers have access levels — private or public.
Private means only authorized users can access files.
Public means anyone with the URL can access files.

### SAS Token
SAS stands for Shared Access Signature.
It is a time-limited secure URL to share a file.
You control what permissions it has — read write delete.
You control when it expires — 1 hour 1 day 1 week.
The file stays private but the SAS URL works temporarily.

### Blob Tiers
Hot tier — frequently accessed data — higher cost
Cool tier — infrequently accessed — lower cost
Archive tier — rarely accessed — lowest cost
You can move blobs between tiers to save money.

### Static Website Hosting
Azure Blob Storage can serve HTML CSS JS files directly.
No web server needed — Azure handles everything.
You get a free URL like storageaccount.web.core.windows.net
Perfect for simple websites and documentation sites.

---

## Phase 1 — Create Storage Account
🔄 Not started yet

---

## Phase 2 — Create Containers and Upload Files
🔄 Not started yet

---

## Phase 3 — Configure Access and SAS Tokens
🔄 Not started yet

---

## Phase 4 — Static Website Hosting
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
| Storage Account LRS | ~$0.002 per GB per month |
| Blob storage operations | Fractions of a cent |
| Static website hosting | Free |
| Total for lab | ~$0.01 |

---

## My Confidence Rating After This Lab
| Skill | Before | After |
|---|---|---|
| Understanding Blob Storage | 1 | fill in |
| Creating Storage Accounts | 1 | fill in |
| Managing containers and blobs | 1 | fill in |
| Generating SAS tokens | 1 | fill in |
| Static website hosting | 1 | fill in |

---

## What I Would Do Differently Next Time
Fill at the end