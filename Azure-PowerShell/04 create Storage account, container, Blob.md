## 1- Create AZ Storage account, container and blob using PowerShell--
### Sign in to Azure
```powershell
Connect-AzAccount
```
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


---
## Create Storage Account using Variable--
### Set variables-
```powershell
$rg_name = "My_rg_akkc"
$location = "EastUS"
$s_acc_name = "mystorageaccountakkc"
$container_name ="my_container1"
```
### Create resource group
```powershell
New-AzResourceGroup -Name $rg_name -Location $location
```
### Create storage account
```powershell
New-AzStorageAccount -ResourceGroupName $rg_name -Name $s_acc_name -Location $location -AllowBlobPublicAccess $true -SkuName "Standard_LRS" -Kind "StorageV2"
```
### Create a container--
```powershell
$ctx = New-AzStorageContext -StorageAccountName $s_acc_name -UseConnectedAccount
New-AzStorageContainer -Name $container_name -Context $ctx -AllowBlobPublicAccess $true
```
### Set container public access level-
```powershell
- Set-AzStorageContainerAcl -Name "$container_name" -Context $ctx -PublicAccess Blob
```
# Upload the blob
```powershell
$storageAccount = Get-AzStorageAccount -ResourceGroupName $rg_name -Name $s_acc_name
$a_ctx = $storageAccount.Context
$filePath = "E:/wall/3.jpeg"
Set-AzStorageBlobContent -File $filePath -Container $container_Name -Context $a_ctx
```
## Upload blobs to the container--
### upload a file to the default account (inferred) access tier
```powershell
$Blob1HT = @{
  File             = 'E:/wall/3.jpeg'
  Container        = $Container_Name
  Blob             = "3.jpeg"
  Context          = $ctx
  StandardBlobTier = 'Hot'
}
Set-AzStorageBlobContent @Blob1HT
  ```
 ### upload another file to the Cool access tier
 ```powershell
 $Blob2HT = @{
  File             = 'D:\Images\Image002.jpg'
  Container        = $ContainerName
  Blob             = 'Image002.png'
  Context          = $Context
  StandardBlobTier = 'Cool'
 }
 Set-AzStorageBlobContent @Blob2HT
  ```

### upload a file to a folder to the Archive access tier
```powershell
$Blob3HT = @{
  File             = 'D:\Images\FolderName\Image003.jpg'
  Container        = $ContainerName
  Blob             = 'FolderName/Image003.jpg'
  Context          = $Context
  StandardBlobTier = 'Archive'
}
Set-AzStorageBlobContent @Blob3HT
```

## List the blobs in a container--
```powershell
Get-AzStorageBlob -Container $ContainerName -Context $Context |
  Select-Object -Property Name
```
  
## Download blobs-
### Download first blob
```powershell
$DLBlob1HT = @{
  Blob        = 'Image001.jpg'
  Container   = $ContainerName
  Destination = 'D:\Images\Downloads\'
  Context     = $Context
}
Get-AzStorageBlobContent @DLBlob1HT
```
### Download another blob
```powershell
$DLBlob2HT = @{
  Blob        = 'Image002.png'
  Container   = $ContainerName
  Destination = 'D:\Images\Downloads\'
  Context     = $Context  
}
Get-AzStorageBlobContent @DLBlob2HT

```


## Create a container--
### Connect to your Azure subscription
 Connect-AzAccount
### Create a context object using Azure AD credentials
 $ctx = New-AzStorageContext -StorageAccountName <storage account name> -UseConnectedAccount
### Create variables
 $containerName  = "individual-container"
 $prefixName     = "loop"

### Approach 1: Create a container
 New-AzStorageContainer -Name $containerName -Context $ctx

### Approach 2: Create containers with a PowerShell loop
 for ($i = 1; $i -le 3; $i++) { 
     New-AzStorageContainer -Name (-join($prefixName, $i)) -Context $ctx
    }

### Approach 3: Create containers using the PowerShell Split method
 "$($prefixName)4 $($prefixName)5 $($prefixName)6".split() | New-AzStorageContainer -Context $ctx




## Clean up resources--
Remove-AzResourceGroup -Name $ResourceGroup




# note--

$rg_name = "My_rg_akkc11"
$location = "EastUS"
$s_acc_name = "mystorageaccountakkc11"
$container_name ="mycontainer11"
New-AzResourceGroup -Name $rg_name -Location $location
New-AzStorageAccount -ResourceGroupName $rg_name -Name $s_acc_name -Location $location -AllowBlobPublicAccess $true -SkuName "Standard_LRS" -Kind "StorageV2"
$ctx = New-AzStorageContext -StorageAccountName $s_acc_name -UseConnectedAccount
New-AzStorageContainer -Name $container_name -Context $ctx
Set-AzStorageContainerAcl -Container $container_name -Context $ctx -PublicAccess container
$storageAccount = Get-AzStorageAccount -ResourceGroupName $rg_name -Name $s_acc_name
$a_ctx = $storageAccount.Context
$filePath = "E:/wall/3.jpeg"
Set-AzStorageBlobContent -File $filePath -Container $container_Name -Context $a_ctx









$rg_name = "AKKC_RG"
$location = "EastUS"
$s_acc_name = "akkcmystorageaccount"
$container_name ="container1"
New-AzResourceGroup -Name $rg_name -Location $location
New-AzStorageAccount -ResourceGroupName $rg_name -Name $s_acc_name -Location $location -AllowBlobPublicAccess $true -SkuName "Standard_LRS" -Kind "StorageV2"
$storageAccount = Get-AzStorageAccount -ResourceGroupName $rg_name -Name $s_acc_name
$s_ctx = $storageAccount.Context
New-AzStorageContainer -Name $container_name -Permission Off -Context $s_ctx
Get-AzStorageContainerAcl -Container $containe_name -Context $s_ctx
Set-AzStorageContainerAcl -Container $container_name -Permission Container -Context $s_ctx
Get-AzStorageContainerAcl -Container $container_name -Context $s_ctx
$filePath = "E:/wall/3.jpeg"
Set-AzStorageBlobContent -File $filePath -Container $container_Name -Context $s_ctx
Get-AzStorageContainer -Context $ctx | Select Name, PublicAccess
