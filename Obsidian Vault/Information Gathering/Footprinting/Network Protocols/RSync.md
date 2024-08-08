- RSync is a [[Linux Remote Management]] Protocol.

- RSync is used to efficently copy files over the network.

- **Port: 873**

# Footprinting the Service

**Nmap**
```bash
sudo nmap -sV -p873 $TARGET
```

**Probe Accessible Shares**
```bash
nc -nv 127.0.0.1 873

(UNKNOWN) [127.0.0.1] 873 (rsync) open
@RSYNCD: 31.0
@RSYNCD: 31.0
#list
dev            	Dev Tools
@RSYNCD: EXIT
```

**Enumerate Open Share**
```bash
# List files
rsync -av --list-only rsync://$TARGET/dev

# Download
rsync -av rsync://$TARGET/dev
```

**If RSync is Configured to Use SSH
```
rsync -av rsync://$TARGET/dev -e ssh
```

