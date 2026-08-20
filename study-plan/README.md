# eJPT Study Plan

A structured path to exam-ready. Assumes a few hours on weekdays plus longer weekend sessions. Most people need **6–10 weeks** depending on starting point; adjust the calendar, keep the sequence.

The eJPT rewards hands-on repetition above all. This plan is built around *doing*, not just reading — each week pairs concepts with lab practice.

---

## Week 1 — Foundations and setup

- Build your [home lab](../labs/home-lab-setup.md): hypervisor, Kali/Parrot attacker VM, first vulnerable target
- Solidify prerequisites: TCP/IP, common ports, Linux CLI comfort
- Read [information gathering](../methodology/01-information-gathering.md) and practise recon tools against your lab

**Goal:** a working lab and comfort on the command line.

## Week 2 — Scanning and enumeration

- Read [scanning and enumeration](../methodology/02-scanning-enumeration.md) — the most important phase
- Drill Nmap until the workflow is automatic
- Practise per-service enumeration (SMB, SNMP, HTTP, FTP) against lab targets
- Start [TryHackMe](../labs/practice-targets.md) beginner rooms

**Goal:** enumerate any service thoroughly without a checklist.

## Week 3 — Vulnerability assessment and exploitation basics

- Read [vulnerability assessment](../methodology/03-vulnerability-assessment.md) and [exploitation](../methodology/04-exploitation.md)
- Learn Metasploit structure and workflow properly
- Practise reverse/bind shells and shell upgrades with netcat
- Compromise several easy boot-to-root machines end to end

**Goal:** reliably get a foothold on an easy target.

## Week 4 — Web application testing

- Read [web application testing](../methodology/07-web-application.md)
- Work through [PortSwigger Web Security Academy](../labs/practice-targets.md) — free and excellent
- Get fluent in Burp Suite: intercept, modify, repeat
- Practise content discovery and the priority vulnerability classes

**Goal:** recognise and exploit basic web vulnerabilities, and turn them into host access.

## Week 5 — Post-exploitation and privilege escalation

- Read [post-exploitation](../methodology/05-post-exploitation.md)
- Practise Linux and Windows privilege escalation enumeration
- Learn to read LinPEAS/WinPEAS output and act on it
- Gather and crack credentials in the lab

**Goal:** escalate from a limited shell to admin/root on common misconfigurations.

## Week 6 — Pivoting

- Read [pivoting](../methodology/06-pivoting.md) — conceptually the hardest part
- Build a multi-network lab and practise tunnelling and proxying
- Get comfortable with SSH forwarding, proxychains, and Metasploit routing
- Draw network diagrams as you go

**Goal:** reach and compromise an internal host through a pivot.

## Week 7 — Reporting and integration

- Read the [reporting](../reporting/README.md) guide and template
- Do full end-to-end boot-to-root machines and **write a short report** for each
- Refine your note-taking system until reporting is easy
- Time yourself; build stamina for long sessions

**Goal:** run the whole methodology unaided and document it.

## Week 8+ — Consolidation

- Attempt Hack The Box machines unguided
- Identify weak phases and drill them specifically
- Do a self-imposed mock: a fresh multi-host lab, full methodology, timed, with a report
- Review the whole [methodology](../methodology/) as a final pass

**Goal:** consistent, methodical, unaided compromise and documentation.

---

## Readiness criteria

- [ ] Home lab built, including a multi-network setup for pivoting
- [ ] Can enumerate any common service thoroughly from memory
- [ ] Comfortable with Metasploit and manual shells
- [ ] Can recognise and exploit basic web vulnerabilities
- [ ] Can escalate privileges on common Linux and Windows misconfigurations
- [ ] Can pivot to an internal network
- [ ] Have compromised many easy machines end to end, unaided
- [ ] Have a working note-taking and reporting system
- [ ] Completed several boot-to-root machines with written reports

Track progress in [progress-tracker.md](progress-tracker.md).

## Exam-day approach

- **Enumerate exhaustively before exploiting.** The path is almost always something you can find.
- **Take notes continuously** — hosts, ports, services, credentials, findings.
- **Use the full time.** It's 48 hours; there's no reward for rushing.
- **When stuck, go back to enumeration.** You missed something. That's almost always the fix.
- **Draw the network** as you discover it, especially for pivoting.
