# agihand




powershell -NoProfile -Command "Get-ChildItem '%USERPROFILE%\Desktop' -Recurse -Include *.inf,*.sys -EA SilentlyContinue | ? {$_.FullName -match 'Omni|CAN|driver'} | Select FullName"
