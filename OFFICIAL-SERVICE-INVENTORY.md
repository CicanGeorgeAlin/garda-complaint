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

