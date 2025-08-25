# From Template to Production with Azure AI Foundry

This repository is an **adapted version** of Microsoft’s [sample-app-aoai-chatGPT](https://github.com/microsoft/sample-app-aoai-chatGPT).  
It shows how to take the official template and deploy it into a **production-ready setup** using **Azure App Service** and **Azure AI Foundry**.

---

## 🚀 What’s Included
- Azure App Service hosting with CI/CD (GitHub Actions)
- Managed Identity and Key Vault integration
- VNet + Private Endpoint configuration
- Prompt Flow for evaluation and iteration
- Observability with Application Insights and Log Analytics

---

## 📂 Repository Structure
├── src/ # Application code (based on Microsoft template)
├── .github/workflows/ # GitHub Actions for CI/CD
├── infra/ # Optional scripts (CLI/Bicep/Terraform)
└── README.md

---

## 🏗️ How to Deploy

### 1. Clone the repo
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```
### 2. Configure Azure resources
Create a Resource Group

Deploy App Service plan + Web App

Enable System Assigned Managed Identity

Create a Key Vault and add secrets

### 3. Set up GitHub Actions
Update .github/workflows/deploy-appservice.yml with:

AZURE_SUBSCRIPTION_ID

AZURE_CLIENT_ID

AZURE_TENANT_ID

WEBAPP_NAME

Secrets are stored in GitHub repository secrets, while sensitive runtime values are pulled from Azure Key Vault.

### 🔐 Security Notes
No secrets are stored in code.

Use Managed Identity for Key Vault access.

Prefer private endpoints for Azure AI Foundry + data sources.

🖼️ Architecture

Browser
   |
   v
Azure App Service (Web App)
   |
   v
Azure Key Vault ---> secrets / endpoints
   |
   v
Azure AI Foundry (Model endpoint)
   |
   v
Data Sources (Search, Storage, SQL) via private endpoints
📖 Full Guide
For the complete article and explanations, see:
👉 From Template to Production with Azure AI Foundry

🙏 Credits
Original template: microsoft/sample-app-aoai-chatGPT

### Adapted and published by Captain Azure ☁️⚓️
