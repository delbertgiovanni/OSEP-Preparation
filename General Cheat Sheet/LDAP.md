# LDAP Enum

## Windapsearch (<a href="https://github.com/ropnop/windapsearch">link</a>)
```bash
# Enum AD users
python3 windapsearch.py -d htb.local --dc-ip 10.129.46.141 -U

# Enum all objects
python3 windapsearch.py -d htb.local --dc-ip 10.129.46.141 --custom "objectclass=*"
```
