# Phase 7 — Web Application Penetration Testing

Web testing expanded in the 2026 eJPT update. You need working familiarity with how web apps are structured and the common vulnerability classes, tested at a junior level.

> Conceptual and methodological. Practise against deliberately vulnerable web apps in your own [lab](../labs/README.md).

---

## Web fundamentals you must be solid on

- **HTTP methods** — GET, POST, PUT, DELETE, and what each is for
- **Status codes** — 200, 301/302, 401, 403, 404, 500 and what they tell you
- **Requests and responses** — headers, cookies, parameters, body
- **Sessions and cookies** — how state is tracked, session identifiers
- **Same-origin basics** — what an "origin" is

You cannot test what you don't understand structurally. A proxy that lets you see and modify every request (Burp Suite) is how you develop this fluency.

## Web enumeration

Before looking for vulnerabilities, map the application:

| Task | Purpose |
|---|---|
| **Directory/file discovery** | Find hidden pages, admin panels, backups, config files |
| **Technology fingerprinting** | Server, framework, CMS, language |
| **Virtual host discovery** | Multiple sites on one IP |
| **Parameter discovery** | Inputs that might be vulnerable |
| **Spidering/crawling** | Map all reachable pages and inputs |

Directory and content discovery is to web apps what port scanning is to hosts — the enumeration that reveals where to look. An exposed admin panel or a forgotten backup file is often the whole path.

## Common vulnerability classes

Understand what each is, how to recognise it, and its impact. (Described conceptually — practise the mechanics in your lab.)

| Vulnerability | Concept | Impact |
|---|---|---|
| **SQL injection** | Untrusted input reaches a database query | Data theft, auth bypass, sometimes code execution |
| **Cross-site scripting (XSS)** | Untrusted input reflected/stored and executed in a victim's browser | Session theft, actions as the victim |
| **Command injection** | Untrusted input reaches a system command | Code execution on the server |
| **File inclusion (LFI/RFI)** | App includes files based on input | File disclosure, sometimes code execution |
| **File upload flaws** | Unrestricted upload of executable content | Code execution |
| **Authentication flaws** | Weak login, default creds, broken session handling | Account takeover |
| **IDOR** | Accessing others' objects by changing an identifier | Unauthorised data access |
| **Directory traversal** | `../` sequences to escape the web root | Read arbitrary files |

For the eJPT, the priorities are **SQL injection, XSS, command injection, file inclusion, and directory traversal** — recognising them, understanding why they occur, and exploiting basic instances in a lab.

## The input-trust idea

Nearly every web vulnerability comes down to one principle: **the application trusted input it should have validated.** SQL injection, XSS, command injection, file inclusion — all are the same root cause in different contexts. Understanding that makes the categories cohere rather than being a list to memorise, and it's exactly what defenders and testers both reason about.

## Web testing workflow

1. **Enumerate** — map the app, discover content, fingerprint tech
2. **Identify inputs** — every parameter, form, header, and cookie is a candidate
3. **Test each input** for the relevant vulnerability classes
4. **Confirm** a finding by demonstrating impact
5. **Use it** — turn a web vulnerability into a foothold on the host where appropriate
6. **Record** with enough detail to reproduce and report

## Connecting web to host

Web testing on the eJPT isn't isolated — a web vulnerability is frequently the route to a shell on the underlying server, which then rejoins the host methodology (post-exploitation, pivoting). Keep the whole picture in view: the web app is often the front door to the network.

## Tools for this phase

See [tools/web-application.md](../tools/web-application.md) for Burp Suite, `gobuster`/`ffuf`/`dirb`, `nikto`, `whatweb`, `sqlmap`, and `wpscan`.

---

## Phase checklist

- [ ] Solid on HTTP methods, status codes, cookies, sessions
- [ ] Enumerated directories, files, and technologies
- [ ] Identified all inputs
- [ ] Tested for the priority vulnerability classes
- [ ] Confirmed findings by demonstrating impact
- [ ] Turned web access into host access where applicable
- [ ] Recorded findings for the report

⬅️ Back to [README](../README.md) · Next: [reporting](../reporting/README.md)
