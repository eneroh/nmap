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
nmap -sn <targetIPrange/CIDR>
```
Targets specific IP addresses (linux specific)

```bash
nmap -sP <targetIPrange/CIDR>
```
Scans and provides mac address, vendor and hostname information for devices on network (windows and linux)

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



