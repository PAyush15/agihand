# agihand




powershell -NoProfile -Command "Get-PnpDevice -PresentOnly | ? {$_.FriendlyName -match 'CANFD|CAN FD|analyser|analyzer'} | Select FriendlyName,Status,InstanceId | Format-List"

powershell -NoProfile -Command "$d=Get-PnpDevice -PresentOnly | ? {$_.FriendlyName -match 'CANFD|CAN'} | Select -First 1; Get-PnpDeviceProperty -InstanceId $d.InstanceId -KeyName DEVPKEY_Device_DriverProvider,DEVPKEY_Device_DriverVersion,DEVPKEY_Device_DriverInfPath | Select KeyName,Data | Format-Table -Auto"


