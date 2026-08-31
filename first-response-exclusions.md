# First Response playbook — Exclusions

*Context for the First Response Agent. Use it to reflect back what we already know and ask precisely for the missing information needed to apply the exclusion/inclusion, in as few replies as possible. Only ask for what's actually missing.*

Request type: **Exclusions** (HubSpot internal value `Contractor/Exclusions`).

---

## What it is
A request to **include or exclude specific employees, groups, levels, employment types, or termination types** from the customer's Ravio data / benchmarking. Signals: "exclude contractors/externals", "include Fixed term contract and EOR", "remove 'gardening leave' from termination types", "include E1/E2", "don't count interns".

## What we usually already know
- The company/tenant.
- A rough statement of who or what they want in or out.

## Information to confirm or request (the checklist)
Ask only for the gaps:
1. **What to include or exclude** — the exact employees, groups, employment types, termination types, levels, or locations.
2. **The rule / criteria** — which **HRIS field** and **value** defines the group (e.g. `Contract = Freelancer`, `employment_type = EOR`, `worker_type = Contractor`, termination reason = "Gardening leave"). This is the single most useful thing to pin down.
3. **A few example employee IDs** that match the rule, so we can verify it behaves as expected.
4. **Direction / scope** — should they be excluded from **benchmarking**, from the **dataset entirely**, or included where currently excluded?
5. **Persistence** — should this apply **automatically to all future employees** who match the criteria, or is it a **one-off** for the current data?

## Common patterns (from real tickets — for our own steer)
- Exclude **contractors / externals / freelancers** so they don't skew benchmarks.
- Exclude specific **termination types** (e.g. gardening leave, notice period) from active headcount.
- **Include** groups currently filtered out — e.g. "Fixed term contract" and "EOR" employees.
- Exclusions are typically implemented as a rule against an HRIS field value, and can be set to apply to future joiners too.

## "Enough context to resolve" signal
If the customer has given a **clear criterion (field + value)**, the **scope** (benchmarking vs dataset), and whether it's **ongoing or one-off** — ideally with an example ID or two — Support can apply it without further questions. Say so in the note.

## Tone for the drafted reply
Warm, concise, UK English. Acknowledge the request, reflect back the rule as you understand it, and confirm the missing specifics as a short bullet list. Never invent field names, values, or employee IDs — ask for them. Make clear a human will action it; this is a first acknowledgement, not a confirmation that the exclusion is done.
