- **WinRM** is a [[Windows Remote Management]] Protocol.
- Ports: **5985 TCP/HTTP, 5586 TCP/HTTPS**
- Services such as remote sessions with PowerShell or event log merging require WinRM.

# Footprinting the Service
##### Nmap
```bash
sudo nmap -sVC $TARGET -p5985,5986
```

##### Interacting with WinRM using Evil WinRM
```bash
evil-winrm -i $TARGET -u USERNAME -p PASSWORD
```
