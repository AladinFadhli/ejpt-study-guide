# How to Write a Penetration Test Report

A practical guide to the standard structure and what makes each part good. Use fictional or lab data only in anything you publish.

## Who reads it

A report usually serves two audiences:
- **Executives** — want the business impact and the bottom line, in plain language
- **Technical staff** — want the detail to reproduce, understand, and fix each finding

Good reports serve both, which is why they're layered: a high-level summary up front, technical detail behind it.

## Standard structure

### 1. Executive summary
Plain-language overview for non-technical readers. What was tested, the overall security posture, the most significant risks, and the key recommendations. No jargon. Someone deciding on budget should understand it.

### 2. Scope and methodology
What was in scope (systems, addresses, applications), the timeframe, and the approach taken. This sets expectations and bounds the engagement. Note what was explicitly *out* of scope.

### 3. Findings
The core. Each finding should include:

| Element | Purpose |
|---|---|
| **Title** | Clear, specific name |
| **Severity** | Risk rating (e.g. Critical/High/Medium/Low/Info) |
| **Description** | What the vulnerability is |
| **Affected assets** | Which hosts/apps/endpoints |
| **Impact** | What an attacker could do — the business consequence |
| **Evidence** | Screenshots, request/response, output proving it |
| **Reproduction** | Steps to observe it again |
| **Remediation** | Specific, actionable fix |

### 4. Technical details / attack narrative
The story of how the assessment unfolded — how findings connected, how one led to another. This shows the chained risk that individual findings can hide.

### 5. Recommendations
Prioritised remediation guidance, strategic as well as per-finding. What to fix first and why.

### 6. Appendices
Tool output, full host lists, supporting data.

## Rating severity

Severity generally combines **impact** (how bad if exploited) and **likelihood** (how easy to exploit). A remote unauthenticated code-execution flaw on a public host is critical; a low-impact information disclosure reachable only by an authenticated admin is low. Be consistent, and justify ratings rather than asserting them.

## What separates a good report

- **Impact stated in business terms**, not just technical ones. "An attacker can read the customer database" beats "SQL injection present."
- **Evidence for every finding.** A claim without proof is not actionable.
- **Reproducible steps.** The client's team must be able to see it themselves.
- **Actionable remediation.** "Patch to version X", "disable anonymous access", not "improve security."
- **Professional tone.** Factual, clear, free of hype. You're informing decisions, not showing off.
- **No false positives.** Verify before you report. A report full of unconfirmed scanner output destroys trust.

## The mindset

Write for the reader who has to *fix* the problem and the reader who has to *fund* the fix. If both can act on your report, it's a good one.
