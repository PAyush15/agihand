# agihand




powershell -NoProfile -Command "Get-Process | ? {$_.Name -match 'Omni|CAN'} | Select Name,Id"



<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/b820b7ae-eda0-473d-a7a7-e97a4c27763c" />


powershell -NoProfile -Command "$env:OHB='C:\path\to\your\extracted\folder'; [Environment]::SetEnvironmentVariable('OHB',$env:OHB,'User'); Write-Host 'Set to:' $env:OHB"

powershell -NoProfile -Command "Get-Content \"$env:OHB\kerneldlls\dll_cfg.ini\""

powershell -NoProfile -Command "$d=Get-PnpDevice -PresentOnly | ? {$_.FriendlyName -match 'CANFD|CAN|analys'} | Select -First 1; Get-PnpDeviceProperty -InstanceId $d.InstanceId -KeyName DEVPKEY_Device_DriverProvider,DEVPKEY_Device_DriverInfPath | Select KeyName,Data | Format-Table -Auto"

powershell -NoProfile -Command "Get-PnpDevice -PresentOnly | ? {$_.FriendlyName -match 'CANFD|analys'} | ForEach-Object { Disable-PnpDevice -InstanceId $_.InstanceId -Confirm:$false; Start-Sleep 2; Enable-PnpDevice -InstanceId $_.InstanceId -Confirm:$false }"




C:\Windows\System32>powershell -NoProfile -Command "Get-Content "$env:OHB\kerneldlls\dll_cfg.ini""                      Get-Content : Cannot find path 'C:\kerneldlls\dll_cfg.ini' because it does not exist.                                   At line:1 char:1                                                                                                        + Get-Content $env:OHB\kerneldlls\dll_cfg.ini                                                                           + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~                                                                               + CategoryInfo          : ObjectNotFound: (C:\kerneldlls\dll_cfg.ini:String) [Get-Content], ItemNotFoundException       + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetContentCommand       
