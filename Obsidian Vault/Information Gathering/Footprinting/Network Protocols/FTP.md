### Info
Command channel: **21 TCP**
Data channel: 20 TCP

Two modes:
	- Active- Client must have an open port to transfer data. (You will need to change your firewall and port-forward)
	- Passive- Server must have open port to transfer data.

### Useful Commands
Download All Available Files
```bash
wget -m --no-passive ftp://anonymous:anonymous@$TARGET
```

### TFTP
TFTP stands for Trivial [[File Transfer]] Protocol. It uses UDP instead of TCP.
TFTP does not use authentication, instead it relies on read/write permissions of the operating system.

 TFTP Commands:

| Command | Description                                                                   |
| ------- | ----------------------------------------------------------------------------- |
| connect | Sets the host with optional port for file transfers.                          |
| get     | Transfers files from remote to local. (Download)                              |
| put     | Transfers files from local to remote. (Upload)                                |
| quit    | Exits TFTP.                                                                   |
| status  | Shows transfer mode (ASCII or binary), connection status, timeout value, etc. |
| verbose | Displays additional information during file transfer.                         |
Note most TFTP commands will work for FTP.


# Footprinting the Service

[[Nmap]] FTP scripts will be useful.


### Service Interaction
```bash
nc -nv $TARGET 21     # Using Netcat
telnet $TARGET 21     # Using Telnet

# If the target uses TLS/SSL, it will be slightly different
openssl s_client -connect $TARGET -starttls ftp
```


