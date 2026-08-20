# Practice Targets

Where to get legal, authorised targets to practise against. All of these are either yours to run locally or platforms that explicitly authorise you to attack their targets.

## Run locally (your own lab)

Intentionally vulnerable machines and applications designed for training. Run them on an isolated network per the [home lab setup](home-lab-setup.md).

| Target type | What it's for |
|---|---|
| **Vulnerable Linux/Windows VMs** | Full host compromise practice: enumeration → exploitation → privilege escalation |
| **Deliberately vulnerable web apps** | Web vulnerability classes in a safe environment |
| **Multi-host lab networks** | Pivoting and lateral movement practice |

Well-known training projects include intentionally vulnerable web applications (for SQLi, XSS, and similar) and vulnerable-by-design boot-to-root VMs. These are built and published specifically to be attacked for learning.

## Authorised online platforms

These platforms provide targets you are **explicitly permitted** to attack as part of using the service — legal reps without building anything:

| Platform | Good for |
|---|---|
| **Hack The Box** | Boot-to-root machines; realistic host compromise. Has beginner tracks |
| **TryHackMe** | Guided, beginner-friendly rooms; excellent for learning the methodology step by step |
| **VulnHub** | Downloadable vulnerable VMs to run in your own lab |
| **PentesterLab** | Web-focused exercises |
| **PortSwigger Web Security Academy** | Free, high-quality web vulnerability labs from the makers of Burp Suite |

## A sensible progression for eJPT prep

1. **TryHackMe** beginner paths — learn the workflow with guidance
2. **PortSwigger Academy** — build real web testing skill for free
3. **Hack The Box** easy machines — practise the full methodology unguided
4. **Local multi-host lab** — practise pivoting
5. **VulnHub boot-to-root VMs** — end-to-end reps under your own steam

The aim throughout: run the [methodology](../methodology/) so many times it becomes automatic.

## The boundary

Everything on this page is either yours or explicitly authorises your testing. That authorisation is what makes it legal. Never point these skills at anything outside your lab or these platforms without written permission — the [ethics guidance](../ETHICS.md) is not optional reading.
