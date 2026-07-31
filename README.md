# agihand

winget install --id Microsoft.VCRedist.2015+.x64 -e --accept-source-agreements --accept-package-agreements

Invoke-WebRequest -Uri "https://aka.ms/vs/17/release/vc_redist.x64.exe" -OutFile "$env:TEMP\vc_redist.x64.exe"
Start-Process "$env:TEMP\vc_redist.x64.exe" -ArgumentList "/install","/quiet","/norestart" -Verb RunAs -Wait