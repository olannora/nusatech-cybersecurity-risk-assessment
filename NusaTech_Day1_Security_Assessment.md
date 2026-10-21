# NusaTech — Initial Cybersecurity Risk Assessment

**Project type:** Educational simulation / fictional organization  
**Version:** 1.0 — Day 1  
**Method:** Illustrative qualitative scoring (Likelihood 1–5 × Impact 1–5). This is not an official NIST or ISO scoring method.

## Scenario and scope
NusaTech is a fictional technology company with 50 employees, a customer-facing web application, and records relating to 10,000 customers. This preliminary exercise identifies selected assets and three illustrative risk scenarios. It is not an actual audit, penetration test, or certification assessment.

## Asset inventory (initial)
| Asset ID | Asset | Business purpose | Provisional owner (role) | CIA priority (illustrative) |
|---|---|---|---|---|
| A-01 | Customer Database | Store customer records | Data / IT Manager | Confidentiality, Integrity, Availability |
| A-02 | Web Application | Provide customer services | Application Owner | Availability, Integrity, Confidentiality |
| A-03 | Administrator Accounts | Manage systems and configurations | IT Operations Lead | Confidentiality, Integrity |
| A-04 | Employee Laptops | Employee workstations | IT Operations Lead | Confidentiality, Integrity |
| A-05 | Backup Storage | Store recovery copies | IT Operations Lead | Availability, Integrity |

*Asset owners are proposed roles for the simulation and have not been verified. Inventory is intentionally limited and should be expanded.*

## Risk scoring assumptions
Likelihood and impact are each scored from 1 (very low) to 5 (very high). Risk score = likelihood × impact. Illustrative levels: 1–4 Low, 5–9 Medium, 10–16 High, 17–25 Critical. Scores are preliminary judgments based on the fictional scenario, not measured probabilities.

## Initial risk register
| Risk ID | Asset(s) | Threat/event | Vulnerability | Risk scenario and business impact | L | I | Score | Level | Proposed controls |
|---|---|---|---|---|---:|---:|---:|---|---|
| R-001 | A-03, A-01 | Attempted administrator account takeover | Weak admin password; no MFA | Unauthorized takeover could enable access to or misuse of customer information, causing confidentiality/integrity and reputational harm | 4 | 5 | 20 | Critical | Phishing-resistant MFA where feasible; strong authentication policy; login monitoring; least privilege |
| R-002 | A-01 | Insider misuse or human error | Excessive privileges; no access review for one year | Employees without a business need could export or misuse customer records, causing privacy, legal and reputational harm | 4 | 4 | 16 | High | Least privilege; role-appropriate access; periodic access reviews; export monitoring |
| R-003 | A-01, A-05, A-02 | Database server failure | Last backup three months ago; restore untested | Failure could cause loss of recent changes and prolonged service outage, harming operations and customer trust | 3 | 5 | 15 | High | Scheduled backups; protected separate copies; regular restore tests; defined RPO/RTO; documented recovery procedure |

## Justifications and evidence limitations
- **R-001:** Repeated unsuccessful administrator login attempts are present in the fictional scenario; weak authentication increases exposure. Impact assumes administrator access to sensitive customer data. No confirmed breach is claimed.
- **R-002:** Broad employee access and absent reviews increase opportunities for accidental or intentional misuse. The scenario confirms export access, but does not confirm that all staff can modify records.
- **R-003:** An old backup and untested restore increase the consequences of server failure; they do not independently establish the probability of hardware failure. Scoring is provisional pending infrastructure and recovery evidence.

## Recommended next steps
1. Verify actual asset owners, access permissions, business processes and current controls.
2. Prioritize administrator authentication and review broad database privileges; assess recovery readiness urgently in parallel.
3. Define risk owners, risk appetite, control implementation status and treatment deadlines.
4. Use NIST CSF 2.0 to perform a current-versus-target gap assessment.
5. Extend the register and prepare ISO/IEC 27001:2022 risk treatment and a draft Statement of Applicability.
6. Use simulated logs for a Google SecOps investigation exercise; do not present simulated activity as production detections.

## Portfolio disclosure
This project is a learning simulation. Findings, data volumes, system conditions, and risk scores are fictional. The deliverable demonstrates initial asset identification, risk reasoning, and proposed security controls, not an independently verified security assessment.
