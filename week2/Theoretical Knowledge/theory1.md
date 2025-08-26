# Alert Priority Levels: SOC Guide

## Overview

Alert priority levels in Security Operations Centers (SOCs) are essential for categorizing incidents according to **severity**, **urgency**, and **business impact**. This structured triage enables security teams to respond efficiently to a range of threats, from minor alerts to catastrophic breaches[web:6][web:11].

---

## Core Concepts

### Priority Definitions

| Level     | Description                                                                                            | Example                                   |
|-----------|--------------------------------------------------------------------------------------------------------|-------------------------------------------|
| Critical  | Imminent severe damage (ransomware, data breach, major service outage). Requires immediate action.      | Ransomware encryption in production server|
| High      | Serious threats (privilege escalation, unauthorized admin access) targeting important assets.            | Attacker gains admin access              |
| Medium    | Moderate risk incidents (malware, phishing, limited scope misconfigurations).                           | Isolated malware infection                |
| Low       | Minor or informational events with low likelihood of escalation.                                        | Blocked memory exploit                    |

Severity encapsulates both the level of impact and urgency for response, guiding escalation protocols.

---

### Assignment Criteria

- **Asset Criticality:** Greater priority for threats targeting essential assets, e.g. production servers, databases.
- **Exploit Likelihood:** Incidents involving known vulnerabilities with public exploits warrant higher urgency, such as Log4Shell (CVE-2021-44228).
- **Business Impact:** Financial, reputational, or compliance risks escalate the priority of incidents.
- **CVSS Scores:** Numerical mapping helps standardize severity and urgency; a score of 9.8 is Critical, especially on important systems.

---

## Scoring Systems

### CVSS (Common Vulnerability Scoring System)

A global standard for measuring and communicating vulnerability severity:

| CVSS Score | Rating    |
|:----------:|-----------|
| 0.0        | None      |
| 0.1–3.9    | Low       |
| 4.0–6.9    | Medium    |
| 7.0–8.9    | High      |
| 9.0–10.0   | Critical  |

**Metric Groups:**
- **Base:** Intrinsic vulnerability attributes (exploitability, impact scope).
- **Temporal:** Time-sensitive contextual changes (exploit code availability, remediation).
- **Environmental:** Local organization context (asset value, controls, likely impact).

Scores are provided as numbers and as vector strings, so scoring can always be recalculated and verified.

### SOC Tools (Splunk, SIEMs)

- Alert risk scores combine severity, threat likelihood, asset value, and external intelligence feeds to automate ticket prioritization.
- Splunk and similar platforms often auto-escalate incidents above CVSS 9 or targeting key assets.

---

## Case Study: Log4Shell (CVE-2021-44228)

- CVSS score of 9.8 (Critical) due to remote code execution and prevalence across environments.
- Elevated immediately to Critical, prompting rapid patching and monitoring in real SOCs.
- SOCs used both CVSS scores and business context to prioritize assets for urgent remediation.

---
