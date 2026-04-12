# Lab 08 — Azure Key Vault
**Name:** Aadil Hussain
**Date Started:** 12 April 2026
**Total Time Taken:** [....]
**Status:** 🔄 In Progress

---

## What I Am Building
An Azure Key Vault to securely store secrets keys and
certificates. I will add secrets store connection strings
and API keys and control access using RBAC and access
policies. This demonstrates secure credential management
without hardcoding sensitive values in code.

---

## Key Concepts

### What is Azure Key Vault
A cloud service for securely storing and accessing secrets.
Secrets are anything you want to keep private like passwords
API keys database connection strings and certificates.
Key Vault eliminates the need to store secrets in code.

### Types of Objects in Key Vault
Secrets — passwords API keys connection strings
Keys — cryptographic keys for encryption and signing
Certificates — SSL TLS certificates for websites

### Why Key Vault Matters
Without Key Vault developers put passwords in code.
Code goes to GitHub and passwords become public.
Key Vault stores secrets securely outside the code.
Applications retrieve secrets at runtime securely.
Access is controlled via RBAC and access policies.

### Soft Delete
Key Vault has soft delete enabled by default.
Deleted secrets are retained for 90 days.
This prevents accidental permanent deletion.
Vault name is reserved for 90 days after deletion.

---

## Phase 1 — Create Key Vault ✅ COMPLETED

### What I Did
- Created resource group rg-lab-keyvault-08 in East Asia
- Navigated to Key Vaults and clicked Create
- Named Key Vault kv-aadil-lab08
- Selected Standard pricing tier
- Set permission model to Azure RBAC
- Disabled purge protection for easy lab cleanup
- Reviewed and created Key Vault successfully
- Assigned Key Vault Administrator role to my account

### Settings I Used
| Field | Value |
|---|---|
| Resource group | rg-lab-keyvault-08 |
| Key Vault name | kv-aadil-lab08 |
| Region | East Asia |
| Pricing tier | Standard |
| Permission model | Azure RBAC |
| Retention days | 7 days |
| Purge protection | Disabled |

### Standard vs Premium Tier
| Feature | Standard | Premium |
|---|---|---|
| Secrets and keys | Yes | Yes |
| HSM backed keys | No | Yes |
| Cost | ~$0.03 per secret | Higher |
| Use case | Learning and apps | High security enterprise |

### Why RBAC Permission Model
RBAC is the modern recommended approach.
It uses familiar Azure role assignments.
Access Policies is the legacy approach.
RBAC provides more granular control.
Can assign roles at vault or secret level.

### What I Learned
- Key Vault name must be globally unique across Azure
- Standard tier is sufficient for learning and most apps
- RBAC model integrates with Azure AD for access control
- Purge protection prevents permanent deletion for 90 days
- Disabled purge protection for easy lab cleanup
- Must assign Key Vault Administrator role before adding secrets
- Without proper role you cannot add or view secrets

### Screenshots
![Resource Group Created](screenshots/01-resource-group-created.png)
![Key Vault Created](screenshots/02-keyvault-created.png)
![Key Vault Overview](screenshots/03-keyvault-overview.png)
![KV Admin Role Assigned](screenshots/04-kv-admin-role-assigned.png)

---

## Phase 2 — Add Secrets and Keys
🔄 Not started yet

---

## Phase 3 — Configure Access Policies
🔄 Not started yet

---

## Phase 4 — Retrieve and Manage Secrets
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
| Key Vault | First 10K operations free per month |
| Secrets storage | ~$0.03 per secret per month |
| Total for lab | ~$0.01 |

---

## My Confidence Rating After This Lab
| Skill | Before | After |
|---|---|---|
| Understanding Key Vault concepts | 1 | fill in |
| Creating and configuring Key Vault | 1 | fill in |
| Adding and managing secrets | 1 | fill in |
| Configuring access policies | 1 | fill in |
| Retrieving secrets securely | 1 | fill in |

---

## What I Would Do Differently Next Time
Fill at the end