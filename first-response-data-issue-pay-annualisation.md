# First Response playbook — Ravio Data Issue & Pay Annualisation

*Context for the First Response Agent. Use it to (1) reflect back what we already know from the ticket and (2) ask precisely for the missing information that will let Product Support resolve the issue in as few replies as possible. Only ask for what's actually missing.*

This doc covers two request types:
- **Ravio Data Issue** (HubSpot internal value `E2E`)
- **Pay Annualisation** (HubSpot internal value `Data Update`)

---

## A. Ravio Data Issue (`E2E`)

### What it is
Data in the Ravio platform is showing **incorrectly, missing, or not syncing**, with **no clear field-mapping cause** stated. Typical signals: "some salaries showing incorrectly", "missing employees/locations/salaries", "benchmarks not appearing", "data isn't syncing", "employees showing as numbers".

### What we usually already know
- The customer/company and tenant ID (on the ticket).
- A rough description of what looks wrong.

### Information to confirm or request (the checklist)
Ask only for the gaps:
1. **What specifically is wrong or missing** — which data: employees, salaries, locations, variable pay, equity, benchmarks, levels?
2. **A few example records** — employee IDs (or names/emails) that are affected, so we can trace them.
3. **Expected vs actual** — what they currently see vs what they expected to see.
4. **Where in Ravio** they're seeing it — which page/view (a screenshot is ideal).
5. **When it started / did it work before** — and whether a recent HRIS change or sync happened.
6. **Data source** — which HRIS/integration feeds this data (e.g. HiBob, Personio, Workday), if relevant.

### Common underlying causes (for our own steer — don't diagnose to the customer prematurely)
- Sync lag or a stalled integration sync.
- Employees excluded by a filter or employment-status rule.
- A field not being pulled by the integration (borderline with Update Field Mapping — if the fix is clearly "map field X", it's a mapping issue, not this).
- Anonymisation / dataset settings hiding records.

### "Enough context to resolve" signal
If the customer has already given **specific affected records + expected values + where they see it**, Support can investigate straight away — no clarifying email needed; say so in the note.

---

## B. Pay Annualisation (`Data Update`)

### What it is
Part-time and/or contractor salaries are showing **non-annualised** (or need annualising) so that pay is comparable in benchmarking. Signals: "annualisation", "part-time salaries non-annualised", "contractor pay looks too low/high vs market".

### What we usually already know
- The company/tenant.
- That something about part-time/contractor pay looks off.

### Information to confirm or request (the checklist)
1. **Which employees are affected** — example employee IDs (the part-time / contractor records in question).
2. **Their working pattern** — FTE / part-time percentage or contracted hours, if known.
3. **Current vs expected figure** — the salary Ravio is showing vs the correct annualised figure.
4. **Scope** — is this all part-time/contractor employees, or specific individuals?
5. **Source field** — which HRIS field holds FTE / working hours (so we can pick it up).

### Common underlying cause
FTE / working-pattern data isn't provided or mapped, so Ravio can't annualise the salary; or contractor pay is entered as actual rather than annualised.

### "Enough context to resolve" signal
If we have **the affected employee IDs and their FTE/working pattern**, Support can annualise without further questions.

---

## Tone for the drafted reply
Warm, concise, UK English. Acknowledge the ticket, reflect back the useful info already provided, then list the missing items as a short, specific bullet list. Never invent employee IDs, figures, or field names — ask for them. Make clear a human will pick the ticket up; this is a first acknowledgement, not a resolution.
