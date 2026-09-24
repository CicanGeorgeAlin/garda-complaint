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

