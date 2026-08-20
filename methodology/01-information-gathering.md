# Phase 1 — Information Gathering (Reconnaissance)

The first phase of every assessment. The goal is to build a picture of the target before touching it aggressively. On the eJPT this maps to the Assessment Methodologies domain.

---

## Passive vs active reconnaissance

- **Passive** — gathering information without directly interacting with the target's systems (public records, DNS, search engines, certificate transparency logs). The target doesn't see you.
- **Active** — directly interacting with target systems (pinging, port scanning, banner grabbing). Faster and richer, but visible in logs.

In a lab or exam you move quickly to active recon. In a real engagement, passive recon comes first and stays within your authorised scope.

## What you're trying to learn

- What hosts exist (the live network)
- What services those hosts run, and what versions
- What the organisation looks like (domains, subdomains, technologies)
- Anything that hints at a weakness — old software, exposed services, information disclosure

## Passive techniques and their purpose

| Technique | What it reveals |
|---|---|
| **WHOIS lookup** | Domain registration, org contacts, name servers |
| **DNS enumeration** | A, MX, NS, TXT records; mail and infrastructure hints |
| **Subdomain discovery** | Additional attack surface beyond the main site |
| **Certificate transparency logs** | Subdomains and hosts from issued TLS certificates |
| **Search engine dorking** | Exposed files, directories, login pages via targeted queries |
| **Technology fingerprinting** | CMS, frameworks, server software in use |

Purpose to internalise for the exam: **every piece of passive recon narrows down where to point active tools.** You're not collecting trivia; you're building a target list.

## DNS — the concepts that matter

DNS record types you should recognise:
- **A / AAAA** — hostname to IPv4 / IPv6
- **MX** — mail servers
- **NS** — authoritative name servers
- **TXT** — arbitrary text, often SPF/DKIM, sometimes information disclosure
- **CNAME** — aliases
- **PTR** — reverse lookup, IP to hostname

**Zone transfer (AXFR)** — a misconfigured DNS server may hand over its entire zone, revealing every record at once. Always worth testing against a discovered name server; when it works, it's a goldmine of hostnames. Most servers correctly refuse it, but the check is cheap.

## Host discovery — mapping the live network

Before scanning ports, find which hosts are actually up. Approaches:
- ICMP echo (ping sweep) — simple, often filtered
- ARP scanning — reliable on a local network segment
- TCP/UDP probes to common ports — works when ICMP is blocked

The output of this stage is a list of live IPs. Everything downstream operates on that list.

## Note-taking starts now

From the very first command, record:
- Every IP that responds
- Every hostname you discover
- Every domain and subdomain
- Anything unusual

A simple structure — one file per host, plus a master list — is enough. The habit matters more than the tool. Good notes are what let you pivot later without re-scanning.

## Tools for this phase

See [tools/reconnaissance.md](../tools/reconnaissance.md) for `whois`, `dig`, `nslookup`, `host`, `dnsenum`, `dnsrecon`, `sublist3r`, `theHarvester`, `netdiscover`, and `arp-scan`, with what each is for.

---

## Phase checklist

- [ ] Identified in-scope hosts and domains
- [ ] Enumerated DNS records; tested for zone transfer
- [ ] Discovered subdomains and additional attack surface
- [ ] Fingerprinted technologies where a web presence exists
- [ ] Built a list of live hosts for scanning
- [ ] Recorded everything in structured notes

➡️ Next: [Phase 2 — Scanning and Enumeration](02-scanning-enumeration.md)
