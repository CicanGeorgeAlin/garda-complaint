# Garda Citizen Access — Routing Test Matrix

Purpose: regression tests for the citizen-facing route engine in `index.html`.

These are expected outcomes, not legal determinations. Emergency screening must always run first.

| Test input | Expected route |
|---|---|
| "Someone is in immediate danger right now" | emergency_999_112 |
| "A crime is happening now but nobody is in immediate danger" | no automatic crime route |
| "My car was stolen yesterday" | station_directory |
| "Someone used force to rob me" | station_directory |
| "My firearm was stolen" | station_directory |
| "There was a burglary but nobody is in danger now" | station_directory |
| "I am reporting something that happened yesterday" | no automatic crime route |
| "There is a crime in progress" | emergency_999_112 |
| "I want to complain about a Garda member" | fiosru_complaint_screen |
| "Fiosrú said my complaint is inadmissible and I want a review" | fiosru_review |
| "Fiosrú discontinued the investigation and I want a review" | fiosru_review_discontinuance |
| "My car was stolen" | station_directory |
| "There was a burglary last night" | station_directory |
| "My property was stolen and it was worth €500" | theft_declaration |
| "My property was stolen and it was worth €1,500" | station_directory |
| "My property was stolen and it was worth €1,000" | theft_declaration |
| "My property was stolen and it was worth €1,001" | station_directory |
| "My property was stolen and it was worth €1,500.00" | station_directory |
| "My property was stolen" | crime_general |
| "Someone stole something from me" | crime_general |
| "I found a stolen item" | crime_general |
| "I want to report a non-emergency dangerous driving incident" | traffic_watch |
| "There is an immediate danger from a driver" | emergency_999_112 |
| "I want to report a hate crime" | hate_crime |
| "A hate incident is happening now and there is immediate danger" | emergency_999_112 |
| "I want to give information confidentially" | garda_confidential |
| "I want to see personal data Gardaí hold about me" | data_access_router |
| "I want Garda records under FOI" | foi |
| "I want records about an incident" | no automatic crime route |
| "I want my personal records about me" | data_access_router |
| "I want environmental records about pollution" | aie |
| "I want to make an FOI request" | foi |
| "I want environmental information held by Gardaí" | aie |
| "I need Garda vetting for work" | garda_vetting |
| "I need a police certificate for another country" | police_certificate_router |
| "I need Garda vetting for employment" | garda_vetting |
| "I need eVetting for volunteering" | garda_vetting |
| "I need a criminal record check" | no automatic crime route |
| "I need a certificate" | no automatic crime route |
| "I want a firearm certificate" | firearms_application |
| "I want to renew my firearm certificate" | firearms_renewal |
| "I am a non-resident applying for a firearm certificate" | firearms_nonresident |
| "I need to renew my firearms licence" | firearms_renewal |
| "I need to contact my local Garda station" | station_directory |
| "I received a Fixed Charge Notice and want to challenge it" | fixed_charge_notice_review |
| "I am a crime victim and need support" | victim_services |
| "I want to organise a public collection" | collection_permit |
| "I need a permit for gaming" | gaming_permit |
| "I need information about an abnormal load" | abnormal_loads |
| "I want public CCTV in my area" | public_cctv_institutional |
| "I found property at a Garda station" | unclaimed_property |
| "I need information about a camera" | no automatic crime route |
| "My property was stolen" | crime_general |
| "I need a National Age Card" | national_age_card |
| "I want to check recovered property" | unclaimed_property |
| "I don't know what Garda service I need" | no automatic crime route |
| "I want to report a crime" | crime_general |
| "I need a permit for gaming" | gaming_permit |
| "I want environmental records about pollution" | aie |
| "I want my personal records about me" | data_access_router |
| "Fiosrú said my complaint is inadmissible" | fiosru_review |
| "I want to complain to Fiosrú about a Garda" | fiosru_complaint_screen |
| "I want to review my Fiosrú complaint" | fiosru_review |
| "I want to appeal a Fiosrú decision" | fiosru_review |
| "I want information about my Fiosrú complaint" | no automatic crime route |
| "Fiosrú discontinued my complaint" | fiosru_review_discontinuance |
| "I want to report a non-emergency incident" | crime_general |
| "I need information about Fiosrú" | no automatic crime route |
| "I have a driving licence question" | no automatic crime route |
| "I want to report dangerous driving" | traffic_watch |
| "I am a victim of Garda conduct" | fiosru_complaint_screen |
| "I was a victim of a crime and need support" | victim_services |
| "I need information about penalty points" | fixed_charge_notice_review |
| "I need information about a certificate" | no automatic crime route |

## Safety invariants

1. Emergency indicators must be evaluated before every specialist route.
2. Excluded online-crime categories must not be sent to the online crime declaration.
3. A theft declaration must not be selected solely because the word "stolen" appears; the qualifying value and exclusions matter.
4. Unknown questions must not default to crime reporting.
5. Fiosrú review language must be checked before the general Garda-complaint route.
6. The website only identifies an official route; it does not itself submit a complaint, crime report, application, or request.

## Registry-vs-engine coverage note — 26 Sep 2026

The route registry contains 41 records, but not every record is intended to be a top-level natural-language matcher. Some are downstream routes, information-only records, accessibility/utility routes, or specialist records reached after a broader screening question.

The following records are currently not selected directly by a literal `route_id` branch in `index.html` and should therefore be reviewed during future routing work rather than assumed to have direct matcher coverage:

- `personal_data_f20` — downstream personal-data access route; `data_access_router` is the screening entry.
- `prosecution_decision_review` — specialist victim-review destination.
- `property_found_taxis_psvs` — specialist property process.
- `youth_awards` — specialist nomination service.
- `property_garda_possession` — property-information service.
- `traffic_fcn_information` — information-only FCN record; the broader FCN route currently screens this topic.
- `gsoc_legacy_transition` — legacy-case information.
- `emergency_sms_112` — accessibility emergency route.
- `accessibility_garda` — accessibility support.
- `fiosru_accessibility` — Fiosrú accessibility support.
- `fiosru_victim_information` — information for people involved in a Fiosrú investigation.
- `fiosru_post_investigation` — post-investigation information.
- `crime_online_router` — screening/router record for online crime reporting.

This is a coverage flag, not a claim that these services are unavailable. Before treating the website as complete, each specialist record should either have a deliberate entry path in the interface or be clearly documented as a downstream/manual route.

### Direct specialist coverage added — 26 Sep 2026

The route engine now has deliberate entry patterns for previously uncovered citizen-facing specialist records:

- Garda Youth Awards → `youth_awards`
- found property in a taxi/PSV → `property_found_taxis_psvs`
- property held by Gardaí → `property_garda_possession`
- prosecution-decision questions → `prosecution_decision_review`
- pre-Fiosrú GSOC complaint → `gsoc_legacy_transition`
- Fiosrú post-investigation questions → `fiosru_post_investigation`
- information about an active Fiosrú investigation → `fiosru_victim_information`
- Fiosrú accessibility → `fiosru_accessibility`
- Garda accessibility → `accessibility_garda`
- uncertainty about online crime reporting → `crime_online_router`

Emergency detection remains ahead of these specialist branches, and the existing theft-value and excluded-crime gates remain ahead of broad crime/property matching.

### Regression cases for expanded specialist routing — 26 Sep 2026

| Input | Expected route |
|---|---|
| “I want to nominate someone for a Garda Youth Award” | `youth_awards` |
| “I found property in a taxi” | `property_found_taxis_psvs` |
| “Gardaí are holding my property” | `property_garda_possession` |
| “I want to challenge a decision not to prosecute” | `prosecution_decision_review` |
| “I made a GSOC complaint before Fiosrú started” | `gsoc_legacy_transition` |
| “Fiosrú finished investigating my complaint; what happens next?” | `fiosru_post_investigation` |
| “I need information about my Fiosrú investigation” | `fiosru_victim_information` |
| “I need accessible help from Fiosrú” | `fiosru_accessibility` |
| “I need Garda services in an accessible format” | `accessibility_garda` |
| “I want to report a crime online but don't know if the form applies” | `crime_online_router` |

### Currency parser regression

The theft-value parser must continue to interpret:

- €1,000 → `theft_declaration`
- €1,001 → `station_directory`
- €1,500.00 → `station_directory`
- €1.500,00 → `station_directory`

The parser must not treat a thousands separator as a decimal point.

### Runtime destination-safety regression — 26 Sep 2026

The route loader must fail closed if a route contains an unsafe `official_info_url` or populated `official_submission_url`. The rendered-link layer must also reject such destinations independently. This prevents a malformed or tampered route record from becoming a clickable external destination.

### Prosecution-review false-positive regression — 26 Sep 2026

The prosecution-decision specialist route is intentionally limited to explicit challenge/review/appeal language. A question merely asking for general information about prosecution decisions must not be treated as a request to challenge a decision.

| Input | Expected route |
|---|---|
| “I want information about prosecution decisions” | no automatic crime route |
| “What is a prosecution decision?” | no automatic crime route |
| “I want to challenge a decision not to prosecute” | `prosecution_decision_review` |
| “Can I appeal a decision not to prosecute?” | `prosecution_decision_review` |
