### check PowerShell version--
```powershell
$PSVersionTable.PSVersion
```
### AzureRM PowerShell module installation--
```powershell
Get-Module -Name AzureRM -ListAvailable
Get-ExecutionPolicy -List
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Install-Module -Name Az -Repository PSGallery -Force
Update-Module -Name Az -Force
```
### Sign in/Connect to azure account-
```powershell
Connect-AzAccount
```

### AzureRM PowerShell module installation for Windows PowerShell--
```powershell
Install-Module -Name PowerShellGet -Force
Get-ExecutionPolicy -List
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Install-Module -Name Az -Repository PSGallery -Force
Update-Module -Name Az -Force
Get-InstalledModule -Name Az -AllVersions -OutVariable AzVersions
```

### Sign in/Connect to azure account-
```powershell
Connect-AzAccount
```
