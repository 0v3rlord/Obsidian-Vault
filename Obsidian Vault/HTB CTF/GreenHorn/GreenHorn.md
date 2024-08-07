![[GreenHorn.png]]
#pwned
# Information Gathering
`sudo nmap -sS $target -p- -T4 --min-rate=1000 -oN initial.nmap`
```bash
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
3000/tcp open  ppp
```

## Service Scan
`sudo nmap -sVC $target -T4 -p22,80,3000 -oN services.nmap`

## Port 80 Enumeration
- Potential Foothold: **http://greenhorn.htb/?file=
- Admin panel: **http://greenhorn.htb/login.php
- Using **pluck 4.7.18** CMS. **Multiple CVEs** discovered.
- https://github.com/SecBridge/Cms_Vuls/blob/main/Pluckcms/Pluck_v4.7.18_Any_File_Upload_Getshell.md
- **Need admin password to exploit!**

Directories:

## Port 3000 Enumeration
- gitea

Discovered sha512 hash
Cracking reveals **password: iloveyou1**

# Exploitation
Site backdoored by uploading a zip file containing php webshell.

Discovered user **junior:iloveyou1** #

# Rooting
Use [Depix.py](https://github.com/spipm/Depix/) on the obfuscated password image, revealing root password:
![[obfuscatedpwd.png]]

![[output.png]]

**root:sidefromsidetheothersidesidefromsidetheotherside**