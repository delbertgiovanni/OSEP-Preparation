# Network Enum

## Nmap

```bash
# Initial scan
nmap -sV -T4 <IPADDRESS> 

# UDP scan
sudo nmap -p 53,67,68,69,111,123,161,162,137,138,139,514,1900,5353,500,445 --open -sU <IPADDRESS> -oN=scan.txt

# TCP scan
nmap -p 443,8180,8888,1000,80,8080,8000,21,22,2222,3306,445,5985,3389,5986,1433,88 --open -A -oN=scan.txt

# Basic service scan to all ports
nmap -p- -sV -T4 -Pn <IPADDRESS> -d

# Aggresive scan to all ports
nmap -p- -A -T4 -Pn <IPADDRESS> -d

# Fast scan all ports
nmap -p- -T5 -Pn 192.168.191.52 -d
```

## Autorecon (<a href="https://github.com/Tib3rius/AutoRecon">link</a>)
```bash
autorecon --nmap-append=" — min-rate=2000" --exclude-tags="top-100-udp-ports" --exclude-tags nikto -vv <IP>
```

## Masscan (<a href="https://github.com/robertdavidgraham/masscan">link</a>)
```bash
masscan -p 1-65535 <IPADDRESS>
```
