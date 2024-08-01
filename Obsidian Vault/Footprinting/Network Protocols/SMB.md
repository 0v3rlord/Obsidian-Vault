Ports: 139, 445

Usually used by [[Windows]] hosts. Linux users can use Samba, which is  FOSS SMB.

Access rights are controlled by Access Control Lists (ACL), and are based on each share.

Samba uses Common Internet File System (CIFS), a "branch" of SMB.

### Commands
```bash
smbclient -N -L //$TARGET     // List shares
smbclient //$TARGET/share     // Access a share
```


# Footprinting the Service

###### 1. Scan ports 139 and 445. 
```bash
sudo nmap -sVC $TARGET -p139,445 
```

###### 2. Manually interact with service via Remote Procedure Call ([[RPC]])
```bash
rpcclient -U "" $TARGET
```

RPC Commands

| Query                    | Description                           |
| ------------------------ | ------------------------------------- |
| srvinfo                  | Server information.                   |
| enumdomains              | Enumerate all domains on the network. |
| querydominfo             | Domain, server, and user info.        |
| netshareenumall          | Enumerates all available shares.      |
| netsharegetinfo \<share> | Information about specified share.    |
| enumdomusers             | Enumerates all domain users.          |
| queryuser \<RID>         | Information about specified user.     |
```bash
# Brute-Force RIDs

for i in $(seq 500 1100);do rpcclient -N -U "" $TARGET -c "queryuser 0x$(printf '%x\n' $i)" | grep "User Name\|user_rid\|group_rid" && echo "";done

# Brute-Force RIDs with Impacket samrdump.py
python samrdump.py $TARGET
```

Other tools you can use include SMBMap, CrackMapExec, and Enum4Linux-ng.

