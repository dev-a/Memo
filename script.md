# Windows
## powershell
### dezipper tous les fichiers zips d'un repertoire dans des sous repertoires
Get-ChildItem -Filter *.zip  | % { $_.FullName } | Split-Path | Get-Unique | % { cd $_ ; &'C:\Program Files\7-Zip\7z.exe' x *.zip -o* }
