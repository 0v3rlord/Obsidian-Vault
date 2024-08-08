- Windows Management Instrumentation(**WMI**) is a [[Windows Remote Management]] Protocol.
- Is an extension of Common Information Model(**CIM**), which is core functionality of the standardized Web-Based Enterprise Management(**WBEM**) for the Windows platform.
- Allows **read and write access** to most Windows settings.
- Typically accessed via PowerShell, VBScript, or Windows Management Instrumentation Console(**WMIC**)
- WMI is not a single program but consists of several programs and databases, known as **repositories**.
- Port: **135/TCP**

# Footprinting the Service
##### Using WMIexec
```bash
wmiexec.py USERNAME:PASSWORD@$TARGET "HOSTNAME"
```
