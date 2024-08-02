- Intelligent Platform Management Interface(**IPMI**) is used for hardware-based host management systems and monitoring.

- Port: **623 UDP**

- Acts as an autonomous subsystem within the host.

IPMI requires the following components:
- Baseboard Management Controller(**BMC**)- Micro-controller
- Intelligent Chassis Management Bus (**ICMB**)- Interface for inter-chassis' communication.
- Intelligent Platform Management Bus(**IPMB**)- Extends to BMC
- IPMI Memory- Stores things such as: system event log, repo store data, etc.


# Footprinting the Service

**Nmap Version Scan**
```bash
sudo nmap -sU --script=ipmi-version -p623 $TARGET
```

**MSF Version Scan**
```
msf6> use auxiliary/scanner/ipmi/ipmi_version
```

**Default Passwords**

| Product         | Username      | Password                                              |
| --------------- | ------------- | ----------------------------------------------------- |
| Dell iDRAC      | root          | calvin                                                |
| HP iLO          | Administrator | Random 8 char string of numbers and UPPERCASE letters |
| Supermicro IPMI | ADMIN         | ADMIN                                                 |
**Hashcat**
```bash
hashcat -m 7300 ipmi.txt -a 3 ?1?1?1?1?1?1?1?1 -1 ?d?u
```

To retrieve IPMI hashes, we can use the Metasploit [IPMI 2.0 RAKP Remote SHA1 Password Hash Retrieval](https://www.rapid7.com/db/modules/auxiliary/scanner/ipmi/ipmi_dumphashes/) module.
```bash
use auxiliary/scanner/ipmi/ipmi_dumphashes 
```
