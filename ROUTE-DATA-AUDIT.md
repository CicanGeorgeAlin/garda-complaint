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
