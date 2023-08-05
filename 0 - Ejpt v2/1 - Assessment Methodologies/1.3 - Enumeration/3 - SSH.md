SSH (Secure Shell) is a remote access service usually located in port 22.

# Tools

## SSH
```
ssh user@ip
```

## Netcat
```
nc IP_ADDRESS PORT -> show service banner
```

## Nmap
```
nmap IP -p22 --script ssh2-enum-algos -> list of algorithms to create keys
nmap IP -p22 --script ssh-hostkey --script-args ssh_hostkey=full -> show hostkey
nmap IP -p22 --script ssh-auth-methods --script-args="ssh.user=USER" -> auth methods
nmap IP -p22 --script ssh-brute --script-args userdb=USERLIST
```

## Hydra
```
hydra -l USER -P wordlist IP_ADDRESS ssh
```

## Metasploit
```
auxiliary/scanner/ssh/ssh_login
auxiliary/scanner/ssh/ssh_version
```