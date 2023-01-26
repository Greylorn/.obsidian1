[[Powershell Scripts]]


## Admin Elevation

```
function IsAdministrator
{
    $Identity = [System.Security.Principal.WindowsIdentity]::GetCurrent()
    $Principal = New-Object System.Security.Principal.WindowsPrincipal($Identity)
    $Principal.IsInRole([System.Security.Principal.WindowsBuiltInRole]::Administrator)
}


function IsUacEnabled
{
    (Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\System).EnableLua -ne 0
}

#
# Main script
#
if (!(IsAdministrator))
{
    if (IsUacEnabled)
    {
        [string[]]$argList = @('-NoProfile', '-NoExit', '-File', $MyInvocation.MyCommand.Path)
        $argList += $MyInvocation.BoundParameters.GetEnumerator() | Foreach {"-$($_.Key)", "$($_.Value)"}
        $argList += $MyInvocation.UnboundArguments
        Start-Process PowerShell.exe -Verb Runas -WorkingDirectory $pwd -ArgumentList $argList 
        return
    }
    else
    {
        throw "You must be administrator to run this script"
    }
}
```

## Reg Key deployment
- Values must be changed for use case. This script deploys two different keys and it's function is to lock windows to a particular version (Prevent win11 auto update)

```
$registryPath = "HKLM:\Software\Policies\Microsoft\Windows\WindowsUpdate"

$Name = "TargetReleaseVersion"

$value = "1"

IF(!(Test-Path $registryPath))

  {

    New-Item -Path $registryPath -Force | Out-Null

    New-ItemProperty -Path $registryPath -Name $name -Value $value `
        -PropertyType DWORD -Force | Out-Null}

 ELSE {

    New-ItemProperty -Path $registryPath -Name $name -Value $value `
        -PropertyType DWORD -Force | Out-Null}

$registryPath = "HKLM:\Software\Policies\Microsoft\Windows\WindowsUpdate"

$Name = "TargetReleaseVersionInfo"

$value = "22h2"

IF(!(Test-Path $registryPath))

  {

    New-Item -Path $registryPath -Force | Out-Null

    New-ItemProperty -Path $registryPath -Name $name -Value $value `
        -PropertyType STRING -Force | Out-Null}

 ELSE {

    New-ItemProperty -Path $registryPath -Name $name -Value $value `
        -PropertyType STRING -Force | Out-Null}
```

## Move FSMO roles

```
Move-ADDirectoryServerOperationMasterRole –Identity "Target_DC_Name" –OperationMasterRole 0,1,2,3,4

```