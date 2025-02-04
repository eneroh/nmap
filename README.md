# nmap

## authors note
- `nmap --help | grep "<tac/flag>"` is a great help in building this
- Shoutout to the eJPT and hackersploit going through the commands for/with me. I wouldn't have had the patience to do it all myself aha

## tips & tricks
- scripts are stored in `/usr/share/nmap/scripts`
- use `ls | grep "<string>"` to find the script you are looking for
- use `cat <script.nse> | grep "<string>"` to find arguments that need to be changed during nmap command phase
- Some scripts have special arguments you need to specify before proceeding, ensure you add these during the nmap command phase
- Change timing and tick rates are loud, only do these if you want to be caught
- `nmap -Pn` for windows specific scanning

## commands

```bash
nmap <targetIP>
```
Basic scan

```bash
nmap -p <port> <targetIP>
nmap -p- <targetIP>
```
Port specific scan

```bash
nmap <targetIP> -o <file>
-oN
-oX
-oS
-oG
-oA
```
Output results to file
<br>
Normal format
<br>
XML format
<br>
script kiddie format
<br>
Greppable format
<br>
Output in 3 major formats

```bash
nmap <targetIP> > <file>
cat <file> | grep ".lan" | awk '{print $5,$6}'
```
Perform scan, outputs to file, grep for unique and found materials, column specific filtering

```bash
nmap -sn <targetIPrange/CIDR>
```
Ping scan, scan host discovery (linux specific)

```bash
nmap -sP <targetIPrange/CIDR>
```
Scans and provides mac address, vendor and hostname information for devices on network (windows and linux)

```bash
nmap -O <targetIP>
```
Present Operating system information

```bash
nmap -T<1,2,3,4,5>
```
Increasing scan timing speed (1=sneaky, 5=insane)
<br>
Can go T4 or T5 in the OSCP
<br>
Real life pen testing, be quiet and sneakier

```bash
nmap -sS <targetIP>
```
TCP Syn scan, sneaky scan

```bash
nmap -sV <targetIP>
```
Versioning, also contains operating system information

```bash
nmap -sC <targetIP>
```
Basic script search, equivalent of: --script=default
<br>
Typically presents more infomration than usual

```bash
nmap -sU <targetIP>
```
UDP Scan

```bash
nmap -v <targetIP>
```
Verbose scan, presents information readily

```bash
nmap -vvv <targetIP>
```
Very verbose scan, presents information constantly

```bash
nmap -Pn
```
Required for windows hosts, treat all hosts as online (skips host discovery)

```bash
nmap --script <script.nse> <target>
```
Calling a script onto a target

```bash
nmap --script <script.nse> --script-args <n1=v1,[n2=v2]>
```
Provide arguments to scripts

```bash
nmap --help | grep "script"
```
Provides additional script information

```bash
nmap --help | grep "Pn"
```
For additional skip host discovery information



