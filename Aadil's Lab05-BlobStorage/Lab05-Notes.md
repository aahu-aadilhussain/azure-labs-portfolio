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

## Phase 1 — Create Storage Account ✅ COMPLETED

### What I Did
- Created resource group rg-lab-storage-05 in East Asia
- Navigated to Storage Accounts and clicked Create
- Named storage account aadilstorage05
- Selected Standard performance and LRS redundancy
- Enabled anonymous access on Advanced tab
- Left networking and data protection as default
- Reviewed and created the storage account
- Explored the storage account overview and services

### Settings I Used
| Field | Value |
|---|---|
| Resource group | rg-lab-storage-05 |
| Storage account name | aadilstorage05 |
| Region | East Asia |
| Performance | Standard |
| Redundancy | LRS — Locally Redundant Storage |
| Anonymous access | Enabled |
| TLS version | 1.2 |

### Storage Redundancy Options Explained
| Option | Copies | Where | Cost |
|---|---|---|---|
| LRS | 3 copies | Same data centre | Cheapest |
| ZRS | 3 copies | Different zones same region | Medium |
| GRS | 6 copies | Two different regions | Expensive |
| GZRS | 6 copies | Zones and regions | Most expensive |

### Why I Chose LRS
LRS is the cheapest redundancy option.
For a learning lab we do not need geo-redundancy.
LRS gives 99.999999999% durability — 11 nines.
That means 1 file loss per 100 billion files stored.
More than enough for lab purposes.

### Storage Account Services Available
| Service | Purpose |
|---|---|
| Blob storage | Unstructured files — images videos documents |
| File shares | SMB file shares — like network drives |
| Queues | Message queuing for app communication |
| Tables | NoSQL key-value storage |

### What I Learned
- Storage account is the top level container for all storage
- Name must be globally unique — only lowercase and numbers
- LRS is cheapest — keeps 3 copies in same data centre
- Performance Standard uses HDD — Premium uses SSD
- Anonymous access must be enabled at account level first
- Then it can be enabled at individual container level
- One storage account can host multiple storage services

### Screenshots
![Resource Group Created](screenshots/01-resource-group-created.png)
![Storage Validation](screenshots/02-storage-validation.png)
![Storage Account Created](screenshots/03-storage-account-created.png)
![Storage Services](screenshots/04-storage-services.png)

---

## Phase 2 — Create Containers and Upload Files ✅ COMPLETED

### What I Did
- Navigated to Containers under Data storage in sidebar
- Created lab-private container with Private access
- Created lab-public container with Blob anonymous access
- Created lab-uploads container with Private access
- Created 3 sample files in VS Code
- Uploaded sample-document.txt to lab-private
- Uploaded sample-data.json to lab-public
- Uploaded both files to lab-uploads
- Viewed blob properties including URL and metadata
- Tested public blob — accessible in browser directly
- Tested private blob — access denied as expected

### Containers Created
| Container | Access Level | Purpose |
|---|---|---|
| lab-private | Private | Secure storage — no public access |
| lab-public | Blob anonymous | Public files anyone can access |
| lab-uploads | Private | Upload staging area |

### Files Created and Uploaded
| File | Container | Type |
|---|---|---|
| sample-document.txt | lab-private and lab-uploads | Plain text |
| sample-data.json | lab-public and lab-uploads | JSON data |
| index.html | Used in Phase 4 for static website | HTML |

### Access Level Differences
| Level | Who Can Access | Use Case |
|---|---|---|
| Private | Only authorized users | Sensitive data |
| Blob | Anyone with URL | Public files images |
| Container | Anyone can list all blobs | Rarely used |

### Blob URL Format
https://[account].blob.core.windows.net/[container]/[blob]
https://aadilstorage05.blob.core.windows.net/lab-public/sample-data.json

### What I Learned
- Containers are like folders inside a storage account
- Access level is set per container not per blob
- Private containers return error to anonymous users
- Public blob containers allow direct URL access
- Blob URL format is always account container filename
- You can upload multiple files at once using Ctrl click
- Blob properties show size content type tier and URL
- Hot tier is default — for frequently accessed files

### Screenshots
![Containers Created](screenshots/05-containers-created.png)
![File Uploaded Private](screenshots/06-file-uploaded-private.png)
![File Uploaded Public](screenshots/07-file-uploaded-public.png)
![Files Uploaded Uploads](screenshots/08-files-uploaded-uploads.png)
![Blob Properties](screenshots/09-blob-properties.png)
![Public Blob Accessible](screenshots/10-public-blob-accessible.png)
![Private Blob Denied](screenshots/11-private-blob-denied.png)

---

## Phase 3 — Configure Access and SAS Tokens ✅ COMPLETED

### What I Did
- Navigated to lab-uploads container
- Generated SAS token for sample-document.txt
- Set permissions to Read only and expiry to 1 hour
- Copied the Blob SAS URL
- Tested SAS URL in InPrivate browser — file accessible
- Modified SAS URL signature — got authentication failed
- Generated container level SAS token for lab-uploads
- Explored Access Control IAM for storage account
- Viewed Access Keys page — kept keys hidden
- Changed blob tier from Hot to Cool
- Changed blob tier back to Hot

### SAS Token Settings Used
| Field | Value |
|---|---|
| Signing method | Account key |
| Permissions | Read |
| Expiry | 1 hour from generation |
| Protocols | HTTPS only |

### SAS URL Format
https://aadilstorage05.blob.core.windows.net/
lab-uploads/
sample-document.txt
?sv=2023-01-03
&se=2026-04-05T...
&sp=r
&sig=XXXXXXXXXXXXXXXX

### SAS URL Parameters Explained
| Parameter | Meaning |
|---|---|
| sv | Storage version |
| se | Signed expiry time |
| sp | Signed permissions r=read w=write d=delete |
| sig | Cryptographic signature |

### Access Tiers Explained
| Tier | Use Case | Storage Cost | Access Cost |
|---|---|---|---|
| Hot | Frequently accessed | Highest | Lowest |
| Cool | Once per month | Medium | Medium |
| Cold | Once per 90 days | Lower | Higher |
| Archive | Rarely accessed | Lowest | Highest |

### Why SAS Tokens Are Better Than Public Access
Public container — anyone forever can access all files
SAS token — specific person specific file specific time
SAS token expires automatically — no cleanup needed
SAS token can be revoked by rotating account keys
SAS token permissions can be read only — very safe

### What I Learned
- SAS tokens provide time-limited access to private blobs
- SAS URL contains expiry time and cryptographic signature
- Changing one character in SAS invalidates it completely
- Container SAS gives access to all blobs in container
- Blob SAS gives access to one specific file only
- Access keys are master keys — never share or hardcode
- Use SAS tokens for sharing — never use access keys
- Blob tiers control storage cost vs access cost tradeoff
- Archive tier requires rehydration before accessing
- IAM roles provide long term access management

### Screenshots
![SAS Token Generated](screenshots/12-sas-token-generated.png)
![SAS URL Working](screenshots/13-sas-url-working.png)
![Invalid SAS Denied](screenshots/14-invalid-sas-denied.png)
![Container SAS Generated](screenshots/15-container-sas-generated.png)
![Storage IAM Roles](screenshots/16-storage-iam-roles.png)
![Access Keys Page](screenshots/17-access-keys-page.png)
![Blob Tier Changed](screenshots/18-blob-tier-changed.png)

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