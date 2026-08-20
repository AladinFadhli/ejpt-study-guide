# Web Application Tools

For the [web application testing](../methodology/07-web-application.md) phase.

> Use only against web applications you own or are authorised to test. Practise against deliberately vulnerable apps in your [lab](../labs/README.md).

## The core: Burp Suite

An intercepting proxy that sits between your browser and the target, letting you see and modify every request and response. Central to web testing. Key features at the eJPT level:

| Feature | Purpose |
|---|---|
| **Proxy** | Intercept, inspect, and modify HTTP(S) traffic |
| **Repeater** | Resend and tweak individual requests |
| **Intruder** | Automate parameter fuzzing (rate-limited in the free edition) |
| **Target/site map** | Build a picture of the application |
| **Decoder** | Encode/decode data |

Learning to read and modify raw requests in Burp is the single most valuable web skill for the exam.

## Content discovery

| Tool | Purpose |
|---|---|
| **gobuster** | Fast directory/file and DNS brute forcing |
| **ffuf** | Flexible, fast web fuzzer for content and parameters |
| **dirb / dirbuster** | Directory brute forcing |
| **feroxbuster** | Recursive content discovery |

Content discovery is web enumeration — it reveals hidden pages, admin panels, backups, and config files that are often the path in.

## Scanning and fingerprinting

| Tool | Purpose |
|---|---|
| **nikto** | Web server misconfiguration and known-issue scanning |
| **whatweb** | Technology fingerprinting |
| **wpscan** | WordPress-specific enumeration (plugins, themes, users) |

## Vulnerability-specific

| Tool | Purpose |
|---|---|
| **sqlmap** | Automated SQL injection detection and exploitation. Understand SQLi manually first, or you won't recognise when sqlmap is right or wrong |

## The discipline

Tools accelerate web testing, but the exam rewards understanding *why* an input is vulnerable. Use `sqlmap` after you understand SQL injection, not instead of understanding it — the same goes for every automated web tool. Burp plus your own comprehension beats any scanner run blindly.
