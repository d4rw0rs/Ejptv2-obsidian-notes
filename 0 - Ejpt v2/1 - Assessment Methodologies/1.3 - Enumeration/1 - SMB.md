SMB is a server used to share files in a network, is usually located in ports 139 and 445 on windows machines. To connect to a share use file explorer or net command in powershell.

```
net use z:(where to mount the share) \\IP_Address\drive password /user:USERNAME
net use * /delete
```

# Tools

## Nmap
```
nmap -p445 --script smb-protocols IP_ADDRESS
nmap -p445 --script smb-os-discovery IP_ADDRESS
nmap -p445 --script smb-enum-shares IP_ADDRESS
nmap -p445 --script smb-security-mode IP_ADDRESS
nmap -p445 --script smb-enum-sessions IP_ADDRESS
nmap -p445 --script smb-enum-sessions --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-enum-shares IP_ADDRESS
nmap -p445 --script smb-enum-shares --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-enum-users --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-server-stats --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-enum-domains --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-enum-groups --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-enum-services --script-args smbusername=USER,smbpassword=PASS IP
nmap -p445 --script smb-enum-shares,smb-ls --script-args smbusername=USER,smbpassword=PASS IP
```

## SMBMap
```
smbmap -u USER -p "PASS" -d . -H IP_ADDRESS
smbmap -u guest -p "" -d . -H IP_ADDRESS -> Null session
smbmap -u USER -p "PASS" -x "command" -H IP_ADDRESS
smbmap -u USER -p "PASS" -H IP_ADDRESS -r 'C$'
smbmap -u USER -p "PASS" -H IP_ADDRESS --upload 'file' 'drive\file'
smbmap -u USER -p "PASS" -H IP_ADDRESS --download 'drive\file'
```

## Mestasploit
```
auxiliary/scanner/smb/smb_version
auxiliary/scanner/smb/smb2 -> check if smb 2 is supported
auxiliary/scanner/smb/smb_enumshares
auxiliary/scanner/smb/smb_login
```

## Nmblookup
```
nmblookup -A IP_ADDRESS
```

## SMBClient -> no info about shares permissions
```
[!] Only use / when connecting to a share, use the following syntax always

smbclient -L IP_ADDRESS -N -> list shares using a null session
smbclient -L IP_ADDRESS -U USER
smbclient //IP_ADDRESS/drive -N -> connect to a drive with a null session
> get -> to download files
```

## RPCClient
```
rpcclient -U "" -N IP_ADDRESS
> srvinfo
> enumdomusers
> enumdomgroups
> lookupnames USER
```

## Enum4linux
```
enum4linux -o IP_ADDRESS -> list OS info
enum4linux -U IP_ADDRESS -> list users
enum4linux -S IP_ADDRESS -> list smb shares
enum4linux -G IP_ADDRESS -> list groups
enum4linux -i IP_ADDRESS -> list printers
enum4linux -r -u "USER" -p "PASS" IP_ADDRESS -> list users SID using the credentials
```

## Hydra
```
hydra -l user -P wordlist IP_ADDRESS smb
```

Other services use smb, services comunicate with pipes, so if were are in smb we can get in other services using pipes.

Metasploit have a module to list pipes

```
auxiliary/scanner/smb/pipe_auditor
```