# SMB Service Enumeration

## Smbclient
```bash
# List SMB share anonymously
smbclient --no-pass -L <ip>

# Connect to a share anonymously
smbclient --no-pass //server/share 

# Connect to a share using creds
smbclient //server/share --user username%password

# Connect to  a share using different workgroup
smbclient //server/share --workgroup domain --user username

# Upload file to share
smbclient //server/share --directory path/to/directory --command "put file.txt"

# Download file from share
smbclient //server/share --directory path/to/directory --command "get file.txt"

# Download file recursively
smb: \> recurse ON
smb: \> prompt OFF
smb: \> mget *
```

## Enum4linux
```bash
enum4linux -a target-ip
```

## Smbmap
```bash
smbmap -H target-ip
```

## Nmap
```bash
nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse target-ip

sudo nmap -sV --script-args=unsafe=1 --script smb-os-discovery 10.10.13.37 -p139,445

sudo nmap -n -Pn -sV --script 'smb-vuln*' 10.10.13.37 -p445
```
