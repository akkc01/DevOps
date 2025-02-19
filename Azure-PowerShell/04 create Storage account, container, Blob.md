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
