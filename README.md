# agihand

winget install --id Microsoft.VCRedist.2015+.x64 -e --accept-source-agreements --accept-package-agreements

Invoke-WebRequest -Uri "https://aka.ms/vs/17/release/vc_redist.x64.exe" -OutFile "$env:TEMP\vc_redist.x64.exe"
Start-Process "$env:TEMP\vc_redist.x64.exe" -ArgumentList "/install","/quiet","/norestart" -Verb RunAs -Wait

<img width="346" height="140" alt="image" src="https://github.com/user-attachments/assets/e1769c7c-44a4-41fc-80bb-15e7a4c1842f" />
