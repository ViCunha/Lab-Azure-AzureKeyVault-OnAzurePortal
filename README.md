
### Overview
---
In this exercise you learn how to perform the following actions by using the Azure CLI:
- Create a Key Vault
- Add and retrieve a secret

   
### Key Aspects
---
- Azure Portal
- Azure Could Shell
- Azure CLI
- Azure Key Vault

### Environment
---
Microsoft Azure Portal
- Valid Subscription

### Actions
---
Prepare your environment
  
  - Sign in to the Azure portal

  - Open the Azure Cloud Shell using the Bash

Create the Azure Key Vault using Azure CLI

- Set environment variables
```
DEFAULT_CURRENTDATETIME="20240513113400"
DEFAULT_LOCATION="eastus2"
DEFAULT_RESOURCEGROUP_NAME="myresourcegroup${DEFAULT_CURRENTDATETIME}"
AZUREKEYVAULT_NAME="keyvault${DEFAULT_CURRENTDATETIME}"
AZUREKEYVAULT_SECRET_NAME="ConnectionStringDB"
```

- Create a resource group
```
az group create --name ${DEFAULT_RESOURCEGROUP_NAME} --location ${DEFAULT_LOCATION}
```

- Create a Key Vault
```
az keyvault create --name ${AZUREKEYVAULT_NAME} --location ${DEFAULT_LOCATION} --resource-group ${DEFAULT_RESOURCEGROUP_NAME}
```

Set and retrieve a secret

- Set a secret
```
az keyvault secret set --vault-name $AZUREKEYVAULT_NAME --name $AZUREKEYVAULT_SECRET_NAME --value "xyz"
```

- Retrieve the secret
```
az keyvault secret show --vault-name $AZUREKEYVAULT_NAME --name $AZUREKEYVAULT_SECRET_NAME
```

Clean up resources

- Delete the Resource Groups and its content
```
az group delete --name ${DEFAULT_RESOURCEGROUP} --no-wait
```

### Media
---
![image](https://github.com/ViCunha/Lab-Azure-AzureKeyVault-OnAzurePortal/assets/65992033/e95acc3c-b365-4c62-b206-180af6ab5050)

### References
---
- [Exercise: Set and retrieve a secret from Azure Key Vault by using Azure CLI - Training | Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/implement-azure-key-vault/5-set-retrieve-secret-azure-key-vault)
