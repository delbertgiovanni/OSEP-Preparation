# Auto AD Enum

## Sharphound
```bash
# Import module
Import-Module .\Sharphound.ps1

# Getting help
Get-Help Invoke-BloodHound

# Collecting data
Invoke-BloodHound -CollectionMethod All -OutputDirectory C:\Users\stephanie\Desktop\ -OutputPrefix "corp_audit"
```

## Python bloodhound (<a href="https://github.com/dirkjanm/BloodHound.py">link</a>)
```bash
# Collecting data
bloodhound-python -d corp.com -u stephanie -p 'LegmanTeamBenzoin!!' -ns 192.168.207.70 -c all --zip
```

## Winpeas (<a href="https://github.com/peass-ng/PEASS-ng/blob/master/winPEAS/winPEASexe/README.md"link</a>)
```bash
Just download the binary and run it
```

## Powersploit scripts (<a href="https://github.com/PowerShellMafia/PowerSploit/tree/master">link</a>)
```bash
Choose the script following your needs
```