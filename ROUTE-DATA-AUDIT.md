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
- an official_info_url or populated official_submission_url outside the same front-end official-destination allowlist used for rendered links.

This is a second safety boundary in addition to the repository audit. The renderer also independently filters destinations before creating clickable links. Latest runtime hardening commit: 5b0b0652215079394854be7962cdc8ff61575636.
