## Create and delete a Resource group--

#### Create a resorce group--
- az group create --name GroupName --location eastus
- **example1-**  az group create -name DevOps-AZ -location eastus
- **example2-**  az group create -n DevOps-AZ -l centralindia

### Know the azure regions--
-	az account list-locations -o table


### Set the Resource Group as default (Optional)--
- cmd-	az config set defaults.group=DevOps-AZ




### Create a VM-

 **Create a Linux VM--**
  
- az vm create --resource-group DevOps-AZ --name ubuntu --image ubuntu2204 --admin-username ubuntu --generate-ssh-keys
- az vm create --resource-group DevOps-AZ --name DevOps --image windowsserver2022 --admin-username devops --admin-password Surveillance1@123 --generate-ssh-keys
-	az vm create --resource-group az-cli  --name myVM --image ubuntu2204 --public-ip-sku Standard --admin-username azureuser --generate-ssh-keys

  **Create a Windows VM--**
- az vm create --resource-group DevOps-AZ --name WS2019 --image Win2019Datacenter --public-ip-sku Standard --admin-username devops --admin-password Surveillance1@123
  
- az vm create --resource-group DevOps-AZ --name win2019 --image Win2019Datacenter --public-ip-sku Standard --admin-username akkc
  
- az vm create --resource-group DevOps-AZ --name ws2019 --image Win2022AzureEditionCore --public-ip-sku Standard --admin-username akkc





### Create this before creation of any VM--
-
- az group create -n DevOps-AZ -l centralindia
- az network vnet create -g DevOps-AZ -n vnet1 --address-prefix 192.168.2.0/24 --subnet-name Subnet1 --subnet-prefixes 192.168.2.0/25
- az network nsg create --resource-group DevOps-NSG --name devops-nsg


### Delete the Resource Group to delete all the resources
- az group delete --name az-cli



