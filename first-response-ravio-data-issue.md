# First response playbook: Ravio Data Issue

Request type: **Ravio Data Issue** (HubSpot internal value `E2E`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer will read the email you draft. Your job is to recognise what we already know, then ask only for what is missing, so Product Support can investigate straight away.

## How to use this playbook

- Decide first whether the ticket already has enough to act on (see "Enough context to resolve"). If it does, do not draft an email.
- Work out **which symptom** the customer means before asking anything. This type is broad, so the right questions depend on the scenario (see "Extra questions by scenario").
- Ask only for items that are genuinely missing. Group them into one short list. Five questions is a sensible ceiling.
- Always ask for **employee IDs (or employee numbers), not names**.
- One issue per ticket. These emails often bundle several asks (levels, exclusions, a framework upload). Focus on the data issue and suggest raising the others separately.
- Never diagnose the cause, never admit fault, never give a timeline.
- Write in UK English. No em dashes. Plain language.

## What this request type covers

Data in Ravio that **doesn't match the customer's HRIS (Human Resources Information System)** or what they expect, other than salary scaling. The most common symptoms:

- **Missing employees** or a headcount that looks too low.
- **Leavers still showing.**
- **Wrong or blank values**: job title, department, location, level, manager, employment type.
- **Data that looks out of date** after a change in the HRIS.
- **People showing as numbers or anonymous** instead of names.
- **Salary missing entirely** (blank, rather than the wrong amount).

## When it's really a different request type

Note this in your reasoning and keep your questions relevant.

- **Salary present but the wrong amount** (part-time, monthly vs annual, holiday allowance): Pay Annualisation.
- **They ask us to use a different HRIS field**: Update Field Mapping.
- **They want to hide or show a group**: Exclusions.
- **They want a specific value changed on Ravio's side**: Overrides.
- **The same person appears twice**: Duplicates.
- **The Ravio level itself** (the levelling decision, not a missing level field): levelling, handled by the Business Operations team.
- **Bonus or commission**: Variable Pay.

## What we usually already know (don't ask for these)

- The company and tenant.
- Which HRIS they use and whether it's an integration or manual upload.
- A rough description, often forwarded by their Customer Success Manager.

## Information we need

### Must have

1. **What exactly looks wrong or missing.** The field (job title, department, location, level, manager, employment status), or which people are missing.
   - Ask: "Which information looks wrong or missing, for example job titles, locations, levels, or particular employees?"
2. **Two or three example employee IDs**, each with **what Ravio shows and what their HRIS shows**. This is the most common blocker on these tickets. We can't trace a problem without specific records.
   - Ask: "Could you share two or three employee IDs as examples, with what you see in Ravio and what your HR system shows for them?"
3. **Who is affected (scope).** Specific people, a group (a country, department, new starters, contractors), or everyone.
   - Ask: "Is this affecting everyone, or a particular group such as one country, one department, or new starters?"
4. **If they changed something in the HRIS recently: when, and whether the change has a future effective date.** Changes with a future effective date won't show in Ravio until that date.
   - Ask: "When was the change made in your HR system, and is it effective now or from a future date?"

### Helpful if missing

5. **The HRIS field that holds the correct information** (the field name as it appears in their HR system). Naming it often solves the problem quickly.
   - Ask: "Which field in your HR system holds this information?"
6. **Whether this is new or has always been the case**, and anything that changed around then (new fields, reorganised data, permission changes, reconnecting the integration).
   - Ask: "Did this look right before? If so, did anything change in your HR system around the time it stopped?"
7. **Where in Ravio they see it** (which page or view), ideally with a screenshot with names blurred.
8. **Expected headcount**, if people are missing.

### Extra questions by scenario

- **Missing employees:** for two or three missing people ask for their employee IDs, their status in the HRIS (active, on leave, not yet started), their start date and their employment type. Also ask roughly how many people they expect to see. Contractors, interns and people who haven't started yet are often hidden by design, so the answers tell us quickly whether anything is actually wrong.
- **Leavers still showing:** ask for one or two employee IDs and their leaving dates.
- **Wrong location, department or job title:** ask for example IDs with the value they expect, and whether one rule applies to everyone (for example "everyone in 'United Kingdom' should be London").
- **Wrong or missing level:** ask which HRIS field holds level, and whether level and track (for example manager or individual contributor) sit in one field or two.
- **Data out of date:** ask what changed, when, and one example employee ID.
- **Names showing as numbers:** ask for one example ID and when they first noticed.

## Enough context to resolve

Don't draft an email when the ticket already includes:

- the specific field, or the specific missing people,
- at least one **employee ID with the Ravio value and the HRIS value** (for missing people: IDs plus their HRIS status),
- the scope,
- and, if they changed something in the HRIS, when it was changed or becomes effective.

## Customer-facing guidance

### Safe to say

These are documented behaviours. Save them for later replies unless they directly answer the question:

- Leavers stay visible in Ravio for two weeks after their leaving date.
- Contractors and interns are hidden by default for most accounts.
- Your HR system is the source of truth. Where the data is wrong at source, updating it there is the most reliable fix.

### Never say or promise

- Any cause ("your data refresh is blocked", "your mapping broke").
- That the issue is our fault, or that it's fixed.
- A date or timeframe.
- That Ravio will change data in their HR system. We never edit their HRIS.
- That we'll manually change values on our side. That's a last resort and won't update when their HRIS changes.
- That reconnecting or re-syncing the integration themselves will fix it. Don't suggest they reconnect unless Product Support asks.
- Internal names: tools, databases, pipelines, dashboards or internal field names.

### Privacy

Ask for employee IDs rather than names. Don't ask for exported lists of employees or salaries. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- Which information looks wrong or missing (for example job titles or particular employees)
- Two or three employee IDs, with what Ravio shows and what your HR system shows for each
- Whether this affects everyone or a particular group
- If you changed something in your HR system recently, when it was changed and whether it's effective yet
