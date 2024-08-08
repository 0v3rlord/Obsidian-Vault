- RDP is a [[Windows Remote Management]] Protocol.
- Port: **3389 TCP/UDP**

# Footprinting the Service
**Nmap**
```bash
sudo nmap -sVC $TARGET -p3389 --script=rdp* 
```

##### RDP Sec Check
Use rdp-sec-check.pl to identify security settings based on handshakes.

**Installation**
```bash
sudo cpan
cpan[1]> install Encoding::BER 

git clone https://github.com/CiscoCXSecurity/rdp-sec-check.git && cd rdp-sec-check
```

###### Authentication
- xfreerdp
- rdesktop
- Remmina
##### Connecting with xFreeRDP
```
xfreerdp /u:USERNAME /p:PASSWORD /v:$TARGET
```

