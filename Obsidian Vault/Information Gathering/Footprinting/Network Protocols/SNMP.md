- Ports: 161 UDP(**command**), 162 UDP(**trap**)

- Simple Network Monitoring Protocol(**SNMP**) was created to monitor network devices. SNMP can also handle configuration tasks and change settings remotely.

- The Management Information Base(**MIB**) is a text file in where SNMP objects are listed. It contains at least one OID. MIBs do not contain data, but show how to find the data. Returns values for specified OID.

- An Object Identifier(**OID**) is a node in a tree. Many nodes only contain references to those below them.


# Footprinting the Service
###### Tools:
- snmpwalk
- onesixtyone
- braa
It is recommended to create custom wordlists to crack community strings.

Try **snmpwalk** first. Use **onesixtyone** with **SecLists** to identify unknown community strings.

Once you know a community string, use with **braa** to brute-force OIDs.