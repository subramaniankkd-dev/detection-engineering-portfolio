# Sigma Detection Rules — KQL & AQL Conversions

A starter set of five [Sigma](https://github.com/SigmaHQ/sigma) detection rules, each
mapped to MITRE ATT&CK and converted into **KQL** (Microsoft Sentinel / Defender XDR)
and **AQL** (IBM QRadar). Built as a portfolio of platform-agnostic detection
engineering work.

## Why Sigma

Sigma is a generic, vendor-neutral signature format for SIEM detections. A single
rule can be authored once and converted to any backend, which keeps detection logic
portable across QRadar, Sentinel, Splunk, Elastic, and others.

## Rules

| # | Rule | ATT&CK | Tactic | Severity |
|---|------|--------|--------|----------|
| 01 | Kerberoasting — RC4 service ticket request | T1558.003 | Credential Access | High |
| 02 | LSASS memory access (credential dumping) | T1003.001 | Credential Access | High |
| 03 | PowerShell EncodedCommand execution | T1059.001 / T1027 | Execution / Defense Evasion | Medium |
| 04 | AWS root account console login | T1078.004 | Privilege Escalation / Persistence | High |
| 05 | Linux reverse shell via common interpreters | T1059.004 | Execution | High |

## Repository Structure

```
sigma-detections/
├── README.md
├── LICENSE
├── rules/                  # Sigma source rules (.yml)
│   ├── 01_kerberoasting_service_ticket_request.yml
│   ├── 02_lsass_memory_access.yml
│   ├── 03_powershell_encoded_command.yml
│   ├── 04_aws_root_console_login.yml
│   └── 05_linux_reverse_shell.yml
└── conversions/
    ├── kql/all_rules.kql   # Microsoft Sentinel / Defender XDR
    └── aql/all_rules.aql   # IBM QRadar
```

## Converting Sigma Rules Yourself

These conversions were written manually for accuracy, but you can regenerate them
with [sigma-cli](https://github.com/SigmaHQ/sigma-cli):

```bash
pip install sigma-cli
sigma plugin install microsoft365defender   # KQL backend
sigma plugin install qradar-aql              # AQL backend

# Convert a single rule to KQL
sigma convert -t microsoft365defender rules/02_lsass_memory_access.yml

# Convert to QRadar AQL
sigma convert -t qradar-aql rules/02_lsass_memory_access.yml
```

## Tuning Notes

- **Thresholds** (e.g. Kerberoasting request count) must be baselined per environment.
- **Field/property names** in the AQL queries assume parsed QRadar custom properties;
  map them to your DSM and QIDs.
- **Filters** for legitimate processes (AV/EDR, backup agents) reduce false positives
  but should be reviewed against your asset inventory.
- All rules are marked `experimental` — validate in a test offense/incident pipeline
  before promoting to production alerting.

## License

MIT — see [LICENSE](LICENSE).
