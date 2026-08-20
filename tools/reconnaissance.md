# Reconnaissance Tools

For the [information gathering](../methodology/01-information-gathering.md) phase.

| Tool | What it does | When to use |
|---|---|---|
| **whois** | Queries domain registration records | Early passive recon on a domain |
| **dig** | Flexible DNS lookup tool | Querying specific DNS records; testing zone transfer (AXFR) |
| **nslookup** | Simpler DNS query tool | Quick record lookups, cross-platform |
| **host** | Concise DNS lookup | Fast A/MX/NS checks |
| **dnsenum** | Automated DNS enumeration | Records, subdomains, and zone-transfer attempts in one run |
| **dnsrecon** | DNS reconnaissance | Broader DNS enumeration and brute forcing |
| **fierce** | DNS reconnaissance and subdomain discovery | Finding non-contiguous IP space and subdomains |
| **sublist3r** | Subdomain enumeration via public sources | Expanding web attack surface passively |
| **theHarvester** | Gathers emails, subdomains, hosts from public sources | OSINT on an organisation |
| **netdiscover** | ARP-based host discovery | Finding live hosts on a local segment |
| **arp-scan** | ARP scanner | Reliable local network host discovery |

## How they fit together

Start with `whois` and DNS tools (`dig`, `host`, `dnsenum`) to understand the domain and infrastructure. Use `sublist3r`/`theHarvester` to expand the attack surface. On a local network, `netdiscover` or `arp-scan` map live hosts before you scan ports.

The **zone transfer test** with `dig` against each discovered name server is a cheap, high-value check — when it succeeds it reveals every DNS record at once.

Every hostname and IP these produce goes into your notes and becomes the input to scanning.
