# Critical TryHackMe Rooms for eJPT

A focused set of [TryHackMe](https://tryhackme.com/) rooms that build exactly the skills the eJPT tests. **These are considered essential preparation — work through all of them.**

They're ordered as a progression: concept-building rooms first, then guided practical rooms, then boot-to-root machines that make you run the full [methodology](../methodology/) unaided. Do them roughly in order — later rooms assume skills the earlier ones build.

> Only attack the target a room provisions for you. That's what TryHackMe authorises. Everything here is legal practice on authorised targets — see [ETHICS.md](../ETHICS.md).

---

## Stage 1 — Foundations

Build the core concepts before touching a full machine.

| Room | Focus | Reinforces |
|---|---|---|
| [Vulnerabilities 101](https://tryhackme.com/room/vulnerabilities101) | How vulnerabilities are found, scored, and researched | [Vulnerability assessment](../methodology/03-vulnerability-assessment.md) |
| [RootMe](https://tryhackme.com/room/rrootme) | Enumeration, web shell upload, basic privilege escalation | [Scanning](../methodology/02-scanning-enumeration.md), [exploitation](../methodology/04-exploitation.md), [post-exploitation](../methodology/05-post-exploitation.md) |
| [Introduction to Metasploit](https://tryhackme.com/room/metasploitintro) | The Metasploit framework end to end | [Exploitation](../methodology/04-exploitation.md), [tools](../tools/exploitation.md) |

## Stage 2 — Guided practical machines

Apply the full workflow with some guidance.

| Room | Focus | Reinforces |
|---|---|---|
| [Basic Pentesting](https://tryhackme.com/room/basicpentestingjt) | End-to-end beginner pentest | Full [methodology](../methodology/) |
| [Bounty Hacker](https://tryhackme.com/room/cowboyhacker) | Enumeration → foothold → privesc | [Scanning](../methodology/02-scanning-enumeration.md) through [post-exploitation](../methodology/05-post-exploitation.md) |
| [Blue](https://tryhackme.com/room/blue) | Exploiting a well-known Windows SMB vulnerability with Metasploit | Windows [exploitation](../methodology/04-exploitation.md), SMB [enumeration](../methodology/02-scanning-enumeration.md) |
| [Ice](https://tryhackme.com/room/ice) | Windows enumeration, exploitation, and privilege escalation | Windows [post-exploitation](../methodology/05-post-exploitation.md) |

## Stage 3 — Boot-to-root machines

Run the whole methodology with little or no hand-holding. This is the closest practice to the exam.

| Room | Focus | Reinforces |
|---|---|---|
| [Mr Robot](https://tryhackme.com/room/mrrobot) | Web enumeration, credential attacks, privesc | [Web](../methodology/07-web-application.md), full chain |
| [Joker CTF](https://tryhackme.com/room/jokerctf) | Web foothold, enumeration, privilege escalation | [Web](../methodology/07-web-application.md) → [post-exploitation](../methodology/05-post-exploitation.md) |
| [GoldenEye](https://tryhackme.com/room/goldeneye) | Enumeration, credential attacks, privesc | [Scanning](../methodology/02-scanning-enumeration.md), password attacks |
| [Bolt](https://tryhackme.com/room/bolt) | CMS enumeration and exploitation | [Web](../methodology/07-web-application.md) |
| [Easy Peasy](https://tryhackme.com/room/easypeasyctf) | Thorough enumeration, hidden services, privesc | [Scanning](../methodology/02-scanning-enumeration.md) — rewards deep enumeration |
| [Inferno](https://tryhackme.com/room/inferno) | Enumeration, credential attacks, privesc | Full chain |
| [Anonymous](https://tryhackme.com/room/anonymous) | FTP/SMB enumeration, privesc via misconfiguration | [Enumeration](../methodology/02-scanning-enumeration.md), [privesc](../methodology/05-post-exploitation.md) |
| [Relevant](https://tryhackme.com/room/relevant) | SMB enumeration, web foothold, Windows privesc | Windows full chain |
| [Hacker Note](https://tryhackme.com/room/hackernote) | Web exploitation and privilege escalation | [Web](../methodology/07-web-application.md) → [post-exploitation](../methodology/05-post-exploitation.md) |

---

## How to work these rooms

1. **Try before you look anything up.** Struggling through enumeration is where the learning happens — the exam gives you no walkthrough.
2. **Run the full methodology every time**, even when the room hints at a shortcut. The habit is what you're building.
3. **Take notes as if it were a real engagement** — every host, port, service, credential, and finding. Note-taking is an exam skill.
4. **When stuck, go back to enumeration** before searching for a hint. The path is almost always something you missed.
5. **After finishing, write a short summary** — how you got the foothold, how you escalated, and where you got stuck. Reviewing these is how weak spots surface.

## A note on walkthroughs

Walkthroughs are a learning aid, not a crutch. Use them to get *unstuck* after a genuine attempt, then understand *why* the step worked — never to speed-run a room. On the exam there's no walkthrough, so practice that way.

For reference, a community walkthrough for Mr Robot is available [here](https://rayenchallouf.github.io/posts/Mr-Robot-copy/) — treat it as a check on your own approach after you've tried, not a substitute for the attempt.

---

⬅️ Back to [labs](README.md) · See also [practice targets](practice-targets.md) for other platforms
