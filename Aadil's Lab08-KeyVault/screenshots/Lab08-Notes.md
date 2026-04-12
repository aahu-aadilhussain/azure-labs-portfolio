# Lab 08 — Azure Key Vault
**Name:** Aadil Hussain
**Date Started:** 12 April 2026
**Date Completed:** 12 April 2026
**Total Time Taken:** [ 1 Day ]
**Status:** ✅ COMPLETED

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

## Phase 2 — Add Secrets and Keys ✅ COMPLETED

### What I Did
- Navigated to Secrets under Objects in Key Vault sidebar
- Added db-password secret with database password value
- Added api-key secret with API key value
- Added db-connection-string with full connection string
- Navigated to Keys under Objects
- Generated RSA 2048 bit encryption key
- Verified all 3 secrets and 1 key are listed

### Secrets Added
| Secret Name | Type | Purpose |
|---|---|---|
| db-password | text/plain | Database admin password |
| api-key | text/plain | External API authentication key |
| db-connection-string | text/plain | Full database connection string |

### Keys Added
| Key Name | Type | Size | Purpose |
|---|---|---|---|
| encryption-key-01 | RSA | 2048 bit | Data encryption and signing |

### Secrets vs Keys vs Certificates
| Object | What it stores | Example |
|---|---|---|
| Secret | Any sensitive text value | Password API key |
| Key | Cryptographic key material | RSA AES key |
| Certificate | SSL TLS certificate | HTTPS certificate |

### Why This Is Better Than Code
Bad practice — hardcoded in code:
password = "MyDatabaseP@ssw0rd123!"
If pushed to GitHub — password is exposed forever

Good practice — retrieved from Key Vault:
password = keyvault.get_secret("db-password")
Password never appears in code or GitHub

### What I Learned
- Secrets store any sensitive text value securely
- Keys store cryptographic material for encryption
- Certificates store SSL TLS certificates for HTTPS
- Secret values are hidden by default in portal
- Must click Show to reveal secret value
- Secrets can have expiration dates for rotation
- Each secret has a version history for auditing
- Key Vault logs every access attempt automatically

### Screenshots
![Secret DB Password](screenshots/05-secret-db-password.png)
![All Secrets Listed](screenshots/06-all-secrets-listed.png)
![Key Created](screenshots/07-key-created.png)

---

## Phase 3 — Configure Access Policies ✅ COMPLETED

### What I Did
- Viewed current role assignments on Key Vault
- Created KV Test User in Microsoft Entra ID
- Assigned Key Vault Secrets User role to KV Test User
- Understood differences between Key Vault RBAC roles
- Confirmed role assignments are visible in IAM page

### Key Vault Roles Configured
| User | Role | Can Read | Can Write | Can Delete |
|---|---|---|---|---|
| My Account | Key Vault Administrator | ✅ | ✅ | ✅ |
| KV Test User | Key Vault Secrets User | ✅ | ❌ | ❌ |

### Key Vault RBAC Roles Explained
| Role | Purpose |
|---|---|
| Key Vault Administrator | Full control of vault and all objects |
| Key Vault Secrets Officer | Manage secrets but not vault settings |
| Key Vault Secrets User | Read secret values only |
| Key Vault Reader | Read metadata but not secret values |
| Key Vault Crypto Officer | Manage keys but not secrets |

### Why Least Privilege Matters in Key Vault
An application only needs to READ secrets.
Give it Key Vault Secrets User role only.
Even if the app is compromised the attacker
cannot delete or modify secrets in the vault.
This limits the damage from a security breach.

### What I Learned
- Key Vault has specific roles for fine grained access
- Key Vault Secrets User can only read secret values
- Key Vault Administrator has complete control
- Assign minimum required role for each user or app
- RBAC roles on Key Vault integrate with Entra ID users
- Role assignments take effect within minutes
- Separate roles exist for secrets keys and certificates

### Screenshots
![Current Access](screenshots/08-current-access.png)
![KV Test User Created](screenshots/09-kv-test-user-created.png)
![Secrets User Role Assigned](screenshots/10-secrets-user-role-assigned.png)
![KV Roles Comparison](screenshots/11-kv-roles-comparison.png)

---

## Phase 4 — Retrieve and Manage Secrets ✅ COMPLETED 

### What I Did
- Navigated to db-password secret in Key Vault
- Clicked Show Secret Value to reveal the password
- Created a new version of db-password with updated value
- Viewed both versions in the secret version history
- Noted the Secret Identifier URL format
- Explored Activity Log showing all Key Vault operations
- Disabled api-key secret to test disable functionality
- Re-enabled api-key secret

### Secret Management Operations Performed
| Operation | Secret | Result |
|---|---|---|
| View secret value | db-password | Value revealed successfully |
| Create new version | db-password | Version 2 created |
| View activity log | All secrets | All operations logged |
| Disable secret | api-key | Secret disabled |
| Re-enable secret | api-key | Secret re-enabled |

### Secret Identifier URL Format
https://[vaultname].vault.azure.net/secrets/[secretname]/[version]
https://kv-aadil-lab08.vault.azure.net/secrets/db-password/

### How Applications Use Key Vault
Instead of hardcoding in code:
connection_string = "Server=sql...Password=123"

Application code uses Key Vault SDK:
secret = client.get_secret("db-connection-string")
connection_string = secret.value

The password never appears in application code.
The password is retrieved securely at runtime only.

### Secret Versioning Benefits
Every update creates a new version automatically.
Old versions are retained for auditing purposes.
You can roll back to previous version if needed.
Applications can pin to specific version or use latest.
Version history provides complete audit trail.

### What I Learned
- Secret values are hidden by default — must click Show
- Every secret update creates new version automatically
- Secret Identifier URL is used by applications to retrieve secrets
- Activity log records every single Key Vault operation
- Disabling a secret blocks access without deleting it
- Disabled secrets can be re-enabled at any time
- Version history provides complete audit trail
- Applications should never store secrets in code
- Key Vault SDK available for all major programming languages

### Screenshots
![Secret Value Revealed](screenshots/12-secret-value-revealed.png)
![Secret Versions](screenshots/13-secret-versions.png)
![Secret Identifier URL](screenshots/14-secret-identifier-url.png)
![Activity Log](screenshots/15-insight.png)
![Secret Disabled](screenshots/16-secret-disabled.png)

---

## Phase 5 — Cleanup ✅ COMPLETED

### What I Did
- Deleted KV Test User from Microsoft Entra ID
- Deleted resource group rg-lab-keyvault-08
- Confirmed all resources are deleted
- Checked for soft deleted vault in Key Vaults
- Purged vault to free up the name immediately
- Checked Cost Management for total cost

### Resources Deleted
| Resource | Type |
|---|---|
| kvtestuser | Entra ID User |
| kv-aadil-lab08 | Key Vault |
| rg-lab-keyvault-08 | Resource Group |

### Key Vault Soft Delete Explained
Key Vault soft delete is enabled by default.
Deleted vaults are retained for 7 to 90 days.
The vault name is reserved during retention period.
Purge permanently deletes and frees the name immediately.
This prevents accidental permanent data loss.

### Cost This Lab Used
| Resource | Cost |
|---|---|
| Key Vault Standard | First 10K operations free |
| Secrets storage | ~$0.01 for lab duration |
| Total | ~$0.00 |

### What I Learned
- Key Vault soft delete retains vault for 7 days minimum
- Vault name is reserved after deletion until purged
- Purge immediately and permanently deletes the vault
- Key Vault is extremely cost effective for secret management
- Deleting resource group triggers soft delete on vault
- Always purge vault after lab to free name for reuse

### Screenshots
![KV Test User Deleted](screenshots/17-kv-test-user-deleted.png)
![Delete Confirmation](screenshots/18-delete-confirmation.png)
![Cleanup Complete](screenshots/19-cleanup-complete.png)
![Vault Purged](screenshots/20-vault-purged.png)
![Cost Analysis](screenshots/21-cost-analysis.png)

---

## Problems I Faced
| Problem | What I Tried | How I Fixed It |
|---|---|---|
| Secret value not visible after creation | Clicked on secret name | Had to click the version number first then click Show Secret Value |
| Could not find Objects section in sidebar | Scrolled through sidebar | Found Secrets Keys Certificates under Objects section in left sidebar |
| KV Test User creation in wrong directory | Created user in wrong tenant | Navigated to Microsoft Entra ID first then created user from Users section |

---

## What I Learned
- Key Vault securely stores secrets keys and certificates
- Eliminates need to hardcode sensitive values in code
- RBAC model provides fine grained access control
- Key Vault Secrets User role allows read only secret access
- Secret values are hidden by default in Azure Portal
- Every secret update creates a new version automatically
- Version history provides complete audit trail
- Secret Identifier URL is used by apps to retrieve secrets
- Activity log records every Key Vault operation
- Disabling secret blocks access without deleting it
- Soft delete retains vault for 7 days after deletion
- Purge immediately and permanently removes vault
- Key Vault is extremely cheap — first 10K ops free monthly
- Applications should always use Key Vault instead of hardcoding

---

## Cost Tracking
| Resource | Cost |
|---|---|
| Key Vault | First 10K operations free per month |
| Secrets storage | ~$0.03 per secret per month |
| Total for lab | ~$0.00 |

---

## My Confidence Rating After This Lab
| Skill | Before | After |
|---|---|---|
| Understanding Key Vault concepts | 1 | 4 |
| Creating and configuring Key Vault | 1 | 3 |
| Adding and managing secrets | 1 | 4 |
| Configuring access policies | 1 | 3 |
| Retrieving secrets securely | 1 | 3 |

---

## What I Would Do Differently Next Time
1. Assign Key Vault Administrator role immediately after creation
2. Test secret retrieval using Azure CLI for more realistic experience
3. Set expiration dates on secrets to practice rotation
4. Connect Key Vault to an App Service using Managed Identity
5. Explore certificate management for SSL TLS use case
6. Purge deleted vault immediately to free name for reuse