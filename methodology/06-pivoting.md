# Phase 6 — Pivoting

Using a compromised host to reach systems you couldn't reach directly. This is a defining eJPT skill and one of the more conceptually challenging parts of the exam.

> Conceptual and methodological. Practise in your own [lab](../labs/README.md).

---

## Why pivoting exists

Networks are segmented. Your attacking machine can usually reach only the "edge" — a public-facing host. Behind it sit internal systems on networks you have no route to. A compromised edge host, however, *can* reach them. Pivoting turns that host into your route inward.

This mirrors real network penetration testing: the first compromise is rarely the goal; it's the doorway to the internal network.

## The core concept

Your compromised host has two (or more) network interfaces or routes:
- One facing you (how you got in)
- One facing an internal network you couldn't previously see

Pivoting makes traffic from your tools flow *through* the compromised host to reach that internal network.

## Discovering the internal network

Once on a host, part of situational awareness is spotting the pivot opportunity:
- Additional network interfaces on the host
- Internal IP ranges in the routing table and ARP cache
- Connections to hosts you couldn't reach directly
- Internal hostnames in configuration and hosts files

If a compromised machine has a second interface on `10.x` or `172.16.x` that your attacker box can't reach, that's your pivot.

## Techniques (conceptually)

| Technique | The idea |
|---|---|
| **Port forwarding** | Forward a specific port on the compromised host to a service on an internal host, so you reach that one service |
| **SSH tunnelling** | Use SSH's local, remote, and dynamic forwarding to route traffic through a host you have SSH access to |
| **SOCKS proxy** | Create a proxy through the compromised host so many tools can reach the whole internal network |
| **Routing through a framework** | Metasploit can add a route through a session and run further modules against the internal network |

**Dynamic forwarding / SOCKS** is the most flexible: it lets you point a range of tools at the internal network through one tunnel, rather than forwarding one port at a time.

**Proxychains** is the standard way to force command-line tools through a SOCKS proxy so they reach internal hosts.

## The pivoting workflow

1. Compromise the edge host
2. Establish situational awareness; discover the internal network
3. Set up a tunnel or route through the compromised host
4. **Enumerate the internal network** through the pivot — you're back to Phase 2, just from a new position
5. Exploit an internal host
6. Repeat as needed (double pivoting) to go deeper

Note that step 4 is enumeration again. Every new position in the network restarts the methodology from scanning. This is the whole game: enumerate, exploit, reposition, enumerate again.

## Why people find this hard

Pivoting trips people up because you're now reasoning about *two* network positions at once — where your tools run and where your traffic exits. Draw the network. A simple diagram of "my box → compromised host → internal network" prevents most confusion. Keep updating it as you move.

## Tools for this phase

See [tools/pivoting.md](../tools/pivoting.md) for SSH tunnelling, `proxychains`, `chisel`-style tunnelling concepts, and Metasploit routing/autoroute.

---

## Phase checklist

- [ ] Identified additional interfaces/routes on the compromised host
- [ ] Mapped the internal network range
- [ ] Established a tunnel, proxy, or route inward
- [ ] Enumerated internal hosts through the pivot
- [ ] Drew/updated a network diagram of your positions
- [ ] Exploited internal targets as the methodology dictates

➡️ Next: [Phase 7 — Web Application Testing](07-web-application.md)
