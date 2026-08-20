# Phase 2 — Scanning and Enumeration

The heart of the eJPT. If you do this phase thoroughly, everything after it becomes easy. If you rush it, you get stuck. This is the phase to be obsessive about.

---

## The scanning workflow

1. **Discover live hosts** (from Phase 1)
2. **Port scan** each host to find open ports
3. **Service and version detection** on those ports
4. **Enumerate each service** individually and deeply

The mistake to avoid: scanning ports, seeing a service, and jumping straight to exploitation. Enumerate the service *first*. The version, configuration, and exposed content usually hand you the way in.

## Port scanning concepts

- **TCP connect scan** — completes the full handshake. Reliable, noisier, no special privileges.
- **SYN (half-open) scan** — sends SYN, doesn't complete. Faster, stealthier, needs privileges.
- **UDP scan** — slow and unreliable but essential. DNS, SNMP, TFTP, and others live on UDP and are easy to overlook.

**Port states:** open (service listening), closed (nothing listening, host reachable), filtered (a firewall is dropping probes). Filtered vs closed tells you about the network defences.

Well-known ports worth memorising: 21 FTP, 22 SSH, 23 Telnet, 25 SMTP, 53 DNS, 80 HTTP, 110 POP3, 139/445 SMB, 143 IMAP, 161 SNMP, 443 HTTPS, 3306 MySQL, 3389 RDP, 5432 PostgreSQL.

## Scanning strategy for the exam

- **Scan all ports**, not just the top 1000. The interesting service is often on a high, non-standard port. Missing it is the classic reason people can't find the path.
- **Then run version detection and default scripts** against the open ports you found.
- **Don't forget UDP** on at least the common UDP services.

The trade-off is speed vs coverage. A fast top-ports scan first gives you something to work with; a full all-ports scan running in the background ensures you miss nothing.

## Service enumeration — the real work

Each service is enumerated differently. What you're looking for in each case:

| Service | Enumerate for |
|---|---|
| **FTP (21)** | Anonymous login, writable directories, version vulnerabilities |
| **SSH (22)** | Version, supported auth methods, weak credentials |
| **SMTP (25)** | User enumeration via VRFY/EXPN/RCPT, open relay |
| **DNS (53)** | Zone transfer, additional records |
| **HTTP/HTTPS (80/443)** | Directories, files, technologies, virtual hosts, parameters — a whole sub-phase (see [web application](07-web-application.md)) |
| **POP3/IMAP (110/143)** | Version, credentials |
| **SMB (139/445)** | Shares, null sessions, users, OS info, version vulnerabilities |
| **SNMP (161)** | Community strings, system info, running processes, sometimes credentials |
| **MySQL/PostgreSQL (3306/5432)** | Default/weak credentials, accessible databases |
| **RDP (3389)** | Version, credentials, NLA status |

### SMB deserves special attention

SMB is one of the richest enumeration targets on Windows networks and appears constantly:
- **Null sessions** — unauthenticated connections that may reveal users, shares, and policies
- **Share enumeration** — readable/writable shares often contain credentials or sensitive files
- **User enumeration** — feeds later password attacks
- **Version** — older SMB implementations have well-known vulnerabilities

### SNMP is easy to overlook

Running on UDP 161, SNMP with a default community string (often `public`) can dump enormous amounts of system detail — running processes, installed software, network configuration, and sometimes credentials in process arguments. Always check it.

## The enumeration mindset

Treat every open port as an unanswered question. Write down what you find on each. When you feel stuck later, the answer is almost always a service you enumerated too shallowly. Come back and go deeper before reaching for anything more advanced.

## Tools for this phase

See [tools/scanning-enumeration.md](../tools/scanning-enumeration.md) for `nmap` (and its scripting engine), `enum4linux`, `smbclient`, `smbmap`, `snmpwalk`, `onesixtyone`, `nikto`, `whatweb`, and more.

---

## Phase checklist

- [ ] Full TCP port scan completed on every host
- [ ] Key UDP ports checked
- [ ] Version and default-script scan run against open ports
- [ ] Every service enumerated individually and deeply
- [ ] SMB checked for null sessions, shares, and users
- [ ] SNMP checked with common community strings
- [ ] Credentials, versions, and exposed content recorded per host

➡️ Next: [Phase 3 — Vulnerability Assessment](03-vulnerability-assessment.md)
