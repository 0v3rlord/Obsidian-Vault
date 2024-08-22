# IP: 10.10.11.23

NMAP permx.htb
Ports 22,80

No leads on http://permx.htb

subdomain enumeration

Found http://lms.permx.htb
Found vulnerability: **(CVE-2023-3533) Chamilo LMS**

Gained foothold as www-data
Linpeas reveals DB password
Credential reuse enables lateral movement to user mtz
Credentials found: **mtz:03F6lY3uXAP2bkW8**

We find we can run a script as sudo
Leverage this script to gain root access
#pwned 