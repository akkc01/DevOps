## Use the below steps-

### Azure Login-
```powershell
az login
```

### Get Subsciption id-
```powershell
az account list --output table
```
### Generate Token using AZ CLI-
```powershell
az account get-access-token --query accessToken --output tsv
```
## Now Download Postman-
- Download `Postman` from below link - 
```powershell
https://www.postman.com/downloads/
```
### Now Open Postman-
- copy& paste below `url` in postman Address bar. choose the `PUT` method from options-
- `https://management.azure.com/subscriptions/f85ee25f-ffbe-4145-896a-4a245999982e/resourceGroups/AKKC_API/providers/Microsoft.Storage/storageAccounts/akkcstorageacc?api-version=2021-04-01`
## Now do following setting in postman-
1- `Params` tab settings-
- api-version       2024-11-01
- 

2- `Authorization` tab settings-
```powershell
Type ---Bearer Token | <Token>

```

3- `Headers` tab settings-
```poweershell
    key             Value
Authorization        Bearer {access token}
Content_type        application/json
```

4- `Body` tab setting--
```powershell
{
    "location": "eastus",
    "tags": {
        "name": "akkc", 
        "add": "india"
    },
    
      "sku": {
        "name": "Standard_LRS"
}
```

4- output look like-
```powershell

{
    "sku": {
        "name": "Standard_LRS",
        "tier": "Standard"
    },
    "kind": "Storage",
    "id": "/subscriptions/f85ee25f-ffbe-4145-896a-4a245999982e/resourceGroups/AKKC_API/providers/Microsoft.Storage/storageAccounts/akkcstorageacc",
    "name": "akkcstorageacc",
    "type": "Microsoft.Storage/storageAccounts",
    "location": "eastus",
    "tags": {
        "name": "akkc",
        "add": "india"
    },
    "properties": {
        "keyCreationTime": {
            "key1": "2025-02-20T06:12:04.4551998Z",
            "key2": "2025-02-20T06:12:04.4551998Z"
        },
        "allowCrossTenantReplication": false,
        "privateEndpointConnections": [],
        "minimumTlsVersion": "TLS1_0",
        "allowBlobPublicAccess": false,
        "networkAcls": {
            "bypass": "AzureServices",
            "virtualNetworkRules": [],
            "ipRules": [],
            "defaultAction": "Allow"
        },
        "supportsHttpsTrafficOnly": true,
        "encryption": {
            "services": {
                "file": {
                    "keyType": "Account",
                    "enabled": true,
                    "lastEnabledTime": "2025-02-20T06:12:04.5333289Z"
                },
                "blob": {
                    "keyType": "Account",
                    "enabled": true,
                    "lastEnabledTime": "2025-02-20T06:12:04.5333289Z"
                }
            },
            "keySource": "Microsoft.Storage"
        },
        "provisioningState": "Succeeded",
        "creationTime": "2025-02-20T06:12:04.3145764Z",
        "primaryEndpoints": {
            "blob": "https://akkcstorageacc.blob.core.windows.net/",
            "queue": "https://akkcstorageacc.queue.core.windows.net/",
            "table": "https://akkcstorageacc.table.core.windows.net/",
            "file": "https://akkcstorageacc.file.core.windows.net/"
        },
        "primaryLocation": "eastus",
        "statusOfPrimary": "available"
    }
}
```
