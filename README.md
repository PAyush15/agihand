# agihand

winget install --id Microsoft.VCRedist.2015+.x64 -e --accept-source-agreements --accept-package-agreements

Invoke-WebRequest -Uri "https://aka.ms/vs/17/release/vc_redist.x64.exe" -OutFile "$env:TEMP\vc_redist.x64.exe"
Start-Process "$env:TEMP\vc_redist.x64.exe" -ArgumentList "/install","/quiet","/norestart" -Verb RunAs -Wait

<img width="346" height="140" alt="image" src="https://github.com/user-attachments/assets/e1769c7c-44a4-41fc-80bb-15e7a4c1842f" />

Try/check:

# --- .NET Framework 4.8 check ---
$net = Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" -ErrorAction SilentlyContinue
if ($net -and $net.Release -ge 528040) {
    Write-Host ".NET Framework 4.8+ : INSTALLED (Release $($net.Release))" -ForegroundColor Green
} else {
    Write-Host ".NET Framework 4.8  : MISSING" -ForegroundColor Red
}

# --- VC++ 2015-2022 x64 Redistributable check ---
$vc = Get-ChildItem "HKLM:\SOFTWARE\Microsoft\VisualStudio\14.0\VC\Runtimes\x64",
                    "HKLM:\SOFTWARE\WOW6432Node\Microsoft\VisualStudio\14.0\VC\Runtimes\x64" -ErrorAction SilentlyContinue |
      Get-ItemProperty | Where-Object { $_.Installed -eq 1 } | Select-Object -First 1
if ($vc) {
    Write-Host "VC++ 2015-2022 x64  : INSTALLED (v$($vc.Version))" -ForegroundColor Green
} else {
    Write-Host "VC++ 2015-2022 x64  : MISSING" -ForegroundColor Red
}
