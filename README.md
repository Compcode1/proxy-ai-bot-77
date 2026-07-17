# Identity Architecture Ledger (IAL)
**Deployment Run Reference:** OIDC-OAUTH2-M2M-HARDENED
**Status:** Core Configurations Validated & Closed

## 1. Directory & Subscription Coordinates (Source/Target Boundary)
| Ledger Field | Registered Value | Architectural Purpose |
| :--- | :--- | :--- |
| **Microsoft Entra Tenant ID** | `9439dd25-f3b5-4829-a76f-5ede8cd54c3c` | Explicit identity plane boundary anchor. |
| **Target Azure Subscription ID** | `d5ffd8a5-d994-4eb5-b87c-4442054d233e` | Infrastructure management plane perimeter. |
| **Target Key Vault Instance** | `key-vault-99` | Secured data-plane asset container. |
| **Target Data-Plane Secret Name** | `top-secret-secret` | Target workload secret asset. |

## 2. Machine Identity & Federation Mapping (App Registration)
| Ledger Field | Registered Value | Architectural Purpose |
| :--- | :--- | :--- |
| **Application (Client) ID** | `93f3c397-70a1-40a4-8859-79caa5cf6d67` | Security principal identity assigned to the bot. |
| **Federated Trust Scenario** | `Other issuer` | Custom policy layout bypassing legacy UI templates. |
| **OIDC Token Issuer URI** | `https://token.actions.githubusercontent.com` | Trusted external authority signing the identity token. |
| **OIDC Audience Coordinate** | `api://AzureADTokenExchange` | Hardcoded system coordinate for token-exchange engine. |
| **Live Runtime Subject Claim** | `repo:Compcode1@171821203/proxy-ai-bot-77@1304057718:ref:refs/heads/main` | **Immutable Identity Signature** containing explicit platform database tracking IDs. |

## 3. Pipeline Runtime & Execution State
| Ledger Field | Registered Value | Architectural Purpose |
| :--- | :--- | :--- |
| **Source Workflow Path** | `.github/workflows/oidc-handshake.yml` | Location of automation script. |
| **Trigger Action Principal** | `push: refs/heads/main` | Explicit execution path constraints. |
| **Inbound Token Minting Permission** | `id-token: write` | Mandatory runner token authority. |
| **Deployment Engine Version** | `Azure CLI / Runner 2.335.1` | Underlying runtime environment. |

## 4. Architectural Control Validation (Hard Booleans)
| Validation Gate | Monosemic Status | Root Cause / Verification Evidence |
| :--- | :--- | :--- |
| **YAML Parse Success** | **TRUE** | String names successfully enclosed in single quotes (`'`) to escape reserved ampersand (`&`) characters. |
| **OIDC Handshake Success** | **TRUE** | Entra ID accepted the assertion and returned a 60-minute token via the custom `Other issuer` subject mapping policy. |
| **Data Plane Secret Extract** | **TRUE** | Pipeline successfully hit `key-vault-99` data-plane API and fetched the payload into hidden runner memory. |
| **Payload Identity Matches** | **TRUE** | Unmasked telemetry test output confirmed string content matches the targeted sentence structure: `"This top secret is worth "` |

---

### Human-AI Project State: Freeze & Close
*   **Core Configuration State:** **LOCKED.** The cryptographic handshake is verified, the trust relationships match, and the data plane connection works perfectly.
*   **Next Sequential Milestone:** This core pipeline is officially operational. When we reopen the lab, we will initiate the massive expansion project for **Phase 4.2** (mapping out all multi-environment variations, conditional access bounds, and add-on architecture scenarios) and audit our AI-assisted documentation notes.
