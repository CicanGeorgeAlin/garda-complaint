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
| "I want environmental information held by Gardaí" | aie |
| "I need Garda vetting for work" | garda_vetting |
| "I need a police certificate for another country" | police_certificate_router |
| "I want a firearm certificate" | firearms_application |
| "I need to contact my local Garda station" | station_directory |
| "I received a Fixed Charge Notice and want to challenge it" | fixed_charge_notice_review |
| "I am a crime victim and need support" | victim_services |
| "I want to organise a public collection" | collection_permit |
| "I need a permit for gaming" | gaming_permit |
| "I need information about an abnormal load" | abnormal_loads |
| "I want public CCTV in my area" | public_cctv_institutional |
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
