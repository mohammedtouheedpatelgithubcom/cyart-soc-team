SOC Analyst Knowledge Framework

Author: Mohammed Touheed Patel

Date: August 21, 2025

Purpose: This document defines the foundational knowledge areas for effective Security Operations Center (SOC) functioning, focusing on alert prioritization, incident classification, and incident response. It is designed to bring consistency, structure, and efficiency to investigations.

1. Alert Priority Levels
Core Concepts

    Priority Definitions

        Critical: Incident poses immediate and severe impact (e.g., ransomware actively encrypting production servers).

        High: Incident with high risk, potential lateral movement, or unauthorized high-privilege activity (e.g., admin account compromise).

        Medium: Moderate threat with limited impact or systems at risk (e.g., user workstation infected with malware but contained).

        Low: Minimal impact, often noisy detections or test environments (e.g., scan from known source against a non-essential VM).

    Assignment Criteria

        Asset Criticality: Business value of the affected system (Production DB > Test VM).

        Exploit Likelihood: Availability of public exploits (e.g., active exploit kits for a CVE).

        Business Impact: Potential financial, reputational, or operational damage.

    Example:

        Log4Shell (CVE-2021-44228); CVSS score: 9.8 → Critical priority.

    Scoring Systems

        CVSS (Common Vulnerability Scoring System): Quantifies risk with Base, Temporal, and Environmental metrics.

        SOC Tool Risk Scores (e.g., Splunk Enterprise Security): Combine threat intelligence, asset data, and alert history to prioritize responses.

Key Objective

Ensure that analysts can quickly and consistently assess alert severity to direct resources toward the highest-risk threats.
How to Learn

    Study CVSS Scoring System via FIRST.org.

    Review NIST SP 800-61 guidelines for incident severity classification.

    Analyze real-world advisories (e.g., CISA’s Log4Shell guidance).

🔹 Severity Matrix (Example)
Priority	Definition	Example
Critical 🚨	Immediate, high business impact, active exploitation	Ransomware encrypting production database
High ⚠️	Serious risk, but not yet service-disrupting	Unauthorized admin login on AD controller
Medium 🔧	Limited impact, isolated system risk	Malware detected on single employee workstation
Low ℹ️	Informational or low business relevance	Port scan from known IP on test VM
🔹 Severity Assignment Example

    New CVE detected: Log4Shell (CVE-2021-44228)

    CVSS Score: 9.8 (Critical)

    Asset Affected: Public-facing web server (production)
    ✅ Priority Assigned: Critical


2. Incident Classification
Core Concepts

    Incident Categories

        Malware infection (e.g., malicious executable or ransomware).

        Phishing attack (e.g., spear-phishing email with credential-harvesting link).

        DDoS attack (e.g., service outage due to massive request flooding).

        Insider threat (e.g., employee exfiltrating sensitive IP).

        Data exfiltration (e.g., large outbound data transfer to untrusted IP).

    Taxonomy Frameworks

        MITRE ATT&CK: Standardized tactics (goal) → techniques (method). Example: T1566 = Phishing.

        ENISA Incident Taxonomy: Broad EU-based classification for SOC incident categorization.

        VERIS (Vocabulary for Event Recording and Incident Sharing): Common language for incident data sharing and reporting.

    Contextual Metadata

        Details such as timestamps, affected system, user accounts, IOCs (hashes, C2 domains, IPs).

        Enrichment with threat intelligence (e.g., VirusTotal hash lookup).

Key Objective

Enable consistent incident categorization across the SOC, ensuring structured reporting, knowledge sharing, and faster investigations.
How to Learn

    Explore MITRE ATT&CK Navigator for mapping alerts to techniques.

    Study ENISA Incident Taxonomy and VERIS Framework.

    Review case studies of phishing and malware campaigns (e.g., SANS Reading Room).

🔹 Classification Table (Example)
Category	Framework Mapping	Mini Example
Phishing	MITRE Technique T1566	Malicious email with fake login page sent to finance user
Malware	VERIS: Malware Action	Suspicious executable dropped via USB
DDoS	ENISA: Availability Incident	Public site down due to traffic flooding
Insider Threat	VERIS: Misuse	Employee exporting client data to USB
🔹 Metadata Example (Phishing Case)

    Incident Type: Phishing

    Targeted User: CFO mailbox

    IOC: Malicious domain login-portal[.]abc

    Timestamp: Aug 19, 2025, 14:23 UTC
    ✅ Classified as Phishing (MITRE T1566)

3. Basic Incident Response
Core Concepts

    Incident Lifecycle (NIST SP 800-61)

        Preparation: Playbooks, communication plans, tools (SIEM, SOAR).

        Identification: Alert triage and validation via logs and telemetry.

        Containment: Isolate the affected system, block malicious domains.

        Eradication: Remove malware, disable compromised accounts.

        Recovery: Restore systems, monitor for re-infection.

        Lessons Learned: Post-incident report, update playbooks and defenses.

    Procedures

        System Isolation: Quarantine compromised hosts.

        Evidence Preservation: Acquire memory dumps, store log files, perform file hashing.

        Communications: Use proper escalation paths and stakeholder notifications.

        Automation with SOAR: Use orchestration tools (e.g., Splunk SOAR/Phantom) for routine containment.

Key Objective

Achieve readiness to detect, contain, neutralize, and learn from incidents to improve resilience over time.
How to Learn

    Study NIST SP 800-61 Incident Handling Guide.

    Use SANS Incident Handler’s Handbook templates.

    Explore hands-on simulations via Let’s Defend or similar SOC training platforms.

🔹 Incident Response Lifecycle (NIST-inspired flow)

Workflow: 

Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned

🔹 Mini Response Example (Phishing Incident)

    Preparation: Anti-phishing playbook in place

    Identification: SIEM alert triggered on suspicious email with attachment

    Containment: Blocked malicious sender + domain in mail gateway

    Eradication: Deleted malicious email from all inboxes

    Recovery: Reset CFO’s credentials, confirm MFA enabled

    Lessons Learned: Added rule in SOAR for auto-blocking similar domains

Conclusion

By mastering these three domains—Prioritization, Classification, and Response—SOC analysts build a structured approach to security operations. Clear prioritization reduces wasted resources, consistent classification enables standardized reporting, and strong response processes ensure that incidents are handled effectively and with long-term learning.



✅ Quick Summary Table
# Incident Management Quick Reference

| **Domain**                | **Goal**                                       | **Mini Example**                          |
|----------------------------|-----------------------------------------------|-------------------------------------------|
| **Alert Prioritization**   | Assign severity for efficient response        | CVSS 9.8 → **Critical**                   |
| **Incident Classification**| Categorize incident type with frameworks      | Phishing → **MITRE ATT&CK T1566**         |
| **Incident Response**      | Contain and eradicate threats                 | Block malicious sender & reset account    |
