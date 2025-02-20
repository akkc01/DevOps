## Create AZ Storage account, container and blob using PowerShell--
### Sign in to Azure
```powershell
Connect-AzAccount
```
---

### Create a Resource Group-
```powershell
New-AzResourceGroup -Name myrg -Location westus
```
- you can use -n , -l for name and location fields.
### Create AZ Storage Account--
To Create Azure Storage Account run the below code in PowerShell:
```powershell
New-AzStorageAccount -ResourceGroupName MyResourceGroup -Name mystorageaccount -Location westus -SkuName Standard_GRS -MinimumTlsVersion TLS1_2
```
> **Note:** The `MinimumTlsVersion TLS1_2` is required.

### Create a Blob Storage account with BlobStorage Kind and hot AccessTier--
```powershell
New-AzStorageAccount -ResourceGroupName MyResourceGroup -Name mystorageaccount -Location westus -SkuName Standard_GRS -Kind BlobStorage -AccessTier Hot
```
### Create a Storage account with Kind StorageV2, and Generate and Assign an Identity for Azure KeyVault--
```powershell
New-AzStorageAccount -ResourceGroupName MyResourceGroup -Name mystorageaccount -Location westus -SkuName Standard_GRS -Kind StorageV2 -AssignIdentity
```


