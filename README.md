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
