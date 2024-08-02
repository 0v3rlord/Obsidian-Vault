[[Enumeration Cheat Sheet]]
### Principles
- There is more than meets the eye. Consider ALL points of view.
- Distinguish between what we see and what we don't.
- There are always ways to gain more information. Understand the target.

### Methodology

Divided into 3 levels:
	- [[Infrastructure-based Enumeration]]
	- [[Host-based Enumeration]]
	- OS-based Enumeration

Layers:

| Layer                  | Description                                                                                        | Information Catergories                                                                       |
| ---------------------- | -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 1. Internet Presence   | Identification of internet presence and externally accessible infrastructure.                      | Domains, Subdomains, vHosts, ASN, Netblocks, IP Addresses, Cloud Instances, Security Measures |
| 2. Gateway             | Identify possible security measures to protect the companies external and internal infrastructure. | Firewalls, DMZ, IPS/IDS, EDR, Proxies, NAC, Network Segmentation, VPN, Cloudflare             |
| 3. Accessible Services | Identify accessible services that are hosted externally or internally.                             | Service Type, Functionality, Configuration, Port, Version, Interface                          |
| 4. Processes           | Identify the internal processes, sources, and destinations associated with the services.           | PID, Process Data, Task, Source, Destination                                                  |
| 5. Privileges          | Identification of the internal permissions and privileges to the accessible services.              | Groups, Users, Permissions, Restrictions, Environment                                         |
| 6. OS Setup            | Identification of the internal components and systems setup.                                       | OS Type, Patch Level, Network Config, OS Environment, Config Files, Sensitive Private Files   |

Layer 1:
	The goal of this layer is to identify all the possible target systems and interfaces that can be tested.

Layer 2:
	The goal is to understand what we are dealing with and what to watch out for.

Layer 3:
	This layer aims to understand the reason and functionality of the target system and gain the necessary knowledge communicate with it and exploit it for out purposes effectively.

Layer 4:
	The goal is to understand the factors associated with the processes and identify dependencies between them.

Layer 5:
	It is crucial to identify privileges and understand what is and isn't possible with them.

Layer 6:
	The goal is to see how the administrators manage the systems and what sensitive internal information can be gleaned out of them.

