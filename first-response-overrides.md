# First response playbook: Overrides

Request type: **Overrides** (HubSpot internal value `Overrides`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer will read the email you draft. Your job is to recognise what we already know, then ask only for what is missing, so Product Support can make the adjustment correctly.

An override means: "when a field has value X, show Y in Ravio instead". It sits on Ravio's side, so it **doesn't update when the customer later fixes their HRIS (Human Resources Information System)**. That's why we only use it when the data can't be fixed at source or by changing which HRIS field we read.

Note: **Override Threshold Breach** tickets are internal alerts, not customer requests. Never draft a customer email for them.

## How to use this playbook

- Decide first whether the ticket already has enough to act on (see "Enough context to resolve"). If it does, do not draft an email.
- Ask only for items that are genuinely missing. Group them into one short list. Five questions is a sensible ceiling.
- Always ask for **employee IDs (or employee numbers), not names**.
- One issue per ticket.
- Never diagnose, never admit fault, never give a timeline.
- Write in UK English. No em dashes. Plain language.

## What this request type covers

- **Changing a value**, for one person, a list of people, or everyone with a given value. Common examples:
  - location (for example "everyone in 'Netherlands' should show as Amsterdam", or "'Remote – Germany' should show as Germany"),
  - FTE (full-time equivalent) or salary inputs for specific employees,
  - a default for blank values (for example a currency where none is set),
  - a single person's job title.
- **Removing existing overrides**, for example after the customer has fixed their HRIS or added a new field.

## When it's really a different request type

Note this in your reasoning and keep your questions relevant.

- **The correct value already exists in another HRIS field**: Update Field Mapping. This is often the better fix.
- **Hiding or showing people**: Exclusions.
- **Salary scaling for part-timers, pay periods or holiday allowance**: Pay Annualisation.
- **Changes to how roles map to Ravio levels** (the levelling framework): a correlation table change, handled by the Business Operations team.
- **Data wrong for an unknown reason**: Ravio Data Issue.

## What we usually already know (don't ask for these)

- The company and tenant, and which HRIS they use.
- Roughly which field they're unhappy with.

## Information we need

### Must have

1. **Which field is wrong in Ravio**, in plain terms (location, FTE, salary, currency, job title, employment type and so on).
   - Ask: "Which information is showing incorrectly in Ravio?"
2. **The current value and the value it should be.** Exact wording matters, because we match values exactly. For locations, ask for the full city and country (a city name can exist in more than one country).
   - Ask: "What does it show now, and what should it show instead? For locations, please give the city and country."
3. **Who it applies to.** Specific people (employee IDs), or everyone who has a particular value.
   - Ask: "Should this apply to specific employees (please share their employee IDs) or to everyone who currently shows that value?"
4. **Whether the value can be corrected in their HRIS.** If the HRIS is wrong and can be fixed, that's the most reliable route. If the HRIS is right, a different field may be the answer.
   - Ask: "Is the value correct in your HR system? If not, would you be able to update it there, or is there a reason it needs to stay as it is?"
5. **For removals: which adjustments to remove.** All of them, a particular field (for example all location adjustments), or specific employees.
   - Ask: "Which adjustments would you like removed: all of them, those for a particular field, or those for specific employees?"

### Helpful if missing

6. **Why the HRIS can't hold the right value** (for example it's tied to payroll, or the field doesn't exist). This helps us choose the right fix.
7. **Whether it's temporary**, for example until they update their HRIS next quarter.
   - Ask: "Is this a permanent change, or a temporary fix until your HR system is updated?"
8. **Whether the rule should also apply to future employees** with the same value (for rule-based requests).
9. **For FTE or salary inputs:** the FTE % or hours, and whether the figure is monthly or annual.
10. **A screenshot** of the HRIS value next to what Ravio shows, with names blurred.

### Extra questions by scenario

- **Location:** confirm the current value, the target city and country, and whether it applies to everyone with that value. Also ask whether the HRIS field is reliable for everyone, because values like "Remote" or "TBC" may need their own handling.
- **Single person's value:** employee ID, field, current value and target value.
- **"The adjustment isn't working":** ask for an employee ID where it's not showing correctly, and what they see.
- **Removal after an HRIS fix:** ask which field was fixed in the HRIS, so we remove the right adjustments.

## Enough context to resolve

Don't draft an email when the ticket already includes:

- the field, the current value and the desired value,
- the scope (employee IDs, or "everyone with value X"),
- and why it can't be fixed in the HRIS, or clear confirmation it can't.

For removals: a clear statement of which adjustments to remove.

## Customer-facing guidance

### Safe to say

- A manual adjustment on our side won't pick up later changes in your HR system. If you correct the data there later, let us know and we'll remove the adjustment.
- Where possible, fixing the value in your HR system is the most reliable option, because Ravio always reflects it.

### Never say or promise

- That an override is the default or best fix.
- A date or timeframe.
- That any field can be adjusted. Some (for example variable pay) need extra work and may not be possible.
- Any cause, or that anything is our fault.
- Internal names: tools, databases, tables, "processed fields" or internal field names.

### Privacy

Ask for employee IDs rather than names. Don't ask for exported lists of employees with salaries. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- Which information is showing incorrectly in Ravio
- What it shows now and what it should show instead (for locations, the city and country)
- Whether this applies to specific employees (employee IDs please) or everyone with that value
- Whether the value can be corrected in your HR system, or needs to stay as it is
