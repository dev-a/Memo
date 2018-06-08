# Windows
## powershell
### dezipper tous les fichiers zips d'un repertoire dans des sous repertoires
Get-ChildItem -Filter *.zip  | % { $_.FullName } | Split-Path | Get-Unique | % { cd $_ ; &'C:\Program Files\7-Zip\7z.exe' x *.zip -o* }

### killer un processus 
Stop-Process -d 12952 -Confirm:$false

 Get-Process | Where-Object {$_.MainWindowTitle -like "Free *"} | Stop-Process
