# azure-architect-learning
My journey to Azure Solutions Architect &amp; AI Engineering.

# ☁️ Azure Architect & AI Engineering Path
**Goal:** Master Azure Infrastructure, Security, and AI Governance by Summer 2026.

## 📚 Book 1: The Fortress (Infrastructure & Security)

### ✅ Chapter 1: The Network Foundation (Jan 17, 2026)
**Objective:** Build a secure, segmented network ("The Private Island").

#### 🏗️ Architecture Built
* **The Land (VNet):** `vnet-learning-01`
    * *Address Space:* `10.0.0.0/16` (65,536 IPs)
* **The Segmentation (Subnets):**
    * 🏠 **Lobby (`snet-web`):** `10.0.1.0/24` -> Public Access Zone.
    * 🔒 **Vault (`snet-data`):** `10.0.2.0/24` -> Private Data Zone.
* **The Firewall (NSG):** `nsg-web`
    * *Rule 110:* `AllowSSH` -> Restricted to Admin Home IP only.
    * *Result:* Blocked all unauthorized internet traffic.

#### 🧪 Verification (Smoke Test)
* Deployed Linux VM (`vm-test-01`) into the Web Subnet.
* Successfully SSH'd via Port 22 using the secure IP whitelist.
* **Outcome:** Identity verified. Network is secure.

### ✅ Chapter 2: The Vault (Jan 25, 2026)
**Objective:** Build a secure, private storage system for AI models.

#### 🏗️ Architecture Built
* **The Vault (Storage):** `stlearning<yourname>`
    * *Tier:* Cool / LRS (Cost Optimized).
    * *Security:* Public Internet Access **DISABLED**.
* **The Tunnel (Private Endpoint):** `pe-storage-01`
    * *Connection:* Connected `snet-data` directly to Blob Storage.
    * *Result:* Storage is only accessible from inside the Private Island.
* **The Identity (Security):**
    * Enabled **Managed Identity** on the VM.
    * Assigned RBAC Role: **Storage Blob Data Contributor**.
    * *Outcome:* Accessed data without a single password or access key.

#### 🧪 Verification (The Heist)
* Deployed Spy VM (`vm-vault-01`) into the network.
* Logged in via Identity: `az login --identity`.
* Successfully retrieved `secret.txt` through the private tunnel.
