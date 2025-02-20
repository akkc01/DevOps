## create VM, VNET,SUBNET,  NSG --

### Create a resorce group--
```powershell
az group create -n DevOps-AZ -l centralindia
```
### Create VNET--
```powershell
az network vnet create -g DevOps-AZ -n vnet1 --address-prefix 192.168.0.0/24 --subnet-name Subnet1 --subnet-prefixes 192.168.0.0/25
 ```
- List VNET-
```powershell
az network vnet list -g akkc_rg
az network vnet list -o table
 ```
### Create subnet--
```powershell
az network vnet subnet create -g DevOps-AZ --vnet-name vnet1 -n subnet2 --address-prefixes 192.168.2.128/25 --network-security-group devops-nsg --route-table MyRouteTable
 ```

### Create a Network security group--
```powershell
az network nsg create --resource-group DevOps_rg --name devops-nsg	
 ```
- List NSG-
```powershell
az network nsg list --out table
 ```
### Delete a VNET-
```powershell
az network vnet delete -g akkc_rg -n VNet1
 ```

### Create a VM-

 **Create a Linux VM--**
```powershell
az vm create --resource-group DevOps-AZ --name ubuntu --image ubuntu2204 --admin-username ubuntu --generate-ssh-keys
az vm create --resource-group DevOps-AZ --name DevOps --image windowsserver2022 --admin-username devops --admin-password Surveillance1@123 --generate-ssh-keys
az vm create --resource-group az-cli  --name myVM --image ubuntu2204 --public-ip-sku Standard --admin-username azureuser --generate-ssh-keys
```
  **Create a Windows VM--**
 ```powershell
az vm create --resource-group DevOps-AZ --name WS2019 --image Win2019Datacenter --public-ip-sku Standard --admin-username devops --admin-password Surveillance1@123
az vm create --resource-group DevOps-AZ --name win2019 --image Win2019Datacenter --public-ip-sku Standard --admin-username akkc  
az vm create --resource-group DevOps-AZ --name ws2019 --image Win2022AzureEditionCore --public-ip-sku Standard --admin-username akkc
```

### Create this before creation of any VM--
```powershell
az group create -n DevOps-AZ -l centralindia
az network vnet create -g DevOps-AZ -n vnet1 --address-prefix 192.168.2.0/24 --subnet-name Subnet1 --subnet-prefixes 192.168.2.0/25
az network nsg create --resource-group DevOps-NSG --name devops-nsg
```

