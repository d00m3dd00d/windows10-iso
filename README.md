# Windows 10 ISO Powershell Functions

Branched from https://github.com/aescolastico/windows10-iso - this version is designed for additionally handling the file transfer from argument.

Get-Win10ISOLink:
This function spoofs a request from a non windows device in order generate a windows 10 ISO link. It leverages MSFTs internal APIs and hardcoded IDs to generate the link.

Example uses of the function:


# GENERATE DL LINK:
CMD 32-bit:
```
"%windir%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -ExecutionPolicy Bypass -Command "& {(new-object Net.WebClient).DownloadString('https://raw.githubusercontent.com/d00m3dd00d/windows10-iso/master/Get-Windows10ISOLink.ps1') | Invoke-Expression; Get-Win10ISOLink -Architecture 32-bit -DownloadISOFile Yes -OutputLocation C:\temp}"
```
CMD 64-bit:
```
"%windir%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -ExecutionPolicy Bypass -Command "& {(new-object Net.WebClient).DownloadString('https://raw.githubusercontent.com/d00m3dd00d/windows10-iso/master/Get-Windows10ISOLink.ps1') | Invoke-Expression; Get-Win10ISOLink -Architecture 64-bit -DownloadISOFile Yes -Output-Location c:\temp}"
```
PowerShell:
```
(new-object Net.WebClient).DownloadString('https://raw.githubusercontent.com/d00m3dd00d/windows10-iso/master/Get-Windows10ISOLink.ps1') | Invoke-Expression; Get-Win10ISOLink -Architecture 64-bit -DownloadISOFile Yes -Output-Location C:\temp
```

See https://github.com/RFAInc/windows10-iso for installation functions.
