- Secure Shell(**SSH**) is a [[Linux Remote Management]] protocol.
- Port: **22 TCP**

#### Authentication Methods
1. Password 
2. Public-key 
3. Host-based 
4. Keyboard 
5. Challenge-response 
6. GSSAPI 

# Footprinting the Service

**SSHAudit
```bash
./sshaudit.py $TARGET
```

**Set Preferred Authentication Method (useful for brute force)
```bash
ssh -v user@$TARGET -o PreferredAuthentications=password
```

##### Login with specified private key
```bash
chmod 600 id_rsa
ssh user@$TARGET -i id_rsa
```
