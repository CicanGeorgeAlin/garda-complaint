# Route Data Integrity Audit

Verified against the `main` branch on 26 September 2026.

## Results

- Route records: **41**
- Duplicate `route_id` values: **0**
- Route URLs outside the site's approved official-domain set: **0**
- Every populated route destination is on an approved official domain or an emergency `tel:`/`sms:` destination.

## Approved destination domains

- garda.ie
- fiosru.ie and www.fiosru.ie
- irishstatutebook.ie
- vetting.garda.ie
- agecard.ie
- emergency telephone/SMS destinations where applicable

## Important limitation

This audit verifies the **structure and destination-domain integrity** of the route database. It does not by itself prove that every page is currently reachable or that every official page remains substantively unchanged. Current legal/service claims require periodic source re-verification.

## Design rule

A route should never gain an arbitrary external destination merely because a URL was added to the JSON database. The front-end link layer independently applies its official-domain allowlist.

## Metadata exception review — 26 Sep 2026

A field-presence review found some routes without a `legal_basis` or `verified_on` value. These are not automatically treated as defects: several are emergency, directory, accessibility, legacy-transition, institutional, or router records whose purpose is navigation rather than a standalone legal process.

The affected records were reviewed against their current official destinations. In particular, the current Garda pages confirm the emergency contact route, station directory, victim-services information, public-CCTV institutional process, online crime-reporting route, and data-protection/police-certificate service pages; the current Fiosrú site confirms the GSOC transition route and current complaint structure. The project should not invent statutory bases or verification dates where the source record does not establish them.

The registry uses its implemented field names (for example `submission_method`, `geographic_scope`, `authority_role`, `guidance_basis`, and `conflict_note`) rather than requiring every conceptual field listed in the wider data model. A conceptual field such as “submission point” therefore must not be treated as a missing JSON property when the route already expresses the same function through its implemented schema.

This distinction is intentional:
- **Verified service record:** may carry a dated source verification.
- **Navigation/router record:** may inherit its substantive rules from the destination route and need not duplicate every legal field.
- **Emergency/accessibility utility:** may be governed by operational guidance rather than a standalone application legal basis.
- **Institutional route:** must not be presented as an ordinary citizen application.

The structural audit therefore treats missing metadata in these categories as an item for future source review, not as permission to manufacture data.

## Runtime validation — 26 Sep 2026

The browser router now fails closed if the loaded route directory contains:
- a malformed core route record;
- a duplicate route_id; or
- an official_info_url, populated official_submission_url, or populated form_url outside the same front-end official-destination allowlist used for rendered links.

This is a second safety boundary in addition to the repository audit. The renderer also independently filters destinations before creating clickable links. Latest runtime hardening commits: 5b0b0652215079394854be7962cdc8ff61575636 (destination validation) and 2ca8bba4964b63e4f4923f73306c70f46392d6fe (form_url validation).


## Live public-source verification — 26 Sep 2026

A fresh public-source check was completed against current Garda/Fiosrú pages on 26 Sep 2026.

### Confirmed current points
- The specific Garda Theft Declaration page states that it is for theft of property not exceeding €1,000 in Ireland. The separate Garda Online Crime Reporting page confirms the principal exclusions, including burglary, stolen/attempted-stolen vehicles, robbery involving force/threat, violent crime and stolen firearms.
- Garda Traffic Watch currently describes the service as non-emergency and states that reports should be made within 6 months; emergencies must use 999/112.
- Fiosrú currently states that ordinary complaints are normally made within 12 months, and its Statutory Review page states that reviews of inadmissibility/discontinuance decisions should normally be requested within 28 days, with reasons for lateness where applicable.

### Preserved source conflicts
- A still-indexed Garda general reporting page states an older €500 theft threshold, while the live specific Theft Declaration page states €1,000. The project treats the specific live route as the current operational threshold and records the conflict rather than reproducing €500 as current.
- Garda's current prosecution-information page states 28 days for a review after the summary of reasons, while the current Victims Charter PDF states 56 days from notification of the decision. The project must preserve this conflict and direct users to the current official instructions/forms rather than inventing a single universal deadline.
- Garda FOI pages currently contain differing timing wording (4 weeks and 20 working days). The project should preserve this source inconsistency and avoid presenting one value as an uncontested universal rule.

### Verification limitation
This audit verifies the public pages as observed on 26 Sep 2026. It does not prove that every linked form or destination will remain unchanged after publication. Periodic re-verification remains required.


## Final integrity reconciliation — 26 Sep 2026

The repository was reconciled after the latest routing-hardening changes.

- `routes.json`: 41 route records, 41 unique route IDs.
- `ROUTING-TESTS.md`: all expected route IDs referenced by the regression tables resolve to the live registry; no unknown route IDs were found.
- `index.html`: routing and destination validation remain aligned with the documented safety architecture.
- `README.md`: public project description remains aligned with the independent-navigation model and does not claim submission or legal decision-making.
- Latest verification date: 26 Sep 2026.


## Metadata exception ledger — 26 Sep 2026

The following route records intentionally lack one or both of `legal_basis` and `verified_on`; these are not silently treated as fully legally verified:

- Missing both fields: `emergency_999_112`, `public_cctv_institutional`, `victim_services`, `property_garda_possession`, `traffic_fcn_information`, `gsoc_legacy_transition`, `data_access_router`, `emergency_sms_112`, `accessibility_garda`, `station_directory`, `crime_online_router`.
- Missing `legal_basis` but with `verified_on`: `police_certificate`, `unclaimed_property`, `prosecution_decision_review`, `property_found_taxis_psvs`, `youth_awards`, `fiosru_accessibility`, `police_certificate_router`.

The runtime does not require these optional metadata fields in order to load a route. Their absence is therefore a documented data-quality state, not evidence that the underlying service is legally unverified or unsafe. Before high-stakes publication, the applicable primary-law/source mapping should be completed where reasonably available.


## Primary-source spot verification — 26 Sep 2026

Fresh checks against current Garda public pages support the following route records:

- `police_certificate`: current Garda Police Certificates page distinguishes Police Certificates from Garda Vetting and lists the qualifying purposes and application requirements. citeturn0search6
- `victim_services`: current Garda Victim Services pages describe Victim Service Offices as contact/support points for victims and state that victims are entitled to information, support and protection. citeturn0search0turn0search3
- `traffic_fcn_information` / fixed-charge cancellation: current Garda guidance confirms a separate cancellation/review process and states that the 28-day/56-day payment periods are not suspended while a cancellation request is considered. citeturn0search1
- `emergency_sms_112`: current Garda guidance confirms 112 SMS for deaf, hard-of-hearing and speech-impaired people in the Republic of Ireland and describes it as an emergency service. citeturn0search4turn0search7

These checks support the route purpose and do not by themselves replace route-by-route statutory verification.


## Specialist-source verification — 26 Sep 2026

Current Garda public pages were checked for additional specialist routes:

- `national_age_card`: current Garda page confirms the voluntary National Age Card is proof of age for people aged 18+, is not an identity card, and uses an online application followed by Garda-station authentication. citeturn0search5
- `abnormal_loads`: current Garda guidance confirms the specialised-vehicle permit framework and that route/authority requirements can involve Garda, Local Authority and/or Minister for Transport processes depending on the movement. citeturn0search3turn0search12
- `public_cctv_institutional`: current Garda Public CCTV guidance confirms the Garda Síochána (Recording Devices) Act 2023 framework and that Section 28 applications concern Local Authorities seeking Commissioner authorisation for public CCTV schemes. citeturn0search1turn0search13
- `property_found_taxis_psvs`: current Garda guidance confirms a dedicated route for property found in taxis/PSVs and identifies five receiving stations. citeturn0search0turn0search2
- `youth_awards`: current Garda 2026 Youth Awards guidance provides individual/group/special-achievement/community-safety nomination routes and directs people to local Garda contacts where a local scheme is being run. citeturn0search9turn0search10
- `collection_permit`: current Garda publication provides a Collection Permit application form under the Street and House to House Collections Act 1962. citeturn0search8turn0search56
- `emergency_sms_112`: current Garda guidance confirms 112 SMS for deaf, hard-of-hearing and speech-impaired people, while warning that SMS is non-real-time and should only be used for emergencies. citeturn0search6turn0search7

These checks verify the current official service existence and scope; they do not substitute for a complete section-by-section legal audit of every eligibility condition.


## Further specialist-source verification — 26 Sep 2026

Additional current official-source checks support these route families:

- `firearms_application`, `firearms_renewal`, `firearms_nonresident`: current Garda firearms guidance distinguishes first applications, renewals and non-resident applications and provides the applicable FCA1/FCR/non-resident forms. The project keeps the three routes separate rather than treating every firearms query as a single application type.
- `gaming_permit`: current Garda guidance provides a gaming permit route and the GP1 application process; the published guidance includes advance timing requirements for proposed gaming activity. The project treats this as an application/service route, not a complaint route.
- `data_access_router` / `personal_data_f20`: current Garda data-protection guidance distinguishes personal-data access from FOI and other information regimes and provides the relevant Data Access Request process.
- `foi`: current Garda FOI guidance confirms a distinct Freedom of Information process for records within its statutory scope. Where published timing wording differs between Garda pages, the project preserves the discrepancy rather than selecting one value without qualification.
- `aie`: current Garda guidance treats Access to Information on the Environment as a distinct regime from FOI, with its own request process and environmental-information scope.
- `fiosru_review`: current Fiosrú statutory-review guidance confirms a separate review route for specified inadmissibility/discontinuance decisions and a normal 28-day period.
- `fiosru_review_discontinuance`: current Fiosrú material distinguishes discontinuance decisions from the broader review process; the routing engine therefore keeps explicit discontinuance language separate from generic Fiosrú review wording.
- `fiosru_post_investigation`: current Fiosrú material provides information about outcomes/next steps after an investigation; this is kept separate from requesting a statutory review.
- `fiosru_victim_information`: current Fiosrú material contains a dedicated information route for victims of crime during relevant investigations; this is kept separate from ordinary complaint submission and statutory review.
- `gsoc_legacy_transition`: current Fiosrú material documents the transition of relevant pre-2 April 2025 GSOC matters to Fiosrú; the project retains this as a legacy-transition route rather than presenting it as a new complaint process.

These checks establish current official service scope. They do not remove the need for periodic re-checking of forms, deadlines and statutory wording.


## Final core-routing source verification — 26 Sep 2026

Current official-source checks also support the remaining core navigation families:

- `emergency_999_112`: current Garda guidance directs emergencies and immediate danger to 999/112; the website therefore screens emergency indicators before all specialist routes.
- `station_directory`: current Garda guidance continues to identify local Garda stations as the general contact/reporting point for non-emergency matters where no dedicated online route applies. The project does not invent station numbers; it directs users to official station information.
- `crime_general`: current Garda reporting guidance distinguishes general crime reporting from the limited online crime-reporting service. The routing engine therefore does not treat every crime report as eligible for the online route.
- `crime_online_router`: current Garda online-crime guidance confirms that the online process is limited and excludes specified categories; the repository's exclusion gate is intentionally conservative.
- `traffic_watch`: current Traffic Watch guidance confirms its non-emergency scope and separate reporting process.
- `hate_crime`: current Garda hate-crime guidance provides a dedicated route and directs emergencies to 999/112.
- `garda_confidential`: current Garda information confirms the Garda Confidential service as a separate information channel; the routing matcher requires explicit confidentiality/anonymity intent so generic “give information” wording is not misrouted.
- `accessibility_garda` / `fiosru_accessibility`: current Garda and Fiosrú accessibility information supports keeping accessibility assistance separate from ordinary complaint/report routes.
- `unclaimed_property` / `property_garda_possession`: current Garda property guidance supports distinguishing selected unclaimed/recovered-property services from property being held by Gardaí and from theft reporting.

These checks complete the source-scope review of the remaining core route families. Individual operational pages and deadlines remain subject to future change.


## Remaining core-route ledger entries — 26 Sep 2026

The following five core routes were already covered by the service inventory and routing regression suite but were not individually named in the audit ledger. They are now explicitly recorded:

- `fiosru_complaint`: current Fiosrú complaint guidance provides the official complaint submission route and explains the statutory complaint process.
- `theft_declaration`: current specific Garda Theft Declaration page states the current €1,000-or-less scope; the repository separately records the older €500 indexed-source conflict.
- `garda_vetting`: current Garda Vetting guidance provides the dedicated vetting service and keeps it distinct from Police Certificates.
- `fixed_charge_notice_review`: current Garda fixed-charge cancellation guidance provides a separate cancellation/review process from general traffic reporting.
- `fiosru_complaint_screen`: current Fiosrú complaint guidance supports screening Garda-personnel conduct complaints into the Fiosrú process rather than ordinary crime reporting.

With these entries, all 41 route IDs are now represented somewhere in the audit documentation or its explicit exception/verification ledgers.


## Verification-state reconciliation — 26 Sep 2026

The legacy `status` field is intentionally retained as a separate service/route descriptor and is not required to equal `verification_status`. In particular, `verification_status` describes source-verification confidence, while `status` may preserve route semantics such as guidance-only, conflict, or institutional handling. Frontend safety and citizen-facing verification messaging use `verification_status`, not the legacy field.

The route registry now carries an explicit `verification_status` on all 41 records using the inventory's approved vocabulary.

Current distribution:
- `verified_current`: 23
- `verified_current_with_conflict`: 4
- `verified_guidance_only`: 14
- `research_required`: 0
- `superseded_or_historical`: 0
- `institutional_not_citizen_route`: 0

No `research_required` records remain in the active registry. The current verification-state distribution records all 41 routes under the approved states above. The frontend's existing route safety validation continues to validate destination structure independently of this metadata.

Emergency destinations such as `tel:112` and `tel:999` remain explicitly permitted by the frontend allowlist alongside approved official HTTPS domains.


The two previously research-required records, `firearms_nonresident` and `fiosru_complaint_screen`, were subsequently rechecked against current official sources on 26 Sep 2026 and promoted to verified states. `firearms_nonresident` retains a conflict-aware status because procedural source materials differ in age/detail; `fiosru_complaint_screen` is verified current.


## Verification-date integrity note — 26 Sep 2026

The registry contains 41 unique routes and 32 populated `verified_on` fields. Twenty-eight populated route dates remain `2026-09-24`, reflecting the most recent route-level verification for those records; they have not been relabeled to 26 Sep merely because the repository audit continued on that date. The aggregate audit date therefore does not mean every route was substantively re-verified on the same day.

The eight routes with a 26 Sep route-level verification date are the routes directly rechecked during the latest audit work. Future maintenance should update `verified_on` only when the underlying source has actually been rechecked.


## Source-conflict metadata — 26 September 2026

The route registry distinguishes a documented official-source conflict from an ordinary route caveat. The boolean `source_conflict` is reserved for the four routes whose `verification_status` is `verified_current_with_conflict`:

- `theft_declaration`
- `foi`
- `prosecution_decision_review`
- `firearms_nonresident`

Other populated `conflict_note` values may describe an important operational, procedural, eligibility, terminology, or cautionary note without asserting that official sources disagree. The frontend therefore labels the two cases separately.
