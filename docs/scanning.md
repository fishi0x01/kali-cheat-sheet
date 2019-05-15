# Scanning

[Port Scanning](#cidr-port-scan)
[DNS Enumeration](#dns-enumeration)
[HTTP Enumeration](#http-enumeration)
[POP3](#pop3)
[MySQL](#mysql)
[SMB](#smb)

## CIDR Port Scan

**nmap top 1000 TCP ports:**
```
nmap -sT --top-ports 1000 <cidr>
```

**nmap top 1000 TCP/UDP ports:**
```
nmap -sT -sU --top-ports 1000 <cidr>
```

## DNS enumeration

**zone transfer with nmap:**
```
nmap --script dns-zone-transfer --script-args dns-zone-transfer.domain=<domain> -p53 <ip>
```

```
host -t axfr <domain> <ip>
```

```
dig axfr @<ip> <domain>
```

**nsec enumeration with nmap:**
```
nmap --script dns-nsec-enum --script-args dns-nsec-enum.domains=<domain> -p53 <ip>

- or -

nmap --script dns-nsec3-enum --script-args dns-nsec3-enum.domains=<domain> -p53 <ip>
```

## HTTP enumeration

**nmap:**
```
nmap --script http-enum --script-args http-enum.displayall -p80 <ip>
```

**dirbuster (GUI):**
```
dirbuster -l /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -u <url>
```

## POP3

**info via nmap:**
```
nmap --script pop3-ntlm-info -p 110,995 <ip>
```

**capabilities via nmap:**
```
nmap --script pop3-capabilities -p 110,995 <ip>
```

## MySQL

**info via nmap:**
```
nmap --script mysql-info -p3306 <ip>
```

**anonymous access via nmap:**
```
nmap --script mysql-empty-password -p 3306 <ip>
```

## SMB

**OS discovery via nmap:**
```
nmap --script smb-os-discovery -p139,445 <ip>
```

**check security modes via nmap:**
```
nmap --script smb-security-mode,smb2-security-mode -p139,445 <ip>
```

**enumerate users via nmap:**
```
nmap --script smb-enum-users -p139,445 <ip>
```
