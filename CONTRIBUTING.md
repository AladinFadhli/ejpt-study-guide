# Contributing

Thanks for helping improve this study guide. The goal is to help people learn the methodology and pass the exam, legally and professionally.

## Ground rules

**No live targets, no working exploit payloads.** This repo teaches methodology, concepts, tool usage, and lab practice. Contributions must not include ready-to-run exploit code aimed at real systems, credentials, data from real engagements, or anything targeting infrastructure you don't own. Techniques are described at the level needed to understand, defend against, and reproduce them in your own lab.

**No exam dumps.** These are hands-on, often open-book practical exams under NDA. Do not submit exam tasks, flags, target details, or specific walkthroughs of the real exam. Doing so violates the certification agreement and can revoke your certification. Describe *methodology* the exam tests, never the exam content itself.

**Respect the licence of anything you reference.** Link to tool documentation rather than copying it. Cite sources.

## What's welcome

- Corrections where a tool, flag, or technique has changed
- Clearer explanations of a concept or phase
- Additions to the methodology that reflect current practice
- Lab setup improvements and additional legal practice targets
- Reporting templates and examples (using fictional/lab data only)
- Fixes to commands that no longer work with current tool versions

## How to contribute

1. Fork and branch: `git checkout -b fix/nmap-flag-update`
2. Make the change
3. Commit with a clear message
4. Open a pull request using the template

## Style

- Explain the *why*, not just the command. A command with no context teaches nothing.
- Keep examples lab-oriented — use RFC 1918 addresses, `target`, or `10.10.10.x`, never real hosts.
- Prefer tables for tool/flag references.
- Note tool version where behaviour is version-specific.
- Keep depth at the exam's level.

## Code of conduct

By participating you agree to the [Code of Conduct](CODE_OF_CONDUCT.md) and the [ethics guidance](ETHICS.md). Be decent, especially to beginners.
