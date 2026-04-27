# Contributing to the PIIRATES Vulnerability Repository

Thank you for considering a contribution. This document explains how to submit a finding and what our anonymisation requirements are.

---

## Who can contribute

- PIIRATES internal pentesters and freelance specialists
- External researchers who have identified a vulnerability in a real engagement and have client authorisation to share anonymised findings

---

## Anonymisation protocol — mandatory before submission

Every finding must pass through our anonymisation checklist before being submitted. **No finding may be published if it could allow identification of the assessed organisation.**

### What must be removed or generalised

| Original data | Replace with |
|---------------|-------------|
| Client name, brand, trade name | Remove entirely |
| System brand / product name | Generic description (e.g. "industrial gateway", "ERP platform") |
| Software version numbers | Remove — mention only if critical to the finding |
| IP addresses, hostnames, URLs | Remove entirely |
| Usernames, account names | Remove entirely |
| Geographic location (city, region) | Remove entirely |
| Sector sub-segment that could identify (e.g. "the only hydrogen operator in Auvergne") | Generalise to top-level sector |
| Dates of the assessment | Remove — use only the publication year |
| Report extracts, screenshots | Never include |

### What must remain

- The vulnerability class and technical mechanism
- The CVSS score and severity
- The MITRE ATT&CK mapping
- The concrete remediation recommendation
- The regulatory mapping

---

## Submission process

1. **Copy** `templates/vulnerability-template.yaml`
2. **Rename** it using the format `PIIRATES-YYYY-NNN.yaml` (ask for the next available number)
3. **Fill in** all mandatory fields
4. **Run the anonymisation checklist** above
5. **Open a Pull Request** to the relevant `sectors/[sector-name]/` directory
6. A senior PIIRATES pentester will review the finding before merge

---

## Review criteria

Before merging, reviewers check:

- [ ] No identifying information present
- [ ] CVSS score is accurate and justified
- [ ] MITRE mapping is correct
- [ ] Remediation is actionable and specific
- [ ] Regulatory mapping is relevant
- [ ] Finding adds value beyond existing entries (no duplicates)

---

## Questions

Open an issue or contact us at contact@piirates.fr
