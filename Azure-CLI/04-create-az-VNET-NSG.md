## How to Create az vnet, subnet & nsg--
### Create VNET--
- az network vnet create -g DevOps-AZ -n vnet1 --address-prefix 192.168.0.0/24 --subnet-name Subnet1 --subnet-prefixes 192.168.0.0/25
 
- az network vnet list -o table


### Create subnet--
- az network vnet subnet create -g DevOps-AZ --vnet-name vnet1 -n subnet2 --address-prefixes 192.168.2.128/25 --network-security-group devops-nsg --route-table MyRouteTable



### Create a Network security group--
- az network nsg list --out table      		
- az network nsg create --resource-group DevOps-AZ --name devops-nsg	

### Delete a VNET-
 - cmd-		az network vnet list
- example-	az network vnet list -g az-cli
- cmd-	az network vnet delete -g az-cli -n VNet1
