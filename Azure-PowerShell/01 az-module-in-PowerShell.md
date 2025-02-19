### check PowerShell version--
- $PSVersionTable.PSVersion

------------------------------------------------------------------------
### AzureRM PowerShell module installation for PowerShell--
------------------------------------------------------------------------
- Get-Module -Name AzureRM -ListAvailable
- Get-ExecutionPolicy -List
- Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
- Install-Module -Name Az -Repository PSGallery -Force
- Update-Module -Name Az -Force
- Connect-AzAccount

------------------------------------------------------------------------
### AzureRM PowerShell module installation for Windows PowerShell--
------------------------------------------------------------------------
- Install-Module -Name PowerShellGet -Force
- Get-ExecutionPolicy -List
- Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
- Install-Module -Name Az -Repository PSGallery -Force
- Update-Module -Name Az -Force
- Get-InstalledModule -Name Az -AllVersions -OutVariable AzVersions
- Connect-AzAccount
