HTTP (Hypertext Transfer Protocol) is the protocol used in websites to send the content to the client.

# Tools

## Whatweb
```
whatweb IP_ADDRESS
```

## HTTP

```
http IP_ADDRESS -> print http response
```

## Dirb
```
dirb URL
dirb URL wordlist
```

## Browsh
```
browsh --startup-url url -> render the web in the terminal
```

## Lynx
```
lynx URL -> view text of the web
```

## Nmap
```
nmap IP_ADDRESS -p80 -sV --script http-enum
nmap IP_ADDRESS -p80 -sV --script http-headers
nmap IP_ADDRESS -p80 -sV --script http-methods --script-args http-methods.url-path=DIR
nmap IP_ADDRESS -p80 -sV --script http-webdav-scan --script-args http-methods.url-path=/webdav-dir/
nmap IP_ADDRESS -p80 -sV --script banner
```

## Metasploit
```
auxiliary/scanner/http/http_version
auxiliary/scanner/http/brute_dir
auxiliary/scanner/http/robots_txt
```

## Curl
```
curl IP_ADDRESS | more
```

## Wget
```
wget URL
```

![[1.1.1 - Website Recon & Footprinting#Interesting files]]