# Windows 10 ISO Powershell Functions

Get-Win10ISOLink:
This function spoofs a request from a non windows device in order generate a windows 10 ISO link. It leverages MSFTs internal APIs and hardcoded IDs to generate the link.

Example uses of the function:


# GENERATE DL LINK:
CMD 32-bit:
```
"%windir%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -ExecutionPolicy Bypass -Command "& {(new-object Net.WebClient).DownloadString('https://raw.githubusercontent.com/aescolastico/windows10-iso/master/win10-iso-functions.ps1') | Invoke-Expression; Get-Win10ISOLink -Architecture 32-bit}"
```
CMD 64-bit:
```
"%windir%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -ExecutionPolicy Bypass -Command "& {(new-object Net.WebClient).DownloadString('https://raw.githubusercontent.com/aescolastico/windows10-iso/master/win10-iso-functions.ps1') | Invoke-Expression; Get-Win10ISOLink -Architecture 64-bit}"
```
PowerShell:
```
(new-object Net.WebClient).DownloadString('https://raw.githubusercontent.com/aescolastico/windows10-iso/master/win10-iso-functions.ps1') | Invoke-Expression; Get-Win10ISOLink
```

See https://github.com/RFAInc/windows10-iso for installation functions.
