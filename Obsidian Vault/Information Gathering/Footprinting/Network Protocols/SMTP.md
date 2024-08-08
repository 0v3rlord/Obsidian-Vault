- Simple Mail Transfer Protocol (SMTP) is for sending emails in an IP network.
- Often combined with IMAP/POP3 for receiving (and sending) emails.
- **Port: 25** (Newer servers may use other ports such as **587 TCP**)
- Other ports may also be used for encryption, such as **port 465** TCP.

### Definitions
- **MUA**: Mail User Agent- Email Client
- **MTA**: Mail Transfer Agent- Email Server (sends and recieves)
- **MSA**: Mail Submission Agent- Aka relay server, checks the validity of the email. Important for **[[Open Relay Attack]]**.
- **MDA**: Mail Delivery Agent- Transfers email to mailbox.

Client(**MUA**) -> Submission Agent(**MSA**) -> Open Relay(**MTA**) -> 
  Mail Delivery Agent(**MDA**) -> Mailbox(**IMAP/POP3**)


### Commands
```bash
telnet $TARGET 25      # Connect to target
```

| **Command**  | **Description**                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------ |
| `AUTH PLAIN` | AUTH is a service extension used to authenticate the client.                                     |
| `HELO`       | The client logs in with its computer name and thus starts the session.                           |
| `MAIL FROM`  | The client names the email sender.                                                               |
| `RCPT TO`    | The client names the email recipient.                                                            |
| `DATA`       | The client initiates the transmission of the email.                                              |
| `RSET`       | The client aborts the initiated transmission but keeps the connection between client and server. |
| `VRFY`       | The client checks if a mailbox is available for message transfer.                                |
| `EXPN`       | The client also checks if a mailbox is available for messaging with this command.                |
| `NOOP`       | The client requests a response from the server to prevent disconnection due to time-out.         |
| `QUIT`       | The client terminates the session.                                                               |


# Footprinting the Service

```bash
# Default nmap scripts sends EHLO
sudo nmap -sVC $TARGET -p25 

# This NSE script determines if the server is a relay
sudo nmap -p25 --script=smtp-open-relay -v
```

