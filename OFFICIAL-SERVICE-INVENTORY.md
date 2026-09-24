# Garda Citizen Access — Official Service Inventory (Audit 01)

Updated: 24 September 2026

This is a working inventory of citizen-facing Garda routes found in current official Garda pages. It is not a legal opinion. Each route must be re-verified before being presented as a definitive eligibility decision.

## Central official directory

- Garda Online Services
  - https://www.garda.ie/en/about-us/online-services/
  - Current categories shown: Garda Vetting; Data Protection / FOI / Police Certificates; Firearms Licensing; Abnormal Loads; Online Crime Reporting; Online Hate Crime Reporting; National Age Card; Unclaimed Property.

## Core reporting routes

### Emergency
- 999 / 112.
- Current Traffic Watch guidance expressly says emergencies must use 999/112.
- Source: https://www.garda.ie/en/trafficwatchreport/

### Crime reporting
- General Garda guidance says crime reports can be made through local Garda stations, with specified online routes.
- Current online crime declaration excludes burglary/attempted burglary, stolen/attempted stolen vehicles, robbery involving force/threat, violent crime and stolen firearms.
- Source: https://www.garda.ie/en/about-us/online-services/online-crime-reporting/
- Important source conflict to resolve: an older/currently indexed Garda general-reporting page still states €500, while the live Online Services theft declaration currently states property not exceeding €1,000. The project must use the live specific route for the theft threshold and must not repeat the older €500 figure as current.
- Specific live theft declaration: https://www.garda.ie/en/about-us/online-services/theft-declaration/

### Traffic Watch
- Non-emergency traffic-related incidents.
- Current form requires confirmation that the matter is not an emergency and that the reporter is willing to make a statement and attend court if required.
- Current form says reports should be made within 6 months.
- Current form requires location, county, incident type, description, date, name, phone, email, address and preferred contact method.
- Source: https://www.garda.ie/en/trafficwatchreport/

### Hate crime / hate incident
- Dedicated Garda online reporting route.
- Emergency matters must use 999/112.
- Source: https://www.garda.ie/en/reportahatecrime/

### Confidential information
- Garda Confidential: 1800 666 111.
- Source: Garda services / reporting guidance.

## Garda-conduct complaints

### Fiosrú
- Statutory complaint body under the current policing framework.
- Official complaint route: https://www.fiosru.ie/complaints/submit-a-complaint/
- Fiosrú FAQ currently states:
  - normal complaint period: 12 months;
  - late complaints may be accepted where there is a good reason;
  - anonymous complaints are not accepted;
  - complainant must provide name/contact details;
  - direct witnessing or direct effect is required;
  - Garda name is not required before complaining;
  - relevant evidence can include date/time/location, witnesses, photographs/video/audio and injury/medical information.
- Source: https://www.fiosru.ie/about-us/faqs/
- Statutory framework: Policing, Security and Community Safety Act 2024, Part 6.

## Specialist / application / request services

### Garda Vetting
- eVetting is initiated by a registered organisation.
- Applicants are invited by that organisation.
- Current Garda page states applicants must be over 16; 16–18 requires parent/guardian consent; valid email/internet access; proof-of-identity process.
- Source: https://www.garda.ie/en/about-us/online-services/garda-vetting/

### Data Protection / GDPR access
- Garda Online Services directory contains the Data Protection / FOI / Police Certificates route.
- Personal data access is distinct from FOI and should be modelled as a separate route.
- Source: https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/

### FOI
- Separate from GDPR/Data Protection access.
- Must be modelled separately, including scope/exemptions and current application route.
- Source: Garda Data Protection / FOI / Police Certificates page.

### Police Certificate
- Separate from Garda Vetting and separate from GDPR/FOI.
- Must be modelled as its own certificate route, with current eligibility and application procedure verified from the live Garda page/form.
- Source: https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/

### Firearms licensing
- Garda publishes first-time, renewal, amendment/cancellation and other firearms forms.
- Current first-time guidance refers to Form FCA1 and local Garda station submission, with decision by the relevant Superintendent/Chief Superintendent as applicable.
- Current Garda page also explicitly describes a non-resident firearm certificate route.
- Source: https://www.garda.ie/en/about-us/online-services/firearms-licensing/
- Example current source: https://www.garda.ie/en/about-us/online-services/firearms-licensing/firearm-certificate-renewals.html
- This project should link to official forms rather than recreate them.

### Abnormal loads
- Garda guidance says certain abnormal loads require permits from relevant local authorities and that Garda National Traffic Bureau must be informed and receive a copy of the application at least 4 working days before submission to the local authority.
- Source: Garda FAQ: https://www.garda.ie/en/faqs/?id=4853
- This is a cross-authority route and should not be presented as a Garda-only application.

### National Age Card
- Voluntary proof-of-age card for people aged 18+.
- Current Garda page says application/payment is online through the Age Card service, followed by local Garda-station authentication with specified ID/photo.
- Legal source identified by Garda: Intoxicating Liquor Act 1988 (Age Card) Regulations 2007.
- Source: https://www.garda.ie/en/about-us/online-services/national-age-card/

### Unclaimed property
- Garda has a public-facing unclaimed-property route/pilot showing selected lost/stolen property in Garda possession.
- It is a recovery/search service, not a substitute for reporting theft.
- Source: https://www.garda.ie/en/about-us/online-services/unclaimed-property/

### Property found in taxi / PSV
- Garda publishes a dedicated route for property lost in taxis/PSVs.
- Current Garda pages identify a small number of stations/emails handling these searches.
- Current pages also contain PSV application forms.
- Sources:
  - https://www.garda.ie/en/roads-policing/property-found-in-taxi-psv.html
  - https://www.garda.ie/en/roads-policing/roads-policing-unit/property-found-in-taxis-and-psvs-and-forms/

## Station-level / less-visible services

Garda's official "Services Provided" material states that local stations hold information leaflets and application forms and identifies services including:
- Victims of Crime Services
- Crime prevention
- Firearm licensing
- Property in Garda possession
- Property found in taxis
- Traffic Watch
- Safety camera locations
- Fixed Charge Notices

Source:
https://www.garda.ie/en/freedom-of-information/publication-scheme/services-provided.html

Therefore the master inventory cannot rely only on the Online Services directory. Site-wide Garda search and service/department pages must also be audited.

## Architecture rule

The public interface should classify a user's need before linking to an official destination:

1. Emergency
2. Crime report
3. Garda-conduct complaint
4. Traffic/road report
5. Hate crime/hate incident
6. Confidential information
7. Data access / GDPR
8. FOI
9. Certificate
10. Vetting
11. Licence / permit / application
12. Property recovery
13. Victim service
14. Other Garda/local-authority service
15. Not sure

For each route, the master record should contain:
- plain-English purpose
- legal basis
- exact provision where applicable
- eligibility
- geographic scope
- emergency status
- official online route
- official form
- email
- phone
- postal/in-person route
- information/evidence
- deadline
- confidentiality/anonymity
- responsible authority
- next steps
- review/appeal
- source
- verification date
- confidence/status

## Critical rule

Never invent an application form or claim that information entered into this website has been submitted to An Garda Síochána, Fiosrú, a local authority or another public body. The site is a navigation and explanation layer.



## Audit 02 — additional citizen actions

### Fixed Charge Notices (FCN/FPN)
- This is a distinct citizen route and should not be buried under generic traffic reporting.
- Garda guidance currently states that the normal statutory payment window is 56 days: first 28 days at the fixed charge amount, followed by 28 days at the amount plus 50%.
- Garda also publishes a specific cancellation/review route. A recipient can apply for cancellation; the published guidance describes circumstances considered by the cancelling authority.
- The project should distinguish:
  1. pay a notice;
  2. request a cancellation/review;
  3. request a photograph for eligible camera speeding notices;
  4. juvenile diversion request where the recipient is under 18;
  5. general information about a notice.
- Sources:
  - https://www.garda.ie/en/roads-policing/fixed-charge-notices/
  - https://www.garda.ie/en/roads-policing/fixed-charge-notices/cancelling-fixed-charge-notices.html
- Do not turn Garda guidance into a statement that a cancellation will be granted; the authority decides the application.

### Victim services
- Garda has a dedicated Victim Services structure and local Garda Victim Service Offices.
- The route is primarily support/information/communication for victims rather than a replacement for making the crime report.
- Current Garda information says victims are entitled to information, support and protection and that divisional Victim Service Offices act as contact points.
- Sources:
  - https://www.garda.ie/en/victim-services/
  - https://www.garda.ie/en/victim-services/garda-victim-service/

### Traffic matters — broader routing
The Garda traffic section identifies several different citizen needs that should eventually have separate route cards:
- road traffic collision;
- witnessing dangerous driving;
- safety camera information;
- penalty points / road offences;
- Fixed Charge Notice;
- NCT/driver-licence information (where the responsible authority is another body);
- road-safety information.
Source:
https://www.garda.ie/en/crime/traffic-matters/

### Property in Garda possession
- Treat this separately from reporting a theft and from unclaimed-property browsing.
- The Garda Services Provided page specifically identifies property in Garda possession as a public service.
- Source:
https://www.garda.ie/en/freedom-of-information/publication-scheme/services-provided.html

### Property found in taxis / PSVs
- Current Garda page says only five listed stations accept found property from taxis/PSVs and provides dedicated email addresses.
- The same page contains PSV 15 and PSV 18 application forms.
- This confirms that site-wide/department-level auditing is necessary because these routes are not represented by the central Online Services directory.
- Source:
https://www.garda.ie/en/roads-policing/roads-policing-unit/property-found-in-taxis-and-psvs-and-forms/

### Unclaimed property
- Current Garda page describes a pilot allowing members of the public to view photographs of selected lost/stolen property in Garda possession.
- It explicitly says stolen property should still be reported to Gardaí.
- Treat this as a recovery/search route, not as the theft-report route.
- Source:
https://www.garda.ie/en/about-us/online-services/unclaimed-property/

## Fiosrú review route

### Statutory review
- A complainant can request a review when Fiosrú has notified them that a complaint is inadmissible or an investigation is being discontinued.
- Current Fiosrú guidance states the request should normally be made within 28 days of being informed of the decision; a later request can be made with good reasons for the delay.
- The requester must be the person who made the initial complaint and must provide enough information to link the request to the original complaint, including the case reference where available.
- Current Fiosrú guidance says the review considers whether the decision was fair, reasonable and proportionate on the available facts.
- Official review page: https://www.fiosru.ie/complaints/statutory-review/
- Request page: https://www.fiosru.ie/complaints/statutory-review/how-to-request-a-review-of-your-inadmissible-complaint/
- Current Fiosrú review form also covers discontinuation decisions and provides postal/email/online routes.
- Statutory basis: section 224 of the Policing, Security and Community Safety Act 2024.

## Audit priority

The next inventory pass should focus on:
1. every downloadable Garda public application/form;
2. every route that requires a local Garda station;
3. every route where Garda is only one part of a multi-authority process;
4. every deadline or review/cancellation mechanism;
5. Dublin station/divisional operational differences;
6. routes where the central Garda Online Services directory does not provide the complete process.



## Audit 03 — victim decision/review forms and downloadable forms

### Garda decision not to prosecute — victim routes
- This is a separate route from a Fiosrú complaint.
- Where Gardaí decide not to prosecute, the victim (and specified family/solicitor categories) may request a summary of the reasons.
- Current Garda guidance states the request for the summary should normally be made within 28 days of receiving the notification of the decision not to prosecute.
- If dissatisfied with the summary, the victim can request a review of the decision. The current Garda guidance states that review should normally be requested within 28 days of receiving the summary.
- Garda states these time limits may be extended where the relevant authority is satisfied that an extension is warranted.
- The review request is made in writing to the Chief Superintendent at the Garda station where the incident was investigated, with a Superintendent appointed to review the decision who had no prior involvement in the case.
- Garda publishes the RS1 and RR1 forms and says copies can also be obtained at local Garda stations.
- This route must be presented separately from:
  - a complaint about Garda conduct (Fiosrú);
  - an appeal/review of a court decision;
  - a DPP decision review.
- Source:
  https://www.garda.ie/en/victim-services/garda-victim-service/information-on-prosecution/

### Downloadable-form discovery rule
The official Garda site contains public PDF/application forms outside the central Online Services directory. Examples verified during this audit include:
- Firearm Certificate Application — FCA1:
  https://www.garda.ie/en/about-us/online-services/firearms-licensing/fca1_firearm_certificate_application.pdf
- Police Certificate application:
  https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/an-garda-siochana-police-certificate-application-form-feb-2022.pdf
- Garda Youth Awards nomination forms:
  https://www.garda.ie/en/crime-prevention/community-engagement/an-garda-siochana-youth-awards/
- RS1 / RR1 victim decision-review forms:
  available from the Garda Information on Prosecution page above.

### FCA1 observations
- The current FCA1 PDF is marked March 2023 and is based on the Firearms Acts as amended.
- It contains separate application types including firearm certificate, restricted firearm certificate, limited firearm certificate, training firearm certificate and substitution of firearm.
- The form collects nationality, usual residence, county, local Garda station and other personal/application details.
- The project should link to the official FCA1 rather than reproduce it.
- Firearms are a regulated specialist route; the public interface should not give the impression that the general crime-reporting flow is an alternative application route.

### Important distinction: Garda form ≠ Garda online service
A downloadable PDF can be an official submission instrument even when it is not listed in the central Online Services directory. Therefore the master inventory will maintain separate delivery types:
- online service
- downloadable form
- station only
- email route
- postal route
- multi-authority

## Current verification notes

- Central Online Services page was rechecked 24 September 2026.
- Online crime declaration page was rechecked 24 September 2026 and currently excludes burglary, stolen/attempted stolen vehicles, robbery by force/threat, violent crime and stolen firearms. It also states theft declarations are for incidents in Ireland excluding Northern Ireland.
- Police Certificate page was rechecked 24 September 2026. It currently states approximately three-week processing and contains both online-completion and postal-submission instructions; because those instructions coexist, the project should preserve the ambiguity until the live submission flow is independently checked rather than inventing a single process.
- Garda Vetting page was rechecked 24 September 2026 and confirms the registered-organisation initiation model.



## Audit 04 — additional official citizen-facing routes

### Prosecution-decision review: source discrepancy resolved
- The current Garda "Information on Prosecution" page states:
  - summary of reasons: normally within 28 days;
  - review of the Garda decision: normally within 28 days of receiving the summary.
- However, the current Garda Victims Charter states a 56-day period for the review of the decision not to prosecute.
- A separate Garda guide for families bereaved by road collisions also states 28 days for a summary and 56 days for a review request to the DPP.
- Because official Garda sources are not consistent, the public interface must NOT present a single review deadline as universally applicable.
- Route design: show "time limit depends on the applicable review route/source; act promptly" and direct the user to the current official form/guidance, with the distinction between a Garda review and a DPP review made explicit.
- Sources checked 24 September 2026:
  - https://www.garda.ie/en/victim-services/garda-victim-service/information-on-prosecution/
  - https://www.garda.ie/en/victim-services/garda-victim-service/victims-charter.pdf
  - https://www.garda.ie/en/roads-policing/roads-policing-unit/roads-policing-initiatives/irva-guide-for-families-bereaved-by-road-collisions.pdf

### National Age Card
- Current Garda page confirms this is a voluntary proof-of-age card for people aged 18+.
- The process begins online at agecard.ie, then the applicant brings the generated application, specified ID and passport photograph to a local Garda station for authentication.
- It is not an identity card and is solely for proving age.
- Source:
  https://www.garda.ie/en/about-us/online-services/national-age-card/

### Garda Youth Awards
- Current 2026 page provides online nomination routes and English/Irish PDF nomination forms for Individual, Group, Special Achievement and Community Safety categories.
- Garda states forms are also available from local Garda stations.
- Eligibility includes young people aged 13–21.
- Local divisional arrangements may vary; the page advises contacting the local Community Garda, Juvenile Liaison Officer or Garda station to confirm whether the local area is participating.
- Source:
  https://www.garda.ie/en/crime-prevention/community-engagement/an-garda-siochana-youth-awards/

### Firearm certificate applications
- Current FCA1 form is a formal Garda application instrument, not merely an information leaflet.
- Garda's current renewal page says first-time applicants must complete FCA1 and return it to the local Garda station for consideration by the relevant Superintendent, or Chief Superintendent for a restricted firearm application.
- The master catalogue must therefore distinguish:
  - first-time firearm certificate;
  - restricted firearm certificate;
  - renewal;
  - other certificate/application types;
  rather than treating "firearms licensing" as one generic route.
- Sources:
  - https://www.garda.ie/en/about-us/online-services/firearms-licensing/fca1_firearm_certificate_application.pdf
  - https://www.garda.ie/en/about-us/online-services/firearms-licensing/firearm-certificate-renewals.html

### Data-access / SIS-specific rights
- Garda states that F20 is used for access to personal data held by An Garda Síochána.
- Garda's SIS material additionally identifies rights of access, rectification and erasure for SIS data and directs people to the Garda Data Protection Unit.
- This should be represented as a specialist sub-route under data protection rather than a new generic crime-reporting route.
- Sources:
  - https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/
  - https://www.garda.ie/en/about-us/our-departments/garda-national-crime-security-intelligence-service1/schengen-information-system-sis-/what-safeguards-are-in-place-to-deal-with-this-.html

## Audit 04 — implementation rules

1. Never collapse two official routes merely because they have similar names.
2. When official Garda pages conflict on a deadline, preserve the conflict and route the citizen to the authoritative current form/authority instead of inventing certainty.
3. Distinguish Garda review, Fiosrú review and DPP review.
4. Distinguish an application form from an information page.
5. Distinguish national routes from local divisional/station arrangements.
6. Record source date and verification status for every deadline-sensitive route.



## Audit 05 — information-access routes

### FOI: separate statutory route
- An Garda Síochána is only partially included under the Freedom of Information Act 2014.
- Current Garda guidance says the FOI scope covers administrative records relating to:
  - Human Resources;
  - Finance;
  - Procurement.
- A person anywhere in the world may make an FOI request according to current Garda FAQ guidance.
- Requests can be made by email or in writing and should state that they are being made under the FOI Act, identify the records sought clearly, and give a correspondence address.
- Current Garda guidance gives a normal decision period of 4 weeks on one FOI information page, while another current Garda FAQ describes 20 working days. These descriptions should be treated carefully and the project should direct users to the current official FOI guidance rather than hard-code a conflicting deadline.
- Official sources:
  - https://www.garda.ie/en/information-centre/freedom-of-information/
  - https://www.garda.ie/en/information-centre/freedom-of-information/freedom-of-information/freedom-of-information-foi-frequently-asked-questions-faqs-.html
  - https://www.garda.ie/en/Information-centre/Freedom-of-Information/Freedom-of-Information/FOI-Application-Form1.pdf

### AIE: access to environmental information
- Garda publishes a separate route under the European Communities (Access to Information on the Environment) Regulations.
- An AIE request must state that it is made under the AIE Regulations, be in writing or electronic form, provide contact details, describe the environmental information as specifically as possible, and state the preferred access format where relevant.
- Garda currently directs AIE requests to the same FOI Office email/postal route.
- The AIE route must NOT be collapsed into FOI: it has a different legal basis and concerns environmental information.
- Source:
  https://www.garda.ie/en/information-centre/freedom-of-information/freedom-of-information/how-do-i-make-a-request-for-information-on-the-environment-.html

### GDPR / F20: subject access
- Current Garda F20 form is a Subject Access Request under GDPR/Data Protection Act 2018.
- The form requires a written, signed request and acceptable proof of identity.
- Current F20 states the normal response period is one month, with possible extension by up to two further months for complex or numerous requests.
- It expressly distinguishes personal-data access from Garda Vetting, Police Certificate, Garda Reference and Security Clearance.
- Current source:
  https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/an-garda-siochana-f20-october-2019-.pdf

### Information-access decision logs
- Garda publishes FOI decision logs and a publication scheme.
- The citizen-access engine should check whether requested information is already publicly available before directing a user to make a new FOI/AIE request.
- Current 2026 decision logs demonstrate that the FOI decision-log system remains actively used.
- Source:
  https://www.garda.ie/en/information-centre/freedom-of-information/decision-log/

## Audit 05 — implementation consequence

The information-access branch now has at least three distinct routes:

1. Personal data about yourself → GDPR/Data Protection / F20
2. Administrative Garda records within FOI scope → FOI
3. Environmental information → AIE

The interface must ask what kind of information the citizen wants before selecting the legal route.



## Audit 06 — Fiosrú and public-form discovery

### Fiosrú current complaint system
- Current Fiosrú complaints page confirms separate routes for:
  - Submit a Complaint
  - Statutory Review
  - Victims of Crime
  - Complaints Suitable for Resolution by An Garda Síochána
  - GSOC complaints
- Current complaint form says it cannot be saved mid-way and should be completed in full; after submission, the user can download a copy once and receives an acknowledgement email.
- Current Fiosrú guidance says complaints may be made online, by post, or at a Garda station.
- Current Fiosrú FAQ states identities are not made public, but information including who made the complaint may be shared with the Garda Commissioner and involved Gardaí where required by law; identity can become public in circumstances such as criminal proceedings.
- Sources:
  - https://www.fiosru.ie/complaints/
  - https://www.fiosru.ie/complaints/submit-a-complaint/
  - https://www.fiosru.ie/about-us/faqs/

### Fiosrú review delivery
- Current review route can be submitted by PDF via email or post.
- Current Review Unit contact: review@fiosru.ie.
- Current postal destination: Review Unit, Fiosrú, Office of the Police Ombudsman, 150 Upper Abbey Street, Dublin 1, D01 FT73.
- Accessibility support is available through the Access Officer.
- Source:
  https://www.fiosru.ie/complaints/statutory-review/how-to-request-a-review-of-your-inadmissible-complaint/

### Public-form discovery: Gaming Permit
- Garda currently hosts an official GP1 Gaming Permit Application.
- The form states it is specified by the Minister for Justice under section 9A of the Gaming and Lotteries Act 1956, as inserted by the Gaming and Lotteries (Amendment) Act 2019.
- The form states an application will not be considered until all information requested by the District Superintendent has been received.
- The form also states the proposed gaming activity date must be at least 60 days from the application date.
- This is a strong example of a specialist regulatory route that is not visible as a standard Online Services category.
- Source:
  https://www.garda.ie/en/about-us/our-departments/office-of-corporate-communications/news-media/gp1-gaming-permit-application1.pdf

### Public CCTV application
- Garda search currently exposes an official Public CCTV Section 28 Application Form for Local Authorities.
- This is a multi-authority/public-body route and should not be represented as an ordinary citizen Garda complaint.
- Source:
  https://www.garda.ie/en/about-us/online-services/public%20cctv/public-cctv-application-form.pdf

## Audit 06 — search methodology

The project must use two discovery layers:
1. central Online Services and Services sitemap;
2. site-wide Garda search for terms such as:
   - application form
   - form
   - permit
   - licence
   - certificate
   - request
   - review
   - cancellation
   - notification
   - local authority
   - station

Search results must then be classified into:
- citizen action;
- professional/business application;
- Garda internal form;
- information-only page;
- multi-authority process;
- historical/obsolete document.

This prevents search-index noise from becoming a false citizen route.



## Audit 07 — newly discovered public application routes

### Collection Permit
- Garda currently hosts an official Collection Permit Application Form.
- This should be classified as a specialist permit/application route, not a complaint or crime-report route.
- The existence of this current official form reinforces the need for site-wide form discovery.
- Source:
  https://www.garda.ie/en/about-us/our-departments/office-of-corporate-communications/news-media/news-archive/collection-permit-application-form.html

### Gaming Permit
- GP1 remains a verified current official application instrument.
- It is specified under section 9A of the Gaming and Lotteries Act 1956, as inserted by the 2019 amendment.
- The application requires the proposed gaming activity date to be at least 60 days from the application date.
- Source:
  https://www.garda.ie/en/about-us/our-departments/office-of-corporate-communications/news-media/gp1-gaming-permit-application1.pdf

### FOI / AIE current operational details
- Current Garda FAQ confirms FOI requests may be made by email or post and should identify the applicant, correspondence address and records sought.
- Current Garda FOI page states a response no later than 4 weeks.
- Current AIE page uses the same FOI Office route and states no initial AIE application fee.
- The project should display these as separate legal routes even where their operational contact point is the same.
- Sources:
  - https://www.garda.ie/en/information-centre/freedom-of-information/freedom-of-information/faqs.html
  - https://www.garda.ie/en/information-centre/freedom-of-information/freedom-of-information/how-do-i-make-a-request-for-information-on-the-environment-.html

### Police Certificate — current page confirms postal submission
- Current Garda Police Certificate FAQ currently instructs applicants to submit the completed application with certified identification and proof of address/previous addresses by post to the Superintendent and/or Assistant Principal Officer in the relevant Division.
- This is more specific than the general page's reference to online completion.
- Until the live online process is independently verified, the public site should treat postal submission as the currently explicit documented submission instruction and flag the online-completion wording for verification.
- Source:
  https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/

### Firearms: first-time versus renewal
- Current Garda guidance explicitly separates first-time FCA1 applications from renewal FCR forms.
- First-time applications use FCA1 and go to the local Garda station.
- Renewals use the pre-populated FCR form; Garda states only the pre-populated FCR is acceptable for renewal.
- Source:
  https://www.garda.ie/en/about-us/online-services/firearms-licensing/firearm-certificate-renewals.html

## Audit 07 — routing safeguards

- A permit/application must never be presented as a "complaint".
- A review/cancellation process must never be presented as a new incident report.
- A certificate must never be presented as Garda vetting unless the official source expressly says so.
- Where one official page gives a broad process and another gives the specific submission method, prefer the specific current submission instruction while recording the broader page as a verification note.
- Do not silently resolve contradictory official deadlines.



## Audit 08 — route taxonomy expansion

### Immigration / visa-related Garda documents
- Garda publishes police-certification material used for overseas visa/consular and related purposes.
- This is a certificate route, not Garda Vetting and not a general character-reference service.
- The eligibility and purpose must be displayed exactly as the current Garda source describes them.
- Source:
  https://www.garda.ie/en/about-us/online-services/data-protection-foi-police-certificates/

### Firearms licensing — delivery model
- Firearms applications are an example of a route where the citizen-facing process combines:
  1. an official Garda form;
  2. a local Garda-station submission;
  3. statutory decision-making by the relevant Garda authority;
  4. possible additional restrictions for restricted firearms.
- The engine should therefore store the legal decision-maker separately from the physical submission point.

### Abnormal loads — multi-authority routing
- Abnormal-load applications are not a simple Garda permit.
- Garda guidance says the relevant local authority issues the permit while Garda National Traffic Bureau is informed and receives a copy of the application before local-authority submission.
- The routing engine must identify the local authority as the permit authority and Garda as a required traffic-policing notification/consultation step.
- Source:
  https://www.garda.ie/en/faqs/?id=4853

### Local Garda station as submission point
- Several services use the local station as a submission/authentication/collection point without making the station the final decision-maker.
- Examples now recorded:
  - firearms applications;
  - National Age Card authentication;
  - victim/prosecution-review forms;
  - certain property routes.
- Therefore "Where do I submit this?" and "Who decides this?" must be separate fields.

## Audit 08 — citizen questions the engine must answer

For every discovered route, the interface should be able to answer:

1. **What is this for?**
2. **Is this an emergency?**
3. **Can I do it online?**
4. **Is there an official form?**
5. **Where do I submit it?**
6. **Who actually decides it?**
7. **What information/evidence is required?**
8. **Is there a deadline?**
9. **Can someone else apply for me?**
10. **Can I remain anonymous?**
11. **What happens after submission?**
12. **Can I review/appeal/challenge the decision?**
13. **Is another authority involved?**
14. **What is the exact legal basis?**
15. **When was this information last verified?**

## Audit 08 — data-model refinement

The master route record should now contain these distinct fields:

- route_id
- citizen_question
- plain_english_purpose
- route_type
- legal_basis
- decision_maker
- submission_point
- jurisdiction
- eligibility
- nationality_or_residency_rule
- emergency_rule
- online_route
- official_form
- email
- phone
- postal_route
- in_person_route
- evidence_required
- deadline
- anonymity
- confidentiality
- next_steps
- review_or_appeal
- other_authority
- source_url
- verified_on
- verification_status
- source_conflict
- notes



## Audit 09 — crime-reporting boundaries and emergency safeguards

### Online crime reporting is not a universal crime-reporting form
Current Garda online-crime guidance identifies categories that must not use the online declaration, including:
- burglary / attempted burglary;
- stolen / attempted stolen vehicle;
- robbery involving force or threat;
- violent crime;
- stolen firearm;
- emergencies.

The public engine must therefore ask about the nature and urgency of the incident before displaying the online declaration.

Source:
https://www.garda.ie/en/about-us/online-services/online-crime-reporting/

### Theft declaration
The current specific Garda theft-declaration page states that the online declaration is for theft of property not exceeding €1,000 and for thefts occurring in Ireland, excluding Northern Ireland.

The engine must not treat this as a general-purpose crime form.

Source:
https://www.garda.ie/en/about-us/online-services/theft-declaration/

### General reporting route
Where no specific online declaration applies, Garda guidance directs people toward local Garda stations/contact routes. The engine should therefore provide:
- the online route when eligible;
- otherwise the appropriate station/contact route;
- emergency escalation when the facts indicate immediate danger.

### Evidence preservation
The website should advise users to preserve original evidence and avoid unnecessarily editing/overwriting original files, while avoiding instructions that could interfere with an active investigation.

### Emergency override
No matter which category a user initially selects, an immediate-danger answer must override the ordinary route and direct to 999/112.

## Audit 09 — routing test cases

The future engine should be tested against at least these cases:

1. "Someone is attacking me now" → emergency.
2. "I saw dangerous driving but nobody is in immediate danger" → Traffic Watch/appropriate traffic route.
3. "My phone was stolen for €700" → eligible theft-declaration branch, subject to current form conditions.
4. "My car was stolen" → not the online theft declaration; local Garda reporting route/emergency depending on circumstances.
5. "A Garda member behaved improperly toward me" → Fiosrú complaint branch.
6. "I want all personal data Gardaí hold about me" → F20/data-access branch.
7. "I want Garda HR records" → FOI branch, subject to FOI scope/exemptions.
8. "I want environmental information held by Garda" → AIE branch.
9. "I received a Fiosrú inadmissibility decision" → statutory-review branch.
10. "I received an FCN and want it cancelled" → FCN cancellation/review branch.
11. "I need a firearm certificate" → firearms application branch.
12. "I need an Age Card" → National Age Card branch.
13. "I need a Police Certificate for an overseas purpose" → Police Certificate eligibility branch.
14. "I need Garda Vetting for a job" → registered-organisation/eVetting branch.
15. "I need an abnormal-load permit" → multi-authority/local-authority branch.

These are routing tests, not legal advice. Each must be rechecked whenever the underlying official source changes.



## Audit 10 — confidentiality, direct-contact, and evidence-routing safeguards

### Confidential information is a different route from a formal complaint
Current Garda guidance confirms that members of the public can provide information about crime or other activities confidentially through the Garda Confidential Line (1800 666 111). This must not be presented as equivalent to a Fiosrú complaint, and it must not be described as anonymous evidence of a Garda complaint. Source: https://www.garda.ie/en/contact-us/useful-contact-numbers/useful-contacts-for-garda-units.html

### Fiosrú complaint eligibility language
Current Fiosrú guidance says a complainant must normally be directly affected by, or have directly witnessed, the Garda behaviour concerned. Fiosrú also states that a complaint is not anonymous and requires name/contact details. A Garda name is not required if the complainant does not know it. Source: https://www.fiosru.ie/about-us/faqs/

The citizen engine should therefore distinguish:
- "I personally experienced this Garda behaviour" → Fiosrú complaint screening;
- "I directly witnessed this Garda behaviour" → Fiosrú complaint screening;
- "I heard about it from someone else / saw it in the news or social media" → do not present this as satisfying the ordinary Fiosrú complaint basis; consider whether another information/reporting route is appropriate;
- "I want to provide confidential information about crime/other activity" → Garda Confidential route.

### Evidence-routing safeguard
For an ordinary crime report, the engine should not tell a person to wait for an online form when:
- the incident is happening now;
- an offender remains at or nearby the scene;
- evidence remains at the scene.

Current Garda guidance expressly identifies these circumstances for avoiding the online theft declaration. Source: https://www.garda.ie/en/victim-services/reporting-a-crime-faqs/why-should-i-report-a-crime-/

### Hate-crime routing
The current Garda hate-crime service is specifically for hate crime and says emergencies must use 999/112. The online service should therefore appear only after the engine establishes that the person is describing a suspected hate-motivated crime/incident, rather than as a generic reporting form. Source: https://www.garda.ie/en/about-us/online-services/online-hate-crime-reporting/

### Station fallback
Where an online route is unavailable or unsuitable, the engine should provide the official Garda Station Directory rather than inventing a local contact. The current directory supports searching by division or station and includes an email-station function, while warning that emergency matters require 999/112. Source: https://www.garda.ie/en/contact-us/station-directory/

### Routing principles added
1. Emergency status is checked before category selection.
2. Confidential-information routes are not labelled as formal complaints.
3. Fiosrú eligibility is screened using direct-effect/direct-witness information.
4. Specific online forms are shown only after their conditions are met.
5. Official station fallback is used when no specific online route applies.
6. The engine never stores or forwards the citizen's substantive complaint merely because they used this website.


## Audit 11 — emergency and accessibility routing verification (24 September 2026)

### Emergency decision gate
Current Garda guidance confirms 999/112 should be used where an incident is happening now or someone is in immediate danger; examples include danger to life, risk of serious injury, crime in progress/about to happen, or an offender still at the scene or having just left. Garda also identifies 112 SMS as an emergency service for deaf, hard-of-hearing and speech-impaired users, while warning that SMS is non-real-time and delivery is not guaranteed.

Sources:
https://www.garda.ie/en/contact-us/useful-contact-numbers/useful-contacts-for-garda-units.html
https://www.garda.ie/en/faqs/

### Non-emergency fallback
For non-emergency/general enquiries, current Garda guidance directs users to their nearest/local Garda station. The station directory should therefore remain the default fallback when no specialised online route is appropriate.

### Fiosrú complaint screening
Current Fiosrú guidance confirms:
- direct effect or direct witnessing can support the complaint route;
- complaints are not anonymous;
- name and contact details are required;
- a Garda name is not required;
- complaints can in some circumstances be made on another person's behalf, subject to the stated representative/consent requirements.

The routing engine must preserve these as screening questions and must not convert them into a guarantee of admissibility.

### Accessibility
The engine should expose an accessibility/help route rather than assuming every citizen can use a long online form. Fiosrú provides an Access Officer contact for access or practical requirements, and Garda identifies an Access Officer for assistance accessing Garda services.

### High-risk specialist routes
The engine should continue to maintain specialist pathways separately from the generic crime branch. Current Garda material includes specialist support such as the Drug-Related Intimidation Reporting Programme. Such routes may involve confidentiality, local nominated inspectors, and safety considerations.

### Test additions
16. "I cannot speak/hear and this is an emergency" → emergency guidance including 112 SMS information, with its limitations.
17. "I need help accessing a Garda service because of a disability" → accessibility route, not a generic complaint.
18. "I heard about Garda behaviour on social media" → do not present ordinary Fiosrú complaint eligibility as established.
19. "I was directly affected by Garda behaviour but don't know the Garda's name" → Fiosrú screening; Garda identity is not a prerequisite.
20. "I want to report non-emergency crime and there is no specialised online route" → local Garda station fallback.
21. "I need help because of drug-related intimidation" → specialist safety/support route, with emergency override.

### Design rule
The engine should ask the smallest number of high-value questions first:
1. Is anyone in immediate danger?
2. What happened / what do you need?
3. Did it involve Garda personnel?
4. Did you experience it directly, witness it directly, or act on behalf of someone?
5. Is there a specialist route?
6. What is the relevant location/jurisdiction?
7. What official route is available now?

The engine should then explain the reason for the route before presenting the official destination.


## Audit 12 — specialist crime branches and Fiosrú resolution boundary (24 September 2026)

### Non-emergency crime fallback
Current Garda guidance says non-emergency crime can be reported to the local or any Garda station, and a Garda can take a report in person at any station. The station directory is therefore a genuine national fallback, not merely a Dublin feature. Source: https://www.garda.ie/en/victim-services/reporting-a-crime-faqs/where-can-i-get-more-information-.html

### Traffic Watch is a conditional route
The current Traffic Watch form requires the reporter to confirm the matter is not an emergency and that they are willing to make a statement and attend court if required. It also currently asks that reports be made within 6 months. Source: https://www.garda.ie/en/trafficwatchreport/
The engine must therefore screen for emergency status and date before displaying Traffic Watch.

### Domestic abuse requires its own safety branch
Current Garda guidance provides separate domestic-abuse reporting information: immediate danger → 999/112; non-immediate danger → local Garda station/advice, with the option to request a Garda of the same gender where possible. Source: https://www.garda.ie/en/crime/domestic-abuse/how-do-i-know-if-someone-is-a-victim-of-domestic-abuse-coercive-control-.html
The generic crime route must not obscure this specialist safety pathway.

### Fiosrú complaint resolution is not the same as a new Garda complaint
Fiosrú currently states that some admitted complaints concerning service-level/performance-management issues can be referred to An Garda Síochána for resolution. Examples include discourtesy, failure to respond/update, and certain public-desk/service issues. Fiosrú remains the entry point for the complaint; the citizen should not be redirected to start a separate Garda complaint merely because resolution may occur within Garda. Sources:
https://www.fiosru.ie/complaints/complaints-suitable-for-resolution-by-an-garda-siochana/
https://www.fiosru.ie/about-us/faqs/

### New routing tests
22. Non-emergency crime, no specialist form → local/any Garda station.
23. Traffic incident, non-emergency, within current Traffic Watch conditions → Traffic Watch.
24. Traffic incident requiring immediate response → emergency route, not Traffic Watch.
25. Domestic abuse, immediate danger → 999/112.
26. Domestic abuse, no immediate danger → specialist Garda/local-station route.
27. Admissible-looking Fiosrú service-level complaint → Fiosrú complaint route; explain that Fiosrú may refer it to Garda for resolution.
28. User asks to complain directly to Garda because Fiosrú may refer the matter to Garda → explain the distinction; do not create a duplicate complaint route.

### Architectural rule
A route can have multiple authorities involved without becoming multiple citizen submissions. The engine should identify:
- entry authority;
- investigating/resolving authority;
- decision-maker;
- review body;
- citizen's next action.
This prevents the common error of treating every authority mentioned in a process as a separate place the citizen must apply to.


## Audit 13 — statutory death/serious-harm boundary and service inventory recheck (24 September 2026)

### Section 203 is a referral/investigation pathway, not an ordinary citizen complaint form
Current Fiosrú material confirms that section 203(1) of the Policing, Security and Community Safety Act 2024 requires the Garda Commissioner, subject to the statutory provision, to refer without delay a matter that appears to indicate that an act or omission of Garda personnel may have resulted in death or serious harm. Fiosrú then appoints a designated officer to investigate under section 208(1)(b). A referral does not itself mean a Garda has been accused of wrongdoing.

Sources:
https://www.fiosru.ie/news-and-publications/latest-news/updated-fiosru-statement-following-receipt-of-s203-referral-15-may-2026/
https://www.fiosru.ie/news-and-publications/latest-news/fiosru-completes-independent-investigation-into-fatal-incident-in-dublin-city-centre/

### Citizen-facing routing rule for death/serious harm
If a citizen describes death or serious harm following contact with Garda personnel, the site must NOT tell the citizen that they personally "submit a section 203 referral". Instead:
- emergency / immediate danger remains 999/112;
- the site explains that a statutory referral/investigation framework exists;
- it directs the citizen to the appropriate Fiosrú contact/information route where the citizen needs to provide information or seek assistance;
- it does not pre-judge whether the statutory threshold is met;
- it clearly distinguishes a Fiosrú complaint under Part 6 from a section 203 statutory referral/investigation.

### National service inventory recheck
Current Garda's Online Services page and sitemap continue to list the core online-service categories:
- Garda Vetting
- Data Protection / FOI / Police Certificates
- Firearms Licensing
- Abnormal Loads
- Online Crime Reporting
- Online Hate Crime Reporting
- National Age Card
- Unclaimed Property
The sitemap additionally exposes roads-policing services such as Traffic Watch, Fixed Charge Notices, Abnormal Loads, and property found in taxis/PSVs and forms.

Sources:
https://www.garda.ie/en/about-us/online-services/
https://www.garda.ie/en/sitemap/

### Routing test additions
29. Death/serious harm after Garda contact → explain statutory framework; do not label citizen action as "s203 referral".
30. Death/serious harm + immediate danger → emergency route first.
31. Death/serious harm, incident concluded, citizen has information → Fiosrú information/contact pathway without asserting statutory qualification.
32. Citizen asks "Can I make a s203 complaint?" → explain that s203 is a statutory referral/investigation mechanism, distinct from an ordinary complaint.

### Data-model requirement
Every specialist route must carry an authority_role field with values such as:
- entry_point
- investigating_body
- resolving_body
- decision_maker
- review_body
- information_contact
This prevents statutory referrals, complaints, applications and information channels from being represented as interchangeable "forms".


## Audit 14 — public-facing vs institutional application boundary (24 September 2026)

### Public CCTV is not a general citizen application
Current Garda Public CCTV guidance confirms that sections 27 and 28 of the Garda Síochána (Recording Devices) Act 2023 provide authorisation routes for Garda personnel and Local Authorities. The published Section 28 application form is for Local Authorities. Community groups can propose schemes through their local authority but do not directly apply for new authorisation under the current regime.

Therefore the citizen engine should classify Public CCTV as:
- institutional / multi-authority route;
- not a general "apply for CCTV" citizen service;
- possible community proposal → local authority / Local Community Safety Partnership pathway;
- legal information → Garda Public CCTV section.

Source: https://www.garda.ie/en/about-us/online-services/public%20cctv/

### National Age Card is a genuine public service but not an identity-card route
Current Garda guidance confirms that the National Age Card is voluntary, for people aged 18+, and solely for proving age. The online application is through the Age Card service, followed by authentication at a local Garda station. It is not an identity card.

Source: https://www.garda.ie/en/about-us/online-services/national-age-card/

### Unclaimed property is a discovery/recovery route, not a replacement for reporting theft
Current Garda guidance says the online unclaimed-property pilot lets members of the public view selected recovered lost/stolen property. If property is stolen, it should still be reported to Gardaí; if an item is not listed, the person should contact the local Garda station.

Source: https://www.garda.ie/en/about-us/online-services/unclaimed-property/

### Core inventory classification rule
Every discovered Garda page/form must first be classified as one of:
1. citizen action;
2. citizen information/self-service;
3. specialist safety/reporting route;
4. institutional/business/professional application;
5. multi-authority route;
6. internal Garda form/process;
7. information-only / background;
8. historical or superseded material.

Only categories 1–5 should normally become visible routing destinations, and categories 4–5 must clearly identify the applicant/authority relationship.

### Current inventory examples
- National Age Card → citizen service.
- Unclaimed Property → citizen self-service/discovery.
- Public CCTV Section 28 form → Local Authority/institutional application.
- Public CCTV community proposal → local authority/community-safety pathway.
- Garda internal CCTV authorisation → internal/institutional, not citizen-facing.
