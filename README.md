# detection-engineering-portfolio
Detection rules in Sigma, mapped to MITRE ATT&amp;CK, with conversions to KQL (Sentinel) and AQL (QRadar).
# Detection Engineering Portfolio

A library of threat detection rules written in **Sigma** (vendor-neutral YAML format), mapped to **MITRE ATT&CK**, and converted to platform-native query languages (**KQL** for Microsoft Sentinel, **AQL** for IBM QRadar).

## About

I'm **Subramanian V**, a Senior Cyber Security Engineer with 13+ years of experience in SIEM detection engineering, SOC operations, and cloud security. This portfolio demonstrates my Detection-as-Code practice and approach to threat detection.

- **Certifications:** AWS Certified Security – Specialty, CEH (Practical)
- **Platforms:** IBM QRadar (AQL), Microsoft Sentinel (KQL), CrowdStrike Falcon NGSIEM, Falcon Fusion SOAR
- **Focus:** Detection engineering, cloud threat detection & response, threat hunting

## Methodology

Each detection follows a structured lifecycle:

1. **Hypothesis** based on a MITRE ATT&CK technique or threat intelligence
2. **Data source identification** — what telemetry surfaces this activity
3. **Sigma rule development** — vendor-neutral YAML
4. **Conversion** to platform-native queries (KQL, AQL)
5. **Testing** against known-good and known-bad activity (Atomic Red Team)
6. **Tuning** for false positive reduction
7. **Deployment + measurement** of detection efficacy

## Repository Structure
/rules/         — Sigma rules (.yml)
/examples/      — Converted KQL and AQL queries
/docs/          — Detection methodology, writeups

## Detection Coverage

| Technique | MITRE ID | Sigma Rule | Status |
|-----------|----------|------------|--------|
| _Coming soon_ | _T1xxx_ | _rule.yml_ | _In progress_ |

## Contact

- **LinkedIn:** [Add your LinkedIn URL]
- **Email:** subramanian.kkd@gmail.com
- **Location:** Chennai, India

---

*This portfolio is actively under development as part of my detection engineering practice. New rules and writeups added regularly.*
