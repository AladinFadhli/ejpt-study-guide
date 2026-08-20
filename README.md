# eJPT — eLearnSecurity Junior Penetration Tester Study Guide

Free, open study material for INE Security's **eJPT** certification: methodology notes, tool reference, lab setup guides, and reporting templates.

> **Legal and ethical use only.** This repo teaches penetration testing methodology for a professional certification. Only ever test systems you own or have written permission to test. Read [ETHICS.md](ETHICS.md) before anything else.

> **No exam content.** Everything here is written from the published exam objectives and general methodology — never from actual exam tasks, which are under NDA. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## About the exam

The eJPT is INE's entry-level, **fully hands-on** penetration testing certification. There is no multiple-choice theory paper — you work in a live lab and answer questions tied to what you find and compromise.

| | |
|---|---|
| **Provider** | INE Security (formerly eLearnSecurity) |
| **Level** | Entry-level / junior |
| **Format** | Hands-on lab with dynamic questions tied to your findings |
| **Duration** | 48 hours |
| **Style** | Open-book, practical |
| **Prerequisites** | None formally; comfort with TCP/IP, common ports, and the Linux CLI expected |
| **Associated course** | INE's Penetration Testing Student (PTS) learning path |

> The eJPT was refreshed in 2026 with expanded reconnaissance and web application coverage and new material on using generative AI responsibly in pentesting. Always confirm the current objectives on the [official exam page](https://ine.com/security/certifications/ejpt-certification) — INE revises these.

## Exam domains

Based on the published objectives, weighted approximately:

| Domain | Weight | Covered in |
|---|---|---|
| Host and Network Penetration Testing | ~35% | [methodology/04](methodology/04-exploitation.md), [05](methodology/05-post-exploitation.md), [06](methodology/06-pivoting.md) |
| Assessment Methodologies | ~25% | [methodology/01](methodology/01-information-gathering.md), [02](methodology/02-scanning-enumeration.md) |
| Host and Networking Auditing | ~25% | [methodology/03](methodology/03-vulnerability-assessment.md) |
| Web Application Penetration Testing | ~15% | [methodology/07](methodology/07-web-application.md) |

Weightings shift between exam revisions — treat these as guidance and the official objectives as authoritative.

## Repository layout

```
methodology/   The penetration testing workflow, phase by phase
tools/         What each standard tool does and when to reach for it
labs/          How to build a legal practice lab, and where to find targets
reporting/     How to document findings, with a template
study-plan/    A structured plan and a progress tracker
resources.md   Curated free and paid learning resources
```

## How to use this repo

The eJPT rewards **methodical enumeration** above everything. Most people who struggle don't struggle because a technique is too advanced — they struggle because they didn't enumerate thoroughly and missed the obvious path.

1. Work through [methodology](methodology/) in order — it mirrors a real assessment.
2. For each phase, read the matching entries in [tools](tools/) and actually run them in your [lab](labs/).
3. Practise on the target types in [labs](labs/) until the workflow is muscle memory.
4. Learn the [reporting](reporting/) format — the exam expects you to interpret findings, not just collect flags.

## The eJPT mindset

- **Enumerate, then enumerate again.** Every open port is a question. Every service is a lead. The answer is almost always something you can find, not something you have to guess.
- **Take notes obsessively.** Every host, port, service, version, credential, and finding. You will need them, and note-taking is a skill the exam rewards.
- **Follow the methodology even when it feels slow.** Skipping enumeration to jump to exploitation is the single most common reason people get stuck.
- **The path exists.** Exam labs are designed to be solvable. If you're stuck, you missed something in enumeration — go back.

## Disclaimer

Community project, not affiliated with or endorsed by INE Security. "eJPT" and "eLearnSecurity" are trademarks of their respective owners. Provided for education. You are responsible for using it legally. The [official exam page](https://ine.com/security/certifications/ejpt-certification) is authoritative.

## License

[MIT](LICENSE) for structure; study content under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
