# Garda Citizen Access — Legal Source Map

## Purpose

This file is the working legal specification for the project. The public website should stay simple; the legal complexity lives here.

## Core statutory framework

**Policing, Security and Community Safety Act 2024 — Part 6: Complaints, Investigations and Other Matters**

Primary source:
https://www.irishstatutebook.ie/eli/2024/act/1/enacted/en/html

Key provisions to map in the complaint engine:

- s.193 — Interpretation (Part 6)
- s.194 — Application of Part
- s.195 — Complaints by members of public
- s.196 — Making and recording complaints
- s.197 — Time limits for making complaints
- s.198 — Determination of admissibility
- s.199 — Admissible complaints
- ss.200–202 — Complaints suitable for resolution by An Garda Síochána
- s.203 — Death or serious harm
- s.204 — Incident of concern
- s.205 — Public-interest investigations
- s.206 — Protected disclosures relating to An Garda Síochána
- s.207 — Matters relating to Garda Commissioner
- s.208 onwards — Investigations and related procedures
- s.219 — Preservation of evidence
- s.224 — Review
- s.226 — False or misleading information

## Current Fiosrú complaint route

Official complaint form:
https://www.fiosru.ie/complaints/submit-a-complaint/

Current Fiosrú guidance confirms:
- A member of the public can complain if directly affected by, or a witness to, the Garda behaviour.
- A complaint may be made on another person's behalf in defined circumstances.
- A complaint can be made online, by post, or at any Garda station.
- The normal time limit is 12 months, with possible acceptance after that where there is a good reason.
- Anonymous complaints are not accepted.
- The Garda member's name is not required.
- Fiosrú provides an accessibility route through its Access Officer.

## Current Garda routes identified for the first build

Emergency:
- 999 / 112

Online crime declaration:
https://www.garda.ie/en/about-us/online-services/online-crime-reporting/

Traffic Watch:
https://www.garda.ie/en/trafficwatchreport/

Hate crime reporting:
https://www.garda.ie/en/reportahatecrime/

Garda online services directory:
https://www.garda.ie/en/about-us/online-services/

Data Protection / F20 / FOI / Police Certificates:
https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/

## Design rule

The website must distinguish:
1. Emergency
2. Crime report
3. Garda-conduct complaint
4. Application/request/service
5. Information/confidential report
6. Data-protection/FOI request
7. Specialist reporting route

The site must never imply that a website link on this project itself constitutes submission to An Garda Síochána or Fiosrú.

## Verification rule

Every substantive legal statement must be traceable to:
1. Irish Statute Book / legislation
2. Statutory instrument or regulation where relevant
3. Fiosrú official guidance
4. An Garda Síochána official guidance/forms
5. Other Irish public authority sources where relevant

Each item in the eventual master catalogue should record:
- action
- legal basis
- eligible person
- geographical scope
- emergency status
- online route
- email
- postal route
- telephone
- in-person route
- official form
- evidence/information required
- deadline
- anonymity/confidentiality
- responsible authority
- next steps
- review/appeal
- source URL
- date last verified

## Scope

First operational location: Dublin.

The legal framework is national. County/city pages should add local operational information without duplicating the national law database.


## Registry reconciliation

The structured route registry is maintained separately in `routes.json`. This legal map is not intended to repeat all 41 route IDs; it records the statutory and primary-source framework that the route registry and service inventory use.

Current registry state checked 26 September 2026:
- 41 route records
- 41 unique route IDs
- verification states are assigned in `routes.json`
- route-level source detail and verification notes are maintained in `OFFICIAL-SERVICE-INVENTORY.md`
- structural/destination verification is maintained in `ROUTE-DATA-AUDIT.md`
- routing behavior and regression expectations are maintained in `ROUTING-TESTS.md`

A route should not be treated as legally verified merely because its topic appears in this source map. Route-level verification status, source date, documented conflicts and guidance-only limitations remain authoritative for activation and presentation.
