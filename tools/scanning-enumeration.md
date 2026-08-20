# Scanning and Enumeration Tools

For the [scanning and enumeration](../methodology/02-scanning-enumeration.md) and [vulnerability assessment](../methodology/03-vulnerability-assessment.md) phases. The most important toolset on the eJPT.

## The core: Nmap

Nmap is the backbone of this phase. Understand these capabilities rather than memorising flags:

| Capability | Purpose |
|---|---|
| **Host discovery** | Find live hosts before port scanning |
| **Port scanning** | TCP (connect and SYN) and UDP scans to find open ports |
| **Service/version detection** | Identify what's running and which version |
| **OS detection** | Fingerprint the operating system |
| **Default scripts** | Safe enumeration scripts against discovered services |
| **Nmap Scripting Engine (NSE)** | Categorised scripts: discovery, safe, vuln, auth, brute, and more |

Workflow habit: a quick scan to get moving, a **full all-ports scan** so you miss nothing, then version detection and default scripts against what you found. Add targeted UDP scanning for DNS, SNMP, and TFTP.

## Per-service enumeration

| Tool | Service | Purpose |
|---|---|---|
| **enum4linux** / **enum4linux-ng** | SMB | Users, shares, groups, policies, OS info |
| **smbclient** | SMB | Connect to and browse shares |
| **smbmap** | SMB | Enumerate shares and permissions |
| **rpcclient** | SMB/MSRPC | Query Windows via RPC (users, groups) |
| **snmpwalk** | SNMP | Walk the MIB for system details |
| **onesixtyone** | SNMP | Fast community-string brute forcing |
| **nbtscan** | NetBIOS | NetBIOS name enumeration |
| **showmount** | NFS | List NFS exports |
| **whatweb** | HTTP | Identify web technologies |
| **nikto** | HTTP | Web server vulnerability scanning |

## Vulnerability lookup

| Tool | Purpose |
|---|---|
| **searchsploit** | Offline search of Exploit-DB for known exploit material by product/version |
| **Nmap vuln scripts** | NSE scripts that check for specific known vulnerabilities |

## The key discipline

Nmap tells you *what's there*; the per-service tools tell you *what you can do with it*. Beginners stop at the Nmap output. The marks — and the footholds — are in the per-service enumeration that follows. When stuck, this is almost always where you didn't go deep enough.
