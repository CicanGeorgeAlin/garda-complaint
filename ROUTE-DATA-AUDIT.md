# Route Data Integrity Audit

Verified against the `main` branch on 24 September 2026.

## Results

- Route records: **41**
- Duplicate `route_id` values: **0**
- Route URLs outside the site's approved official-domain set: **0**
- Every populated route destination is on an approved official domain or an emergency `tel:`/`sms:` destination.

## Approved destination domains

- garda.ie
- fiosru.ie
- irishstatutebook.ie
- vetting.garda.ie
- agecard.ie
- emergency telephone/SMS destinations where applicable

## Important limitation

This audit verifies the **structure and destination-domain integrity** of the route database. It does not by itself prove that every page is currently reachable or that every official page remains substantively unchanged. Current legal/service claims require periodic source re-verification.

## Design rule

A route should never gain an arbitrary external destination merely because a URL was added to the JSON database. The front-end link layer independently applies its official-domain allowlist.
