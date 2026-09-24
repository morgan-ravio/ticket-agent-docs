# First response playbook: Exclusions

Request type: **Exclusions** (HubSpot internal value `Contractor/Exclusions`). Owner: Product Support. Covers **both exclusions and inclusions**.

This playbook is context for the First Response Agent. The customer will read the email you draft. Your job is to recognise what we already know, then ask only for what is missing, so Product Support can set up the right visibility rule first time.

## How to use this playbook

- Decide first whether the ticket already has enough to act on (see "Enough context to resolve"). If it does, do not draft an email.
- Ask only for items that are genuinely missing. Group them into one short list. Five questions is a sensible ceiling.
- Always ask for **employee IDs (or employee numbers), not names**. Names can change and don't match reliably. We also avoid handling personal data we don't need.
- One issue per ticket. If the email also raises unrelated topics, focus on the visibility request and suggest raising the others separately.
- Never diagnose, never admit fault, never give a timeline.
- Write in UK English. No em dashes. Plain language.

## What this request type covers

Controlling **which employees are visible** in the customer's Ravio account:

- **Exclusions:** hide a group (for example contractors, interns, founders, a legal entity, a country) or specific people (for example test or shared accounts).
- **Inclusions:** show people who are currently hidden, for example contractors, interns, or staff on parental leave, or one person carved out of a broader rule.
- **"Why is this person still showing / missing?"** questions about visibility.

Rules are based on a field in their HRIS (Human Resources Information System) and a value in it (for example Employment Type = "Contractor"). Once set, a rule also applies to future employees who match it.

## When it's really a different request type

Note this in your reasoning and keep your questions relevant.

- **The value itself is wrong** (for example someone's employment type or location is incorrect): Update Field Mapping or Overrides.
- **Employees are missing for another reason** (not started yet, data out of date): Ravio Data Issue.
- **The same person appears twice**: Duplicates.

Some questions need no change at all, because the behaviour is by design:

- **Leavers stay visible for two weeks** after their leaving date.
- **Future joiners** are visible before their start date.
- **Contractors, interns and students are hidden by default** for most accounts, even when the customer hasn't set a rule.

If the ticket is only asking why one of these is happening, a short explanation may be all that's needed. Still check which employees they mean.

## What we usually already know (don't ask for these)

- The company and tenant, and which HRIS they use.
- A rough statement of who should be hidden or shown.

## Information we need

### Must have

1. **Direction: hide or show.** Usually clear, but confirm if the wording is ambiguous (for example "sort out our contractors").
   - Ask: "Would you like these employees hidden from Ravio, or made visible?"
2. **The HRIS field and exact value that identifies the group.** This is the most common blocker. Customers often name a field that turns out to be empty, holds a different value, or isn't visible to Ravio. Values must match exactly as they appear in the HRIS, including local-language values (for example "Stagiaire", "Aushilfe").
   - Ask: "Which field in your HR system identifies these employees, and what exact value does it show? For example 'Contractor' in the Employment Type field."
3. **Whether it's the whole group or specific people.** For specific people, ask for employee IDs.
   - Ask: "Should this apply to everyone with that value, or only specific people? If it's specific people, please share their employee IDs rather than names."
4. **Two or three example employees** who are wrongly visible or hidden now, by employee ID. We use these to find the right field and test the rule.
   - Ask: "Could you share two or three employee IDs for people this should apply to?"

### Helpful if missing

5. **Any exceptions.** For example "all contractors except those in the UK", or "exclude contractors but keep this one person who manages a team".
   - Ask: "Are there any exceptions, for example a country or a person who should stay visible?"
6. **Whether a keyword match is enough**, when they describe a pattern rather than an exact value (for example "any job title containing 'Student'").
7. **Roughly how many employees should remain visible afterwards.** This helps us sanity-check the rule before applying it.
   - Ask: "Roughly how many employees would you expect to see once this is in place?"
8. **Confirmation the field is filled in and shared with Ravio.** Some HR systems restrict fields like contract type by default.
   - Ask: "Could you check this field is filled in for these employees, and that the account connected to Ravio has permission to see it?"
9. **A screenshot** of the field on one employee's HRIS record, with the name blurred.

### Extra questions by scenario

- **Staff on leave missing:** ask which leave types (for example parental leave) should be visible, plus one example employee ID.
- **Leavers still showing:** ask for one or two example employee IDs and their leaving dates, and whether they want them hidden before the standard two weeks.
- **One person to include or exclude:** only the employee ID and direction are needed.
- **Several criteria at once** (for example contractors and interns in two countries): ask them to list each group with its field and value, plus any exceptions.

## Enough context to resolve

Don't draft an email when the ticket already includes:

- the direction (hide or show),
- the HRIS field and exact value(s), or the specific employee IDs,
- the scope and any exceptions,
- and ideally one example employee.

Tickets like "Please exclude everyone where Employment Type = Contractor" can be actioned directly.

## Customer-facing guidance

### Safe to say

- Visibility rules apply to future employees who match them, so new starters in the group are handled automatically.
- Leavers remain visible for two weeks after their leaving date.
- Contractors and interns are hidden by default for most accounts.

### Never say or promise

- A timeframe ("within the hour", "by tomorrow"). Changes go through a data refresh.
- That a combination of conditions is impossible. There are workarounds, so let Product Support confirm.
- That they can change these settings themselves in Ravio.
- Any cause, or that anything is our fault.
- Internal names: tools, databases, rule tables or internal field names.

### Privacy

Ask for employee IDs, not names or work emails. Don't ask for lists of names. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- Whether these employees should be hidden or made visible
- The field in your HR system that identifies them, and the exact value it shows (for example Employment Type = "Contractor")
- Whether this applies to everyone with that value, or specific people (employee IDs please)
- Two or three example employee IDs, plus any exceptions
