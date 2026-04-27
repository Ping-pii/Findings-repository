# PIIRATES — Open Vulnerability Repository

> **Cross-sector anonymised vulnerability findings from offensive cybersecurity assessments.**  
> Maintained by [PIIRATES](https://www.piirates.fr) — French penetration testing specialist.

---

## About this repository

This repository centralises anonymised vulnerability findings identified during penetration tests and vulnerability assessments conducted by PIIRATES across regulated sectors in France and Europe.

**Every entry is:**
- Fully anonymised — no client, organisation or system can be identified
- Validated by a senior pentester before publication
- Mapped to MITRE ATT&CK, CVSS and relevant regulatory frameworks (NIS2, CRA, DORA, CER)
- Accompanied by a concrete remediation recommendation

**Current status:** This repository is being progressively populated. The anonymisation and validation process takes time — we prioritise quality over volume. New findings are added as missions are completed and reviewed.

---

## Why this exists

Offensive cybersecurity findings are rarely shared publicly. Each organisation that gets pentested learns about its own vulnerabilities — but the broader ecosystem misses the pattern.

We believe that anonymised, well-documented findings benefit everyone: operators can benchmark their exposure, developers can build more securely, regulators can better understand the real threat landscape.

This is a small contribution to closing that gap.

---

## Sector coverage

Findings are organised by sector, aligned with the NIS2 Directive (Annex I & II), CER Directive, and Cyber Resilience Act (CRA):

| Sector | NIS2 / Regulation | Status |
|--------|-------------------|--------|
| Energy | NIS2 Annex I — Essential | 🔄 In progress |
| Transport | NIS2 Annex I — Essential | 🔄 In progress |
| Health | NIS2 Annex I — Essential | 🔄 In progress |
| Drinking water | NIS2 Annex I — Essential | ⏳ Planned |
| Wastewater | NIS2 Annex I — Essential | ⏳ Planned |
| Digital infrastructure | NIS2 Annex I — Essential | 🔄 In progress |
| ICT service management | NIS2 Annex I — Essential | 🔄 In progress |
| Public administration | NIS2 Annex I — Essential | 🔄 In progress |
| Space | NIS2 Annex I — Essential | ⏳ Planned |
| Banking | NIS2 Annex I — Essential | ⏳ Planned |
| Financial market infrastructures | NIS2 Annex I — Essential | ⏳ Planned |
| Food | NIS2 Annex II — Important | 🔄 In progress |
| Chemicals | NIS2 Annex II — Important | 🔄 In progress |
| Manufacturing | NIS2 Annex II — Important | 🔄 In progress |
| Postal & courier services | NIS2 Annex II — Important | ⏳ Planned |
| Cloud / MSP / MSSP | NIS2 Annex II — Important | 🔄 In progress |
| High-impact AI systems | CRA / AI Act | 🔄 In progress |
| Connected products — CRA Class I | CRA | ⏳ Planned |
| Connected products — CRA Class II | CRA | 🔄 In progress |

---

## Finding format

Each finding follows a standardised YAML template. See [`templates/vulnerability-template.yaml`](templates/vulnerability-template.yaml) for the full schema.

**Quick example:**

```yaml
id: PIIRATES-2025-001
sector: energy
environment: OT/ICS
asset_type: SCADA remote access gateway
cvss_score: 9.1
severity: critical
mitre_technique: T0822 — External Remote Services
description: >
  Unauthenticated access to an industrial remote desktop interface exposed on a
  public IP address. Default credentials had not been changed on the gateway firmware.
impact: >
  Full control of the SCADA HMI. Potential disruption of the monitored
  industrial process with no prior authentication required.
remediation: >
  Enforce VPN with MFA for all OT remote access. Rotate all default credentials.
  Implement strict IT/OT network segmentation.
regulatory_relevance:
  - NIS2 — Article 21 (network security measures)
  - CER — resilience of critical infrastructure
cve_candidate: true
disclosure_status: vendor_notified
```

---

## How to use this repository

**For operators and security teams:**  
Browse findings by sector to identify patterns relevant to your environment. Each remediation is actionable and regulation-mapped.

**For researchers and regulators:**  
Aggregate findings to identify cross-sector vulnerability trends. All data is anonymised and freely reusable under CC BY 4.0.

**For contributors:**  
See [`CONTRIBUTING.md`](CONTRIBUTING.md) for submission guidelines.

---

## Contributing

PIIRATES contributors follow a strict anonymisation protocol before publishing any finding. External contributions from other pentesters are welcome — see [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## License

All findings in this repository are published under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).  
You are free to share and adapt the material for any purpose, including commercial use, as long as you give appropriate credit.

---

## About PIIRATES

PIIRATES is a French offensive cybersecurity company specialising in penetration testing and vulnerability assessment. Over 5 years, we have conducted 220+ penetration tests for 160 clients across regulated sectors including energy, OT/ICS, cloud, AI and public administration.

- Website: [piirates.fr](https://www.piirates.fr)
- Active participant: FIC, SIDO, Minalogic, Digital League

---

*This repository is part of PIIRATES' commitment to open, vendor-independent cybersecurity research.*
