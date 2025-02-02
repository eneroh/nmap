# nmap

## commands

```bash
nmap <IP>
```
Basic scan

```bash
nmap -sn <targetIPrange/CIDR>
```
Targets specific IP addresses (linux specific)

```bash
nmap -sP <targetIPrange/CIDR>
```
Scans and provides mac address, vendor and hostname information for devices on network (windows and linux)
