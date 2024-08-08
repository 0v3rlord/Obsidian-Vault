# Subdomain Brute-Force Enumeration

 By using carefully crafted **wordlists**, you can significantly increase the efficency and effectiveness of your enumeration.

This process is broken into **4 steps**:
1. **Wordlist Selection**: Wordlists can be
   - *General Purpose*- Broad range of common subdomains
   - *Targeted*- Focuses on specific industries, tech, or naming conv
   - *Custom*- Create your own wordlist based on keywords, patterns, or target intelligence.

2. **Iteration and Querying**: Tool iterates through wordlist appending subdomains to target domain.
3. **DNS Lookup**: A query is performed for each potential subdomain use A or AAAA records.
4. **Filtering and validation**: If the query resolves successfully, subdomain is added to valid list of subdomains. Further validation or verification steps may be taken.

# Effective Tools
| Tool                                                    | Description                                                                                                                     |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [[dnsenum]]                                             | Comprehensive DNS enumeration tool that supports dictionary and brute-force attacks for discovering subdomains.                 |
| [fierce](https://github.com/mschwager/fierce)           | User-friendly tool for recursive subdomain discovery, featuring wildcard detection and an easy-to-use interface.                |
| [dnsrecon](https://github.com/darkoperator/dnsrecon)    | Versatile tool that combines multiple DNS reconnaissance techniques and offers customisable output formats.                     |
| [amass](https://github.com/owasp-amass/amass)           | Actively maintained tool focused on subdomain discovery, known for its integration with other tools and extensive data sources. |
| [assetfinder](https://github.com/tomnomnom/assetfinder) | Simple yet effective tool for finding subdomains using various techniques, ideal for quick and lightweight scans.               |
| [puredns](https://github.com/d3mondev/puredns)          | Powerful and flexible DNS brute-forcing tool, capable of resolving and filtering results effectively.                           |
