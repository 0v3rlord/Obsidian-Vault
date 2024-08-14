## Gaining Situational Awareness
Run these basic commands to orient yourself.
- **whoami** - What user are we
- **id** - What groups are we part of
- **hostname** - Name of the server
- **ip a** - What subnet are we in? Do we have extra NICs in other subnets?
- **sudo -l** - Can we use sudo?

###### OS and Version 
```bash
cat /etc/os-release
```

###### PATH Variable
If misconfigured, can be used for priv esc.
```bash
echo $PATH
```

###### Environment Variables
```bash
env
```

###### CPU Type/Version
```bash
lscpu
```

###### List Login Shells
```bash
cat /etc/shells
```

##### Check for Defenses:
- Exec Shield
- iptables
- AppArmor
- SELinux
- Fail2ban
- Snort
- Uncomplicated Firewall(**ufw**)

###### List Block Devices/Filesystems/Drives
```bash
lsblk
```

###### Printer Information
```bash
lpstat
```


###### Check FSTAB for Mounted/Unmounted Filesystems =
You may find credentials for a mounted fs. Try grepping
```bash
cat /etc/fstab
```

###### Check Routing Table
You can see what networks are available for each interface.
```bash
route
netstat -rn

# In a domain environment, check here.
cat /etc/resolv.conf
```

###### Who is the host communicating with
```bash
arp -a
```

###### Existing Users
```bash
cat /etc/passwd
cat /etc/passwd | cut -f1 -d:
```

##### Common Hash Algorithms
| **Algorithm** | **Hash**       |
| ------------- | -------------- |
| Salted MD5    | `$1$`...       |
| SHA-256       | `$5$`...       |
| SHA-512       | `$6$`...       |
| BCrypt        | `$2a$`...      |
| Scrypt        | `$7$`...       |
| Argon2        | `$argon2i$`... |
###### Existing Groups
```bash
cat /etc/group
```

###### List Users of Interesting Groups
```bash
getent group <GROUP>
```

###### Mounted File Systems
```bash
df -h
```

###### Unmounted File Systems
```bash
cat /etc/fstab | grep -v "#" | column -t
```

###### All Hidden Files
```bash
find / -type f -name ".*" -exec ls -l {} \; 2>/dev/null | grep <USERNAME>
```

###### All Hidden Directories
```bash
find / -type d -name ".*" -ls 2>/dev/null
```

###### Temporary Files
```bash
ls -l /tmp /var/tmp /dev/shm
```

