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
| "I need information about penalty points" | traffic_fcn_information |
| "I need information about a certificate" | no automatic crime route |

## Semantic gap regressions — 26 Sep 2026

The route engine must recognize natural-language ordering differences where the citizen places the object before the requested action:

| Input | Expected route |
|---|---|
| "I received a Fixed Charge Notice and want to challenge it" | fixed_charge_notice_review |
| "I received a fixed charge and want a review" | fixed_charge_notice_review |
| "I want to complain to Fiosrú about a Garda" | fiosru_complaint_screen |
| "I am a victim of Garda conduct" | fiosru_complaint_screen |
| "I want to complain about a Garda" | fiosru_complaint_screen |

These cases protect against overly rigid phrase ordering while retaining the existing conservative ambiguity rules.

## High-consequence semantic regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "Someone used force to rob me" | station_directory |
| "My firearm was stolen" | station_directory |
| "Fiosrú discontinued my complaint and I want a review" | fiosru_review |
| "Fiosrú stopped investigating and I want a review" | fiosru_review |

These cases ensure excluded online-crime categories, stolen firearms, and explicit Fiosrú review requests retain the correct precedence.

## Accessibility/emergency precedence regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I am deaf and need emergency SMS" | emergency_sms_112 |
| "I need emergency SMS" | emergency_sms_112 |
| "I cannot hear and need emergency help" | emergency_999_112 |
| "I am deaf and there is immediate danger" | emergency_999_112 |
| "I cannot speak and someone is in danger" | emergency_999_112 |
| "I am hard of hearing and there is a crime in progress" | emergency_999_112 |
| "I need help because I cannot hear" | emergency_sms_112 |
| "I need an accessible Garda service" | accessibility_garda |
| "I need help accessing Fiosrú" | fiosru_accessibility |

Emergency indicators must continue to outrank accessibility routing when immediate danger is described.

## Online-crime boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I want to report a crime online" | crime_online_router |
| "Can I report a crime online?" | crime_online_router |
| "I want to use the online crime form" | crime_online_router |
| "I want to report a burglary online" | station_directory |
| "Can I report my stolen car online?" | station_directory |
| "I want to report a robbery online" | station_directory |
| "I want to report violent crime online" | station_directory |
| "My firearm was stolen and I want to report it online" | station_directory |
| "There was a burglary but nobody is in danger now" | station_directory |
| "My car was stolen yesterday" | station_directory |
| "I want to report a non-emergency incident" | crime_general |
| "I want to report a crime" | crime_general |
| "I need information about a crime" | no automatic crime route |
| "Something happened yesterday" | no automatic crime route |

These tests protect the distinction between the online-reporting eligibility screen and general crime reporting.

## Data/records boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I want to see personal data Gardaí hold about me" | data_access_router |
| "I want my personal records about me" | data_access_router |
| "I need information about my Garda data" | data_access_router |
| "I want Garda records under FOI" | foi |
| "I want to make an FOI request" | foi |
| "I want environmental information held by Gardaí" | aie |
| "I want environmental records about pollution" | aie |
| "I want records about an incident" | no automatic crime route |
| "I want information about Garda records" | no automatic crime route |
| "I want my neighbour's personal data" | no automatic crime route |

Personal-data access must remain focused on the citizen's own data (or clearly framed authorised access), rather than treating any third-party personal-data request as a self-access route.

## Fiosrú lifecycle regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I want to complain to Fiosrú about a Garda" | fiosru_complaint_screen |
| "Fiosrú discontinued my complaint and I want a review" | fiosru_review |
| "Fiosrú stopped investigating and I want a review" | fiosru_review |
| "Fiosrú discontinued my complaint" | fiosru_review_discontinuance |
| "Fiosrú stopped investigating my complaint" | fiosru_review_discontinuance |
| "Fiosrú finished investigating my complaint" | fiosru_post_investigation |
| "What happens next after Fiosrú finished investigating my complaint?" | fiosru_post_investigation |
| "I want information about my Fiosrú investigation" | fiosru_victim_information |
| "I need information about significant developments in my Fiosrú investigation" | fiosru_victim_information |
| "I need help accessing Fiosrú" | fiosru_accessibility |
| "I need an accessible Fiosrú service" | fiosru_accessibility |
| "I want information about my Fiosrú complaint" | no automatic route |

Explicit review requests must outrank the generic discontinuance route; lifecycle information questions must remain separate from complaint submission and statutory review.

## Police Certificate / Garda Vetting boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I need a police certificate" | police_certificate_router |
| "I need a Garda police certificate" | police_certificate_router |
| "I need a criminal record certificate for another country" | police_certificate_router |
| "I need Garda vetting for work" | garda_vetting |
| "I need vetting for employment" | garda_vetting |
| "I need vetting for volunteering" | garda_vetting |
| "I need e-vetting for a job" | garda_vetting |
| "I need a police certificate for a job" | police_certificate_router |
| "I need a background check for work" | garda_vetting |
| "I need a certificate to work in another country" | no automatic route |
| "I need information about certificates" | no automatic route |

A Police Certificate and Garda Vetting are distinct services. Ambiguous certificate/background-check wording must not be treated as proof of either route without sufficient context.

## Firearms boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I want to apply for a firearm certificate" | firearms_application |
| "I want a gun licence" | firearms_application |
| "I need a firearms licence" | firearms_application |
| "I want to renew my firearm certificate" | firearms_renewal |
| "I need to renew my firearms licence" | firearms_renewal |
| "I am a non-resident applying for a firearm certificate" | firearms_nonresident |
| "I am a non resident applying for a gun licence" | firearms_nonresident |
| "My firearm was stolen" | station_directory |
| "My firearm has been stolen and I need to report it" | station_directory |
| "I need information about firearms" | firearms_application |
| "I want a firearm certificate for the first time" | firearms_application |

Stolen-firearm reporting must remain ahead of the generic firearms application route. Renewal and non-resident language must also remain ahead of generic application matching.

## Fixed Charge / prosecution-decision boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I received a Fixed Charge Notice" | traffic_fcn_information |
| "I got a traffic fine" | traffic_fcn_information |
| "I want information about penalty points" | traffic_fcn_information |
| "I received a Fixed Charge Notice and want to challenge it" | fixed_charge_notice_review |
| "I want to review my fixed charge notice" | fixed_charge_notice_review |
| "I want to cancel a fixed charge notice" | fixed_charge_notice_review |
| "I want to challenge the decision not to prosecute" | prosecution_decision_review |
| "I want to review the decision not to prosecute" | prosecution_decision_review |
| "I want to appeal a prosecution decision" | prosecution_decision_review |
| "I want to review a prosecution decision" | prosecution_decision_review |
| "I want information about a prosecution decision" | no automatic route |

Action language must identify the relevant object before selecting a review route; general information requests must not be promoted into a review.

## Emergency / confidential-information boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I want to give information anonymously about dangerous driving" | garda_confidential |
| "I want to report dangerous driving" | traffic_watch |
| "I want to give information confidentially" | garda_confidential |
| "Can I report anonymously?" | garda_confidential |
| "I want to report a hate incident" | hate_crime |
| "A hate incident is happening now and there is immediate danger" | emergency_999_112 |
| "There is a crime in progress" | emergency_999_112 |
| "Someone is in immediate danger right now" | emergency_999_112 |
| "I am deaf and need emergency SMS" | emergency_sms_112 |
| "I need emergency SMS" | emergency_sms_112 |
| "I need help because I cannot hear" | emergency_sms_112 |
| "I cannot hear and need emergency help" | emergency_999_112 |
| "I cannot speak and someone is in danger" | emergency_999_112 |
| "I need an accessible Garda service" | accessibility_garda |

Emergency indicators must outrank specialist routing. Accessibility need alone must not be treated as an emergency, while explicit immediate danger must remain on the emergency path.

## Property-route boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I found property in a taxi" | property_found_taxis_psvs |
| "I found property in a PSV" | property_found_taxis_psvs |
| "Property was found in a taxi" | property_found_taxis_psvs |
| "A taxi passenger left property" | no automatic route |
| "I found property" | unclaimed_property |
| "I found lost property" | unclaimed_property |
| "I found recovered property" | unclaimed_property |
| "I found a stolen item" | crime_general |
| "Gardaí are holding my property" | property_garda_possession |
| "My property is held by Garda" | property_garda_possession |
| "I want to know about property Gardaí are holding" | property_garda_possession |
| "I lost property in a taxi" | unclaimed_property |
| "I need information about lost property" | unclaimed_property |

Specific taxi/PSV found-property language must outrank generic found-property routing. Lost-property language must not be converted into the specialist taxi/PSV found-property route merely because a taxi is mentioned.

## Specialist application boundary regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I need a National Age Card" | national_age_card |
| "I need proof of age" | national_age_card |
| "I want to nominate someone for a Garda Youth Award" | youth_awards |
| "I want a Garda Youth Award nomination form" | youth_awards |
| "I need a collection permit" | collection_permit |
| "I need a public collection permit" | collection_permit |
| "I need a gaming permit" | gaming_permit |
| "I need a lottery permit" | gaming_permit |
| "I need an abnormal load permit" | abnormal_loads |
| "I have an oversized load" | abnormal_loads |
| "I want to request public CCTV footage" | public_cctv_institutional |
| "I want public CCTV in my area" | public_cctv_institutional |
| "I want to complain about CCTV" | no automatic route |
| "I want to complain about a collection permit" | no automatic route |

Permit/application language must not automatically convert complaint, appeal, challenge, objection or dispute wording into an application route.

## Generic-action ambiguity regressions — 26 Sep 2026

| Input | Expected route |
|---|---|
| "I want to complain" | no automatic route |
| "I want to report something" | no automatic route |
| "I need information" | no automatic route |
| "I want a review" | no automatic route |
| "I want to appeal" | no automatic route |
| "I want to challenge something" | no automatic route |
| "Something happened" | no automatic route |
| "I have a problem with Gardaí" | no automatic route |
| "I need help with Gardaí" | no automatic route |
| "I want to complain about a Garda" | fiosru_complaint_screen |
| "I want to report a crime" | crime_general |
| "I want to report dangerous driving" | traffic_watch |
| "I want to review my fixed charge notice" | fixed_charge_notice_review |
| "I want to review a prosecution decision" | prosecution_decision_review |
| "I want to appeal a prosecution decision" | prosecution_decision_review |
| "I want to review a Fiosrú decision" | fiosru_review |

Generic action words must not select a route without a sufficiently specific object, authority or circumstance.

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

The route engine has deliberate citizen-language entry patterns for the specialist records previously identified as needing review:

- Garda Youth Awards → `youth_awards`
- found property in a taxi/PSV → `property_found_taxis_psvs`
- property held by Gardaí → `property_garda_possession`
- prosecution-decision challenge/review language → `prosecution_decision_review`
- pre-Fiosrú GSOC complaint → `gsoc_legacy_transition`
- Fiosrú post-investigation questions → `fiosru_post_investigation`
- information about an active Fiosrú investigation → `fiosru_victim_information`
- Fiosrú accessibility → `fiosru_accessibility`
- Garda accessibility → `accessibility_garda`
- uncertainty about online crime reporting → `crime_online_router`
- emergency SMS/accessibility emergency language → `emergency_sms_112`

Emergency detection remains ahead of these specialist routes.

### Registry-to-engine reconciliation — 26 Sep 2026

A literal `route_id` search is not a sufficient reachability test because the engine intentionally uses `state.routes.find(...)` inside shared matcher arrays and uses screening/router records for some downstream services.

The current architecture therefore treats these as deliberate downstream records rather than unreachable routes:

- `fiosru_complaint` — entered through `fiosru_complaint_screen`, which provides the statutory complaint submission destination.
- `personal_data_f20` — entered through `data_access_router`, because the correct data-protection sub-route depends on the request.
- `police_certificate` — entered through `police_certificate_router`, because purpose and destination must be distinguished from Garda Vetting.
- `property_found_taxis_psvs`, `property_garda_possession`, `prosecution_decision_review`, `youth_awards`, `gsoc_legacy_transition`, `emergency_sms_112`, `accessibility_garda`, `fiosru_accessibility`, `fiosru_victim_information`, `fiosru_post_investigation`, and `crime_online_router` have deliberate natural-language entry patterns.

The remaining validation requirement is semantic regression testing: a route being reachable is not enough; broad citizen wording must still remain unresolved when the available information is insufficient, and emergency/specialist precedence must continue to hold.
## Route coverage ledger — 26 Sep 2026

Every registered route is assigned an intentional entry role. A route may be a direct natural-language destination or a downstream destination reached through a screening/router record; downstream status is deliberate, not an accidental coverage gap.

| Route ID | Entry role |
|---|---|
| emergency_999_112 | direct emergency gate |
| fiosru_complaint | downstream from fiosru_complaint_screen |
| crime_general | direct general-crime gate |
| theft_declaration | direct theft-value gate |
| traffic_watch | direct traffic gate |
| hate_crime | direct specialist gate |
| garda_confidential | direct confidential-information gate |
| personal_data_f20 | downstream from data_access_router |
| foi | direct information-access gate |
| aie | direct information-access gate |
| police_certificate | downstream from police_certificate_router |
| garda_vetting | direct specialist gate |
| national_age_card | direct specialist gate |
| unclaimed_property | direct property gate |
| fixed_charge_notice_review | direct explicit review/cancellation gate |
| prosecution_decision_review | direct explicit review/appeal gate |
| abnormal_loads | direct specialist gate |
| collection_permit | direct specialist gate |
| gaming_permit | direct specialist gate |
| firearms_application | direct firearms gate |
| firearms_renewal | direct renewal gate |
| property_found_taxis_psvs | direct specialist property gate |
| youth_awards | direct specialist gate |
| public_cctv_institutional | direct institutional-service gate |
| fiosru_review | direct explicit Fiosrú review gate |
| victim_services | direct crime-victim support gate |
| property_garda_possession | direct specialist property gate |
| traffic_fcn_information | direct FCN-information gate |
| gsoc_legacy_transition | direct legacy-case gate |
| data_access_router | direct personal-data screening gate |
| emergency_sms_112 | direct accessibility-emergency gate |
| accessibility_garda | direct accessibility gate |
| fiosru_accessibility | direct accessibility gate |
| firearms_nonresident | direct non-resident firearms gate |
| police_certificate_router | direct certificate-purpose screening gate |
| station_directory | direct station/contact and excluded-crime fallback |
| fiosru_victim_information | direct Fiosrú-investigation information gate |
| fiosru_post_investigation | direct post-investigation gate |
| fiosru_review_discontinuance | direct discontinuance gate |
| crime_online_router | direct online-crime screening gate |
| fiosru_complaint_screen | direct Garda-personnel complaint screening gate |

**Coverage result: 41/41 route IDs have an intentional entry role.**

## Traffic / FCN collision regressions — 26 Sep 2026

Traffic Watch and Fixed Charge Notice routes must remain distinct. General FCN/penalty-point information belongs to the FCN information route; an explicit challenge, cancellation, review or appeal belongs to the FCN review route. Non-emergency dangerous-driving reports belong to Traffic Watch. Emergency indicators remain authoritative before all of these routes.

| Input | Expected route |
|---|---|
| “I want to report dangerous driving” | `traffic_watch` |
| “I want to report a dangerous driver” | `traffic_watch` |
| “I want to report a non-emergency traffic incident” | `traffic_watch` |
| “I received a Fixed Charge Notice” | `traffic_fcn_information` |
| “What penalty points apply?” | `traffic_fcn_information` |
| “I want information about a traffic fine” | `traffic_fcn_information` |
| “I want to challenge my Fixed Charge Notice” | `fixed_charge_notice_review` |
| “I want to appeal my Fixed Charge Notice” | `fixed_charge_notice_review` |
| “Can I cancel this Fixed Charge Notice?” | `fixed_charge_notice_review` |
| “There is immediate danger from a driver” | `emergency_999_112` |
| “A dangerous driver is causing serious injury right now” | `emergency_999_112` |
| “I have a driving licence question” | no automatic crime route |


## Property-route collision regressions — 26 Sep 2026

Explicit specialist property language must be resolved before generic theft-value parsing. This prevents a monetary value in a taxi/PSV property question, or the word “stolen” in a Garda-held-property question, from changing the intended process.

| Input | Expected route |
|---|---|
| “I found property in a taxi” | `property_found_taxis_psvs` |
| “I found property in a PSV worth €500” | `property_found_taxis_psvs` |
| “Taxi found property worth €1,500” | `property_found_taxis_psvs` |
| “Gardaí are holding my property” | `property_garda_possession` |
| “Gardaí are holding my stolen property” | `property_garda_possession` |
| “I found property at a Garda station” | `unclaimed_property` |
| “I found a stolen item” | `crime_general` |
| “My property was stolen and it was worth €500” | `theft_declaration` |
| “My property was stolen and it was worth €1,500” | `station_directory` |
| “I need information about property” | no automatic crime route |


## Certificate / vetting collision regressions — 26 Sep 2026

Certificate-related language must not be treated as interchangeable. The router may identify a police-certificate topic without inventing the person's destination or purpose. Generic “certificate” and generic “criminal record check” questions remain unresolved unless the wording establishes a supported specialist route.

| Input | Expected route |
|---|---|
| “I need a Garda Police Certificate” | `police_certificate_router` |
| “I need a police certificate for another country” | `police_certificate_router` |
| “I need a criminal record certificate for another country” | `police_certificate_router` |
| “I need Garda vetting for work” | `garda_vetting` |
| “I need vetting for employment” | `garda_vetting` |
| “I need eVetting for volunteering” | `garda_vetting` |
| “I need a criminal record check” | no automatic crime route |
| “I need a certificate” | no automatic crime route |
| “I need information about a certificate” | no automatic crime route |
| “I need a certificate for work” | no automatic crime route |


## Accessibility / Emergency SMS collision regressions — 26 Sep 2026

Accessibility support must remain distinct from the emergency SMS 112 route. The general emergency gate remains first, so an accessibility-related description that also establishes immediate danger routes to emergency services rather than ordinary accessibility support.

| Input | Expected route |
|---|---|
| “I cannot speak and need to contact emergency services by SMS” | `emergency_sms_112` |
| “I cannot hear and need information about SMS 112” | `emergency_sms_112` |
| “I am deaf and need emergency SMS information” | `emergency_sms_112` |
| “I need Garda services in an accessible format” | `accessibility_garda` |
| “I need accessible help from Gardaí” | `accessibility_garda` |
| “I need accessible help from Fiosrú” | `fiosru_accessibility` |
| “I need to communicate with Fiosrú accessibly” | `fiosru_accessibility` |
| “I am deaf and someone is in immediate danger” | `emergency_999_112` |
| “I cannot speak and there is immediate danger” | `emergency_999_112` |
| “I need accessibility information” | no automatic crime route |


## Fiosrú review false-positive regressions — 26 Sep 2026

A generic request to review or appeal a complaint must not be routed to Fiosrú unless the wording establishes Fiosrú context or a specific Fiosrú decision such as inadmissibility/discontinuation. This preserves the distinction between a general complaint and the statutory Fiosrú review process.

| Input | Expected route |
|---|---|
| “I want to review my complaint” | fiosru_review must NOT be selected |
| “I want to appeal my complaint” | fiosru_review must NOT be selected |
| “I want to review my Fiosrú complaint” | fiosru_review |
| “I want to appeal a Fiosrú decision” | fiosru_review |
| “Fiosrú said my complaint is inadmissible” | fiosru_review |
| “Fiosrú discontinued my complaint” | fiosru_review_discontinuance |
| “My complaint was discontinued and I want a review” | fiosru_review |
| “Fiosrú finished investigating my complaint; what happens next?” | fiosru_post_investigation |
| “I need information about my Fiosrú investigation” | fiosru_victim_information |
| “I want to complain about a Garda member” | fiosru_complaint_screen |


## Crime-reporting / online-reporting boundary regressions — 26 Sep 2026

The online-crime route is a screening route, not a blanket replacement for ordinary crime reporting. Generic online-reporting wording may identify the screening process, but excluded crime categories must remain directed to the station route, and emergency indicators must remain authoritative.

| Input | Expected route |
|---|---|
| “I want to report a crime” | crime_general |
| “I want to report a crime online” | crime_online_router |
| “I want to report a crime online but don't know if the form applies” | crime_online_router |
| “Can I report this crime online?” | crime_online_router |
| “There was a burglary and I want to report it online” | station_directory |
| “My car was stolen and I want to report it online” | station_directory |
| “Someone robbed me and I want to report it online” | station_directory |
| “My firearm was stolen and I want to report it online” | station_directory |
| “A violent crime happened and I want to report it online” | station_directory |
| “There is a crime in progress” | emergency_999_112 |
| “Someone is in immediate danger” | emergency_999_112 |
| “My property was stolen and it was worth €500” | theft_declaration |
| “My property was stolen and it was worth €500; can I report it online?” | theft_declaration |
| “My property was stolen and it was worth €1,500; can I report it online?” | station_directory |
| “I am reporting something that happened yesterday” | no automatic crime route |


## Complaint / victim-support collision regressions — 26 Sep 2026

Explicit victim-support requests should remain on the victim-services route even when the person describes a crime. Garda-personnel conduct complaints should remain on the Fiosrú complaint-screen route rather than being treated as ordinary crime reports.

| Input | Expected route |
|---|---|
| “I am a victim of a crime and need support” | victim_services |
| “I was a victim of a crime and need victim support” | victim_services |
| “I am a crime victim and need support after the incident” | victim_services |
| “I want to report a crime” | crime_general |
| “I want to report a crime and need support as a victim” | victim_services |
| “I want to complain about a Garda member” | fiosru_complaint_screen |
| “I was affected by Garda conduct and want to complain” | fiosru_complaint_screen |
| “I want to report a crime committed by someone else” | crime_general |
| “I need support after a crime but do not want to report it here” | victim_services |
| “I want information about victim services” | victim_services |


## Data-access / FOI / AIE collision regressions — 26 Sep 2026

The information-access routes are intentionally distinct. Personal-data wording routes to the data-access screening process; explicit FOI wording routes to FOI; environmental-information wording routes to AIE. A generic request for “records” or “information” remains unresolved rather than being assigned a legal regime by guesswork.

| Input | Expected route |
|---|---|
| “I want to see personal data Gardaí hold about me” | data_access_router |
| “I want my personal records about me” | data_access_router |
| “What personal data does Garda hold about me?” | data_access_router |
| “I want to make an FOI request” | foi |
| “I want Garda records under FOI” | foi |
| “I want administrative information under FOI” | foi |
| “I want environmental information held by Gardaí” | aie |
| “I want environmental records about pollution” | aie |
| “I want environmental information under AIE” | aie |
| “I want Garda records” | no automatic crime route |
| “I want information about an incident” | no automatic crime route |
| “I want my data” | no automatic crime route |
| “I need information” | no automatic crime route |
| “I want CCTV footage” | no automatic crime route |


## Firearms-route collision regressions — 26 Sep 2026

Firearms routing must preserve the distinction between first-time/general applications, renewals, and non-resident applications. The specialist branches run before the generic firearms matcher. Emergency screening and excluded-crime handling remain higher priority.

| Input | Expected route |
|---|---|
| “I want a firearm certificate” | firearms_application |
| “I want to apply for a gun licence” | firearms_application |
| “I want to renew my firearm certificate” | firearms_renewal |
| “I need to renew my firearms licence” | firearms_renewal |
| “I am a non-resident applying for a firearm certificate” | firearms_nonresident |
| “I live abroad and want to apply for a firearm certificate” | firearms_nonresident |
| “I need information about firearms” | firearms_application |
| “My firearm was stolen” | station_directory |
| “My firearm was stolen and I want to report it online” | station_directory |


## Confidential-information collision regressions — 26 Sep 2026

Confidential-information routing requires explicit confidentiality or anonymity intent. Generic phrases such as “give information” must not intercept ordinary crime, traffic, firearms, or service questions.

| Input | Expected route |
|---|---|
| “I want to give information” | no automatic route |
| “I want to give information about dangerous driving” | traffic_watch |
| “I want to give information about a crime” | crime_general |
| “I want to give information anonymously” | garda_confidential |
| “I want to report this confidentially” | garda_confidential |
| “I want to remain anonymous when giving information” | garda_confidential |
| “I need confidential information about a Garda service” | garda_confidential |


## Awards / permits / CCTV collision regressions — 26 Sep 2026

These specialist service routes require their service-specific terms. Generic requests for a “permit”, “award”, “camera”, or “load” must not be assigned a specialist route without sufficient context.

| Input | Expected route |
|---|---|
| “I want to nominate a young person for a Garda Youth Award” | youth_awards |
| “I want information about the Garda Youth Awards” | youth_awards |
| “I need an abnormal load permit” | abnormal_loads |
| “I need an oversized load permit” | abnormal_loads |
| “I want a public collection permit” | collection_permit |
| “I need a permit for a public collection” | collection_permit |
| “I need a gaming permit” | gaming_permit |
| “I need a lottery permit for gaming” | gaming_permit |
| “I want information about public CCTV” | public_cctv_institutional |
| “I want to request public CCTV footage” | public_cctv_institutional |
| “I want a permit” | no automatic route |
| “I want an award” | no automatic route |
| “I saw a camera” | no automatic route |
| “I need information about a load” | no automatic route |


## Certificate / vetting / Fiosrú lifecycle regressions — 26 Sep 2026

Certificate and vetting requests must remain distinguishable, while Fiosrú lifecycle wording must preserve the distinction between legacy GSOC matters, discontinuance, review, post-investigation outcomes, victim information, and accessibility.

| Input | Expected route |
|---|---|
| “I need a Garda Police Certificate” | police_certificate_router |
| “I need a police certificate for another country” | police_certificate_router |
| “I need Garda vetting for employment” | garda_vetting |
| “I need vetting for volunteering” | garda_vetting |
| “I need a criminal record certificate for work” | no automatic route |
| “I have an old GSOC complaint from before Fiosrú” | gsoc_legacy_transition |
| “Fiosrú stopped my investigation” | fiosru_review_discontinuance |
| “Fiosrú discontinued my complaint and I want to review it” | fiosru_review |
| “I want to review my Fiosrú decision” | fiosru_review |
| “Fiosrú finished investigating my complaint; what happens next?” | fiosru_post_investigation |
| “I need information about my Fiosrú investigation” | fiosru_victim_information |
| “I need help accessing Fiosrú” | fiosru_accessibility |
| “I need an accessible Garda service” | accessibility_garda |


## Accessibility / property / traffic review precedence regressions — 26 Sep 2026

Emergency SMS, property-process, fixed-charge, prosecution-review, and traffic routes must remain distinguishable when wording overlaps. Emergency indicators remain authoritative before every specialist route.

| Input | Expected route |
|---|---|
| “I cannot speak and need emergency help” | emergency_999_112 |
| “I am deaf and need emergency SMS” | emergency_sms_112 |
| “I need help using Garda services because I cannot hear” | emergency_sms_112 |
| “I found property” | unclaimed_property |
| “I found property in a taxi” | property_found_taxis_psvs |
| “Garda is holding my property” | property_garda_possession |
| “I want information about a fixed charge notice” | traffic_fcn_information |
| “I want to challenge my fixed charge notice” | fixed_charge_notice_review |
| “I want to review the decision not to prosecute” | prosecution_decision_review |
| “I want to report dangerous driving” | traffic_watch |
| “There is dangerous driving and someone is in immediate danger” | emergency_999_112 |
| “I want to report a road traffic incident” | traffic_watch |
| “I want to challenge a traffic fine because I disagree with it” | traffic_fcn_information |



## Route verification-state integrity regression

- Every route record must contain exactly one value from the approved verification-state vocabulary.
- The current registry must contain 41 route records with 41 unique route IDs.
- Verification state is metadata for audit transparency; it must not bypass the frontend's independent destination allowlist.
- tel:112 and tel:999 are valid emergency destinations under the frontend allowlist.
- firearms_nonresident and fiosru_complaint_screen have now been source-verified; the former remains conflict-aware and the latter is verified_current.


## Verification metadata completeness regression

- Every `verified_current` route has `verified_on`.
- Every `verified_current_with_conflict` route has an explicit conflict/maintenance note.
- Every `verified_guidance_only` route has an explicit guidance-only rationale.
- No route may rely on the aggregate audit ledger alone to explain its verification state.


## Frontend verification-state routing regression

- The frontend must reject a route registry record whose `verification_status` is missing or outside the approved vocabulary.
- `verified_current` results may state that current official sources were verified.
- `verified_current_with_conflict` results must warn that official sources contain a documented difference and direct the citizen to the linked official guidance.
- `verified_guidance_only` results must say that the route is supported by current official guidance and that exact legal/eligibility details may depend on circumstances.
- Unknown or research-only states must not be presented as fully verified.


## Emergency SMS precedence regression — 26 Sep 2026

The generic emergency matcher must not intercept the dedicated Emergency SMS route when the phrase is specifically about emergency SMS/text access. Explicit danger indicators still take precedence.

| Input | Expected route |
|---|---|
| “I am deaf and need emergency SMS” | emergency_sms_112 |
| “I need emergency SMS” | emergency_sms_112 |
| “I am deaf and there is immediate danger” | emergency_999_112 |
| “I need emergency help and someone is in danger” | emergency_999_112 |


## Ambiguous-input negative matrix — 26 Sep 2026

These cases intentionally remain unresolved. The router must not manufacture a route when the citizen has not supplied enough information to distinguish the relevant service.

| Input | Expected route |
|---|---|
| “I want to complain” | unresolved |
| “I want to report something” | unresolved |
| “I want a review” | unresolved |
| “I want to appeal” | unresolved |
| “I want to challenge something” | unresolved |
| “I have a problem with Gardaí” | unresolved |
| “I need information about Garda records” | unresolved |
| “I want my data” | unresolved |
| “I want my neighbour’s personal data” | unresolved |
| “I want CCTV footage” | unresolved |
| “I want information about an incident” | unresolved |
| “I want to report something about my neighbour” | unresolved |
| “I need a certificate to work in another country” | unresolved |
| “I want information about a prosecution decision” | unresolved |
| “A taxi passenger left property” | unresolved |
| “I want to complain about a collection permit” | unresolved |
| “I want to challenge an abnormal load permit” | unresolved |
| “I want to complain about a youth award” | unresolved |

“Unresolved” means the production chooser returns no route; it is not a legal conclusion about the underlying matter.

## Stolen-property specialist precedence regression — 26 Sep 2026

Generic theft parsing must not intercept specialist property-process wording when the same sentence also contains “stolen”.

| Input | Expected route |
|---|---|
| “I found stolen property in a taxi” | `property_found_taxis_psvs` |
| “Gardaí are holding my stolen property” | `property_garda_possession` |
| “My stolen property is being held by Gardaí” | `property_garda_possession` |
| “I found property in a taxi” | `property_found_taxis_psvs` |

## Full precedence stress matrix — 26 Sep 2026

These cases are checked against the complete ordering of the production `choose()` function, not isolated specialist regexes. The purpose is to catch broad earlier gates intercepting a more specific route.

| Input | Expected route |
|---|---|
| “My firearm was stolen” | `station_directory` |
| “I want to renew my firearm certificate” | `firearms_renewal` |
| “My property was stolen and it was worth €500” | `theft_declaration` |
| “I found stolen property in a taxi” | `property_found_taxis_psvs` |
| “Gardaí are holding my stolen property” | `property_garda_possession` |
| “Fiosrú discontinued my complaint and I want a review” | `fiosru_review` |
| “Fiosrú stopped investigating my complaint” | `fiosru_review_discontinuance` |
| “Fiosrú finished investigating my complaint” | `fiosru_post_investigation` |
| “I want information about my Fiosrú investigation” | `fiosru_victim_information` |
| “I want to appeal the prosecution decision” | `prosecution_decision_review` |
| “I received a fixed charge and want a review” | `fixed_charge_notice_review` |
| “I want to report this crime online” | `crime_online_router` |
| “There was a burglary and I want to report it online” | `station_directory` |
| “I want to report dangerous driving” | `traffic_watch` |
| “I want to give information anonymously about dangerous driving” | `garda_confidential` |
| “I am deaf and need emergency text” | `emergency_sms_112` |
| “I am deaf and there is immediate danger” | `emergency_999_112` |

The matrix is intentionally small and high-consequence: it tests precedence boundaries rather than attempting to prove legal eligibility from free text.

## Emergency text / SMS precedence regression — 26 Sep 2026

The emergency gate must not capture SMS/text-specific requests merely because they contain the word “emergency”. Bare emergency danger language must still retain precedence.

| Input | Expected route |
|---|---|
| “I need emergency text” | `emergency_sms_112` |
| “I need emergency text information” | `emergency_sms_112` |
| “I need emergency SMS” | `emergency_sms_112` |
| “I need to contact emergency services by text” | `emergency_sms_112` |
| “There is an emergency and someone is in danger” | `emergency_999_112` |
| “There is an emergency and someone is seriously injured” | `emergency_999_112` |

## Information-access semantic stress regressions — 26 Sep 2026

The router must not infer FOI, AIE or personal-data rights from generic “information”, “records”, “data” or “CCTV” wording. A specific legal regime must be established by the citizen's wording before routing.

| Input | Expected route |
|---|---|
| “I want to see personal data Gardaí hold about me” | `data_access_router` |
| “What personal data does Garda hold about me?” | `data_access_router` |
| “I want my Garda personal records” | `data_access_router` |
| “I want my neighbour’s personal data” | no automatic route |
| “I want my data” | no automatic route |
| “I want to make an FOI request” | `foi` |
| “I want Garda records under FOI” | `foi` |
| “I want administrative information under FOI” | `foi` |
| “I want environmental information held by Gardaí” | `aie` |
| “I want environmental records about pollution” | `aie` |
| “I want environmental information under AIE” | `aie` |
| “I want Garda records” | no automatic route |
| “I want information about an incident” | no automatic route |
| “I need information” | no automatic route |
| “I want CCTV footage” | no automatic route |
| “I want public CCTV footage” | `public_cctv_institutional` |

## Property / theft semantic collision stress regressions — 26 Sep 2026

Specialist property-process wording must be evaluated before generic theft parsing. The presence of “stolen”, a monetary value, or a taxi/PSV reference must not redirect a clearly identified property-handling process.

| Input | Expected route |
|---|---|
| “I found property” | `unclaimed_property` |
| “I found lost property” | `unclaimed_property` |
| “I found property in a taxi” | `property_found_taxis_psvs` |
| “I found stolen property in a taxi” | `property_found_taxis_psvs` |
| “I found property in a PSV worth €500” | `property_found_taxis_psvs` |
| “Taxi found property worth €1,500” | `property_found_taxis_psvs` |
| “Gardaí are holding my property” | `property_garda_possession` |
| “Gardaí are holding my stolen property” | `property_garda_possession` |
| “My stolen property is being held by Gardaí” | `property_garda_possession` |
| “My property was stolen and it was worth €500” | `theft_declaration` |
| “My property was stolen and it was worth €1,500” | `station_directory` |
| “I found a stolen item” | `crime_general` |
| “I need information about property” | no automatic crime route |

## Crime-reporting / theft-value semantic stress regressions — 26 Sep 2026

The online crime boundary must remain conservative. Explicit excluded categories go to the station route; qualifying theft values may use the theft declaration; a theft with no stated value remains general crime screening.

| Input | Expected route |
|---|---|
| “I want to report a crime” | `crime_general` |
| “I want to report a crime online” | `crime_online_router` |
| “Can I report this crime online?” | `crime_online_router` |
| “My property was stolen and it was worth €500” | `theft_declaration` |
| “My property was stolen and it was worth €1,000” | `theft_declaration` |
| “My property was stolen and it was worth €1,001” | `station_directory` |
| “My property was stolen and it was worth €1,500” | `station_directory` |
| “My property was stolen” | `crime_general` |
| “There was a burglary last night” | `station_directory` |
| “My car was stolen” | `station_directory` |
| “My firearm was stolen” | `station_directory` |
| “Someone robbed me” | `station_directory` |
| “A violent crime happened” | `station_directory` |
| “There is a crime in progress” | `emergency_999_112` |
| “Someone is in immediate danger” | `emergency_999_112` |

## Fiosrú / prosecution-decision appeal-boundary regressions — 26 Sep 2026

Generic “appeal” or “challenge” language must not be assigned to a legal review route unless the wording identifies the relevant decision/process. Fiosrú review wording remains tied to Fiosrú context; prosecution-decision review requires the prosecution decision to be identified.

| Input | Expected route |
|---|---|
| “I want to appeal” | no automatic route |
| “I want to challenge something” | no automatic route |
| “I want to review my complaint” | no automatic route |
| “I want to appeal my Fiosrú decision” | `fiosru_review` |
| “I want to review my Fiosrú complaint” | `fiosru_review` |
| “Fiosrú said my complaint is inadmissible and I want a review” | `fiosru_review` |
| “Fiosrú discontinued my complaint and I want a review” | `fiosru_review` |
| “I want to challenge the decision not to prosecute” | `prosecution_decision_review` |
| “I want to review the decision not to prosecute” | `prosecution_decision_review` |
| “I want to appeal the prosecution decision” | `prosecution_decision_review` |
| “I want to challenge a decision” | no automatic route |

## Emergency SMS / accessibility semantic boundary regression — 26 Sep 2026

Emergency SMS is a dedicated emergency-access route. Deafness, hearing/speech impairment or a general accessibility need must not by itself be treated as a request for SMS 112. Explicit emergency danger still takes the emergency 999/112 route first.

| Input | Expected route |
|---|---|
| “I need emergency SMS” | `emergency_sms_112` |
| “I need to contact emergency services by SMS” | `emergency_sms_112` |
| “I need SMS 112 information” | `emergency_sms_112` |
| “I am deaf and there is immediate danger” | `emergency_999_112` |
| “I cannot hear and need emergency help” | `emergency_999_112` |
| “I am deaf and need accessible Garda help” | `accessibility_garda` |
| “I cannot hear and need an accessible Garda service” | `accessibility_garda` |
| “I cannot speak and need accessibility support from Gardaí” | `accessibility_garda` |

## Additional precedence stress cases — 26 Sep 2026

| Input | Expected route |
|---|---|
| “I need emergency SMS” | emergency_sms_112 |
| “I need help using Garda services because I cannot hear” | emergency_sms_112 |
| “I want to give information anonymously about dangerous driving” | garda_confidential |
| “I want to report dangerous driving” | traffic_watch |
| “I want to report a stolen firearm” | station_directory |
| “I found property in a taxi” | property_found_taxis_psvs |
| “Garda is holding my property” | property_garda_possession |
| “Fiosrú discontinued my complaint and I want to review it” | fiosru_review |
| “Fiosrú stopped my investigation” | fiosru_review_discontinuance |
| “I want to review my Fiosrú decision” | fiosru_review |
| “I want information about my Fiosrú investigation” | fiosru_victim_information |
| “I need a Garda Police Certificate” | police_certificate_router |
| “I need Garda vetting for employment” | garda_vetting |
| “I need a gaming permit” | gaming_permit |
| “I need a public collection permit” | collection_permit |
