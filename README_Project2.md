
# 🚀 Project 2: Configure Azure Storage Account with Lifecycle and Security Policies

## 🔍 Summary

In this project, we configure an Azure Storage Account with enhanced security and cost-saving lifecycle rules. The tasks reflect the day-to-day responsibilities of an entry-level Azure Administrator.

---

## ✅ Skills Demonstrated

- Blob Lifecycle Management  
- Encryption at Rest  
- Private Endpoints  
- Shared Access Signatures (SAS)  
- Role-Based Access Control (RBAC)  

---

## 🧭 Step-by-Step Guide

### 1. Create a Storage Account

- **Go to:** Azure Portal → Storage Accounts → Create
- **Select settings:**
  - **Region:** (Choose your region)
  - **Performance:** Standard
  - **Redundancy:** Locally-redundant storage (LRS)
- **Advanced Tab:**
  - **Secure transfer required:** Enabled
  - **Access tier:** Hot
- Click **Review + Create**, then **Create**.

![Image alt](https://github.com/vasiliykop/Azure-Storage-Security/blob/fc4299bcbfca4538d2927db2aa721dd0392497af/storage-account-overview.png)
---

### 2. Configure Backup (Optional)

- **Navigate to:** Recovery Services Vault → Create new vault
- **Go to Backup blade → Select:**
  - **Workload:** Azure
  - **Backup Item:** Blob Storage (if supported)
- Create and configure a **backup policy**.

📸 *Screenshot: Backup policy settings*

---

### 3. Enable Role-Based Access (RBAC)

- Go to **Storage Account → Access Control (IAM)**
- Click **+ Add → Add Role Assignment**
  - **Role:** Storage Blob Data Contributor
  - **Assign to:** your user
- Click **Save**

![Image alt](https://github.com/vasiliykop/Azure-Storage-Security/blob/a91ab5fe5078081345f6a2020ebf20e95eb21e6c/RBAC.png)
---

### 4. Generate Shared Access Signature (SAS)

- Go to **Storage Account → Shared access signature**
  - **Services:** Blob
  - **Resource Types:** Service, Container, Object
  - **Permissions:** Read, Write, List
  - Set expiration to 1 day
- Click **Generate SAS token and URL**

![Image alt](https://github.com/vasiliykop/Azure-Storage-Security/blob/d260c46327d00d5ab313db908b4bb157963fa490/sas.png)

---

### 5. Configure Lifecycle Management Rule

- **Go to:** Storage Account → Data Management → Lifecycle Management
- Click **+ Add rule**
  - **Condition:** Last Modified > 30 days
  - **Action:** Move to Cool Storage
- Save the rule.

📸 *Screenshot: Lifecycle rule configuration*

---

### 6. Set Up Private Endpoint (Optional but recommended)

- Go to **Networking** tab → **Private Endpoint → + Add**
  - **Target sub-resource:** blob
  - **Assign to existing VNet and subnet**

📸 *Screenshot: Private endpoint configuration*








