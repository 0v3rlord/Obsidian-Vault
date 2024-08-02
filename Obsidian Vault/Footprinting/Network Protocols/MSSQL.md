Port: **1433 TCP**
MSSQL uses [Transact SQL(**T-SQL**)](https://www.tutorialspoint.com/t_sql/index.htm) 
### Clients
- SQL Server Management Studio (**SSMS**)
- mssql-cli
- SQL Server PowerShell
- HeidiSQL
- SQLPro
- Impacket mssqlclient.py

### MSSQL Databases
| Default System Database | Description                                                                                                                                                                                            |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `master`                | Tracks all system information for an SQL server instance                                                                                                                                               |
| `model`                 | Template database that acts as a structure for every new database created. Any setting changed in the model database will be reflected in any new database created after changes to the model database |
| `msdb`                  | The SQL Server Agent uses this database to schedule jobs & alerts                                                                                                                                      |
| `tempdb`                | Stores temporary objects                                                                                                                                                                               |
| `resource`              | Read-only database containing system objects included with SQL server                                                                                                                                  |
*Table source:* [System Databases Microsoft Doc](https://docs.microsoft.com/en-us/sql/relational-databases/databases/system-databases?view=sql-server-ver15)

# Footprinting the Service
msf6 auxiliary(**scanner/mssql/mssql_ping**)
###### Nmap NSE Scripts
```bash
sudo nmap --script ms-sql-info,ms-sql-empty-password,ms-sql-xp-cmdshell,ms-sql-config,ms-sql-ntlm-info,ms-sql-tables,ms-sql-hasdbaccess,ms-sql-dac,ms-sql-dump-hashes --script-args mssql.instance-port=1433,mssql.username=sa,mssql.password=,mssql.instance-name=MSSQLSERVER -sV -p 1433 $TARGET
```

###### Connect With MsSqlClient.py
```bash
python3 mssqlclient.py Administrator@$TARGET -windows-auth
```

