# Incident Classification in SOC Workflows

## Overview

Incident classification is foundational for effective security operations. It enables teams to assign the correct response and communicate about threats in a consistent, actionable way. Leveraging taxonomies and metadata, SOCs can manage incidents ranging from malware infections to insider threats[web:26][web:28].

---

## Core Concepts

### Incident Categories

Incidents are categorized by type, providing a clear label for investigation and mitigation:

| Category          | Description                                           | Example                                  |
|-------------------|------------------------------------------------------|------------------------------------------|
| Malware           | Malicious software infection                         | Endpoint infected by ransomware          |
| Phishing          | Deceptive attempt to obtain sensitive info           | Employee clicks fake email link          |
| DDoS              | Distributed denial of service attack                 | Network overwhelmed by botnet traffic    |
| Insider Threat    | Harmful action by trusted user                       | Unauthorized data export by employee     |
| Data Exfiltration | Stealing sensitive information                       | Malicious script uploads key data offsite|

These categories help prioritize workflows and reporting across SOCs.

---

## Taxonomy Frameworks

### MITRE ATT&CK

The MITRE ATT&CK framework systematically organizes cyber incident behaviors in terms of **tactics** (attacker objectives) and **techniques** (methods used):

- **Tactics**: e.g., Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Command and Control, Exfiltration, Impact, Resource Development, Reconnaissance[web:24][web:28].
- **Techniques**: e.g., Phishing (T1566), Process Injection, Pass-the-Hash, etc.
- **Sub-Techniques**: More granular variations, e.g., Spearphishing Link vs Attachment.
- Every incident can be mapped to MITRE ATT&CK IDs (e.g., phishing = T1566).

### ENISA Incident Taxonomy

ENISA provides standardized categories and event definitions to harmonize reporting across Europe, facilitating metrics and strategy at scale.

### VERIS (Vocabulary for Event Recording and Incident Sharing)

VERIS enables structured sharing of incident data with standardized fields for event types, threat actions, actor motives, and asset impact.

---

## Contextual Metadata

Enrich incidents with detailed information to advance investigation:

- **Affected Systems**: Hostnames, asset IDs, or systems targeted
- **Timestamps**: Date/time for each event and detection
- **Source IPs**: Originating addresses, mapped to external or internal sources
- **Indicators of Compromise (IOCs)**: Malicious hashes, suspected URLs, suspicious file signatures

Properly labeled metadata makes searching, correlation, and automated response fast and accurate.

---

