# Pivoting Tools

For the [pivoting](../methodology/06-pivoting.md) phase.

> Use only against systems you own or are authorised to test.

## Concepts first

Pivoting routes your traffic through a compromised host to reach an internal network. The tools implement a few core ideas:

| Idea | What it achieves |
|---|---|
| **Local port forward** | Reach one internal service via a local port on your machine |
| **Remote port forward** | Expose a service back through the tunnel |
| **Dynamic forward (SOCKS)** | Route many tools to the whole internal network through one proxy |

## Tools

| Tool | Purpose |
|---|---|
| **SSH** | Built-in tunnelling: local (`-L`), remote (`-R`), and dynamic/SOCKS (`-D`) forwarding. The first choice when you have SSH access |
| **proxychains** | Forces command-line tools through a SOCKS proxy so they reach internal hosts |
| **chisel** | TCP/UDP tunnelling over HTTP, useful when SSH isn't available; client/server model |
| **Metasploit routing** | `autoroute` and `route` add a route through a session; run further modules against the internal network |
| **Metasploit portfwd** | Meterpreter's port forwarding for reaching specific internal services |
| **socat** | Relaying and forwarding connections |

## The workflow with tools

1. Confirm the compromised host can reach the internal network (situational awareness)
2. Establish a tunnel or route:
   - Have SSH access? SSH dynamic forwarding + proxychains is clean and flexible
   - Have a Meterpreter session? autoroute + a SOCKS proxy module
   - Neither? A tool like chisel
3. Point your enumeration tools at the internal range **through** the tunnel
4. Enumerate and exploit internal hosts as normal

## Keep a diagram

The single most useful habit for pivoting: draw your positions. "Attacker → compromised host (interface A / interface B) → internal network." Update it as you move. Most pivoting confusion is losing track of which host reaches which network, and a diagram fixes that instantly.
