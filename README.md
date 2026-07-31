# agihand




C:\Users\BUH local-admin>powershell -NoProfile -Command "Get-PnpDevice -PresentOnly | ? {$_.FriendlyName -match 'CANFD|CAN FD|analyser|analyzer'} | Select FriendlyName,Status,InstanceId | Format-List"


FriendlyName : CANFD Analyser
Status       : OK
InstanceId   : USB\VID_A8FA&PID_8598&MI_00\7&37A1AB33&0&0000

FriendlyName : CANFD Analyser
Status       : OK
InstanceId   : USB\VID_A8FA&PID_8598&MI_01\7&37A1AB33&0&0001




C:\Users\BUH local-admin>powershell -NoProfile -Command "$d=Get-PnpDevice -PresentOnly | ? {$_.FriendlyName -match 'CANFD|CAN'} | Select -First 1; Get-PnpDeviceProperty -InstanceId $d.InstanceId -KeyName DEVPKEY_Device_DriverProvider,DEVPKEY_Device_DriverVersion,DEVPKEY_Device_DriverInfPath | Select KeyName,Data | Format-Table -Auto"

KeyName                       Data
-------                       ----
DEVPKEY_Device_DriverProvider Microsoft
DEVPKEY_Device_DriverVersion  10.0.26100.1150
DEVPKEY_Device_DriverInfPath  winusb.inf

