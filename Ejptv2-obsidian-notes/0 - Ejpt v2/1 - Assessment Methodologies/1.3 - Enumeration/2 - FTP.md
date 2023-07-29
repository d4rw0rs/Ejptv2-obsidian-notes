FTP (File Transfer Protocol) is a server used to share files in a network, is usually located in port 21. 

# Tools

## Hydra
```
hydra -L users_list -P wordlist IP_ADDRESS ftp
hydra -l USER -P wordlist IP_ADDRESS ftp
```
## FTP
```
ftp IP_ADDRESS
> get file -> download a file
```
## Nmap
```
nmap IP_ADDRESS --script ftp-brute --script-args userbd=USERS_LIST -p21
nmap IP_ADDRESS --script ftp-anon -p21
```