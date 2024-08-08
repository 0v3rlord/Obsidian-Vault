- R-Services are a [[Linux Remote Management]] Protocol

- R-Services are only accessible through a suite of programs called **R-Commands**.

- Uses Pluggable Authentication Modules(**PAM**) for authentication.


#### R-Commands

| **Command** | **Service Daemon** | **Port** | **Transport Protocol** | **Description**                                                                                                                                                                                                                                                            |
| ----------- | ------------------ | -------- | ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `rcp`       | `rshd`             | 514      | TCP                    | Copy a file or directory bidirectionally from the local system to the remote system (or vice versa) or from one remote system to another. It works like the `cp` command on Linux but provides `no warning to the user for overwriting existing files on a system`.        |
| `rsh`       | `rshd`             | 514      | TCP                    | Opens a shell on a remote machine without a login procedure. Relies upon the trusted entries in the `/etc/hosts.equiv` and `.rhosts` files for validation.                                                                                                                 |
| `rexec`     | `rexecd`           | 512      | TCP                    | Enables a user to run shell commands on a remote machine. Requires authentication through the use of a `username` and `password` through an unencrypted network socket. Authentication is overridden by the trusted entries in the `/etc/hosts.equiv` and `.rhosts` files. |
| `rlogin`    | `rlogind`          | 513      | TCP                    | Enables a user to log in to a remote host over the network. It works similarly to `telnet` but can only connect to Unix-like hosts. Authentication is overridden by the trusted entries in the `/etc/hosts.equiv` and `.rhosts` files.                                     |
| `rstat`     |                    |          |                        |                                                                                                                                                                                                                                                                            |
| `ruptime`   |                    |          |                        |                                                                                                                                                                                                                                                                            |
| `rwho`      |                    |          |                        |                                                                                                                                                                                                                                                                            |


# Footprinting the Service

**Nmap**
```bash
sudo nmap -sV -p512,513,514 $TARGET
```


**Logging In**
```bash
rlogin $TARGET -l user
```


**List Authenticated Users**
```bash
# With rwho
rwho

# With rusers
rusers -al $TARGET
```


