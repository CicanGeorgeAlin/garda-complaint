# Garda Citizen Access

An independent citizen-navigation website for finding the appropriate official route for Garda, Fiosrú and related public-service matters in the Republic of Ireland.

## What this project does

The website helps a person describe a situation in plain language and identifies a **likely official route** based on the project's audited route data and explicit verification states.

It is a navigation and explanation layer only. It does **not**:

- act as An Garda Síochána or Fiosrú;
- submit complaints, crime reports, applications or information requests;
- determine whether a legal threshold has been met;
- replace official forms, procedures or legal advice.

Where the routing engine cannot safely distinguish between routes, it deliberately asks the citizen to use the official service directory or obtain further assistance rather than guessing.

## Safety principles

- Emergency screening comes before ordinary routing.
- Online crime reporting is not treated as universal.
- Specialist services are separated from general crime reporting.
- Fiosrú complaints, Fiosrú statutory reviews and Garda prosecution-decision reviews are treated as different processes.
- FOI, AIE and personal-data access are distinct routes.
- Applications and permits are not treated as complaints.
- Conflicting official information is preserved rather than silently resolved.
- Official destinations are restricted by an allowlist in the frontend.

## Repository structure

- `index.html` — public interface and client-side routing logic.
- `routes.json` — structured official-route registry.
- `ROUTING-TESTS.md` — routing regression and safety tests.
- `ROUTE-DATA-AUDIT.md` — structural and destination-integrity audit.
- `OFFICIAL-SERVICE-INVENTORY.md` — detailed service/source working inventory.
- `LEGAL-SOURCE-MAP.md` — legislation and official-source mapping.

## Current route registry

The route registry currently contains **41 route records** with unique route IDs.

The project uses conservative matching: an ambiguous question should remain unresolved rather than being sent to an inappropriate official service.

## Maintenance

Official public-service pages and legal information can change. A clean structural audit does not prove that every linked page remains unchanged or continuously available.

Before publishing or relying on a route for a high-stakes matter, re-check the current official source and any applicable deadline or eligibility condition.



### Source conflicts and route notes

The registry distinguishes documented differences between official sources from other important route caveats. Routes with a genuine documented source conflict carry `source_conflict: true` and `verification_status: verified_current_with_conflict`. Other `conflict_note` text is displayed as an important route note and must not be interpreted as evidence that official sources disagree.
