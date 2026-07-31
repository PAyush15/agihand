# agihand




powershell -NoProfile -Command "Get-Process | ? {$_.Name -match 'Omni|CAN'} | Select Name,Id"
