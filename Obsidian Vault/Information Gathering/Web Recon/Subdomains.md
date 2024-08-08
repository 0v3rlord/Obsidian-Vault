Subdomains often host valuable information and resources that aren't directly linked to main site. Subdomains are essential in [[Infrastructure-based Enumeration]].

# Why is This Important for [[Web Recon]]?

###### You may discover:
- Development and Staging Environments
- Hidden Login Portals
- Legacy Applications
- Sensitive Information

# Subdomain Enumeration

## [[Active Subdomain Enumeration]]
- Involved directly interacting with the domains DNS servers. One method is a [[DNS]] [[Zone Transfer]]. Due to security measures, this is rarely successful.
- A more common technique is brute-force. Use tools like [[dnsenum]], [[ffuf]], and [[gobuster]].

## Passive Subdomain Enumeration
- Relies on external sources. A valuable resource is [Certificate Transparency Logs(**CT**)](https://crt.sh/)
- Another approach is **Search Engines**.