# Penetration Test Report — Template

> A reusable skeleton. Fill with **fictional or lab data only** when practising. Replace bracketed placeholders.

---

# Penetration Test Report

**Client:** [Fictional Client / Lab Name]
**Assessment type:** [Network / Web Application / Internal]
**Date:** [Date range]
**Author:** [Your name]
**Version:** [1.0]
**Classification:** Confidential

---

## 1. Executive Summary

[2–4 short paragraphs in plain language: what was tested, the overall posture, the most significant risks in business terms, and the headline recommendations. No technical jargon.]

**Summary of findings:**

| Severity | Count |
|---|---|
| Critical | [n] |
| High | [n] |
| Medium | [n] |
| Low | [n] |
| Informational | [n] |

---

## 2. Scope and Methodology

**In scope:**
- [Systems, IP ranges, applications]

**Out of scope:**
- [Anything explicitly excluded]

**Timeframe:** [Dates]

**Methodology:** [Brief description of the phased approach: information gathering, scanning and enumeration, vulnerability assessment, exploitation, post-exploitation, reporting.]

---

## 3. Findings

### 3.1 [Finding Title]

| | |
|---|---|
| **Severity** | [Critical/High/Medium/Low/Info] |
| **Affected assets** | [Hosts / endpoints] |

**Description**
[What the vulnerability is.]

**Impact**
[What an attacker could achieve — in business terms.]

**Evidence**
[Screenshots, request/response, tool output demonstrating the finding.]

**Reproduction steps**
1. [Step]
2. [Step]

**Remediation**
[Specific, actionable fix.]

---

*(Repeat 3.x for each finding, ordered by severity.)*

---

## 4. Attack Narrative

[The story of the assessment: how you moved from initial access through the environment, how findings chained together, what the realistic attack path looked like end to end.]

---

## 5. Recommendations

**Immediate (Critical/High):**
- [Prioritised actions]

**Short-term (Medium):**
- [Actions]

**Strategic:**
- [Broader improvements: patching processes, credential policy, segmentation, monitoring]

---

## 6. Appendices

**Appendix A — Hosts and services**
[Full inventory.]

**Appendix B — Tool output**
[Supporting raw output.]
