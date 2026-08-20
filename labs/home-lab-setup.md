# Home Lab Setup

A self-contained penetration testing lab on your own hardware. Everything stays on an isolated virtual network you control — nothing here touches systems you don't own.

## What you need

- A host machine with enough RAM (16 GB comfortable, 8 GB workable) and disk
- A **hypervisor** — VirtualBox (free) or VMware Workstation Player
- An **attacker VM** — Kali Linux or Parrot OS (both are purpose-built pentesting distributions with the tools preinstalled)
- One or more **target VMs** — intentionally vulnerable machines (see [practice targets](practice-targets.md))

## Network isolation — the important part

Configure your VMs on a **host-only** or **internal** network, not bridged. This keeps the vulnerable targets off your real network and off the internet. Vulnerable-by-design machines are exactly what you don't want reachable from anywhere else.

A typical layout:
- Attacker VM and target VMs on the same host-only network
- No route from that network to your LAN or the internet for the targets
- Snapshots taken before you start, so you can reset targets quickly

## Suggested build order

1. Install the hypervisor
2. Create the Kali/Parrot attacker VM; update it; take a snapshot
3. Add a vulnerable target VM on a host-only network
4. Confirm the attacker can reach the target and *cannot* reach your real network from the target
5. Practise the full methodology against the target
6. Snapshot targets before attacking so you can reset and repeat

## Practising pivoting locally

To practise [pivoting](../methodology/06-pivoting.md), build a small multi-network lab: one target with two interfaces (one on the attacker network, one on a second internal network) and a second target only on that internal network. Now the only way to the second target is through the first — exactly the exam scenario.

## Reset discipline

Take snapshots liberally. When you break a target (you will), roll back rather than rebuild. This keeps you practising instead of reinstalling.
