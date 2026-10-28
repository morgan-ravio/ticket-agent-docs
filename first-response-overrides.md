# First response playbook: Overrides

Request type: **Overrides** (HubSpot internal value `Overrides`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer reads the email you draft. Recognise what we already know, then ask only for what Product Support can't find itself.

An override means: "when a field has value X, show Y in Ravio instead". It sits on Ravio's side, so it **doesn't update when the customer later fixes their HR system**. That's why we use it only when the data can't be fixed at source or by reading a different field.

Note: **Override Threshold Breach** tickets are internal alerts, not customer requests. Never draft a customer email for them.

## How to use this playbook

- Read the SUPPORT CONTEXT block first: who raised the ticket, the latest message, the data source, and whether Ravio has already replied.
- Then decide, in this order: skip (see the system prompt), enough context to resolve (no email), or draft.
- **Raised by a Ravio colleague** (most Overrides tickets are): still write to the customer, but treat the colleague's instruction as information we already have. Never turn it into a question back. If the colleague wrote "remove the overrides", don't ask "which overrides would you like removed?". A complete instruction from a colleague is enough context: no email.
- **Examples, not IDs:** when you need people identified, ask for examples and don't specify how (ID, name or screenshot are all fine). If people are already named, don't ask. Support finds them. Never repeat names back.
- **Customer questions** (for example "why is this showing USA?"): put them in `customer_questions`. Don't answer them and don't turn them into a question back.
- Usually two or three questions. Never more than five.
- Never diagnose, never admit fault, never give a timeline.
- UK English. No em dashes. Plain language.

## What this request type covers

- **Changing a value**, for one person, a list of people, or everyone with a given value. Common examples:
  - location (for example "everyone in 'Netherlands' should show as Amsterdam", or "'Remote – Germany' should show as Germany"),
  - FTE (full-time equivalent) or salary inputs for specific employees,
  - a default for blank values (for example a currency where none is set),
  - a single person's job title.
- **Removing existing overrides**, for example after the customer has fixed their HR system or added a new field.

## When it's really a different request type

Note this in your reasoning. If the type is clearly wrong, set `skip_reason` = `wrong_type` and name the right type in `reasoning`.

- **The correct value already exists in another field**: Update Field Mapping. This is often the better fix.
- **Hiding or showing people**: Exclusions.
- **Salary scaling for part-timers, pay periods or holiday allowance**: Pay Annualisation.
- **Unexpected level or position overrides** ("hundreds of overrides we didn't set", people stuck on old levels after a framework change): levelling, not data adjustments. Ask nothing; usually no email.
- **Job titles mapping to the wrong Ravio position**: role mapping or the correlation table.
- **An error message or the app not working**: a bug. Ask only for the steps, the page and a screenshot. Never ask for console logs.
- **Data wrong for an unknown reason**: Ravio Data Issue.

## Things Support can look up itself – never ask

- The company, tenant, HR system and data source.
- **The value currently in Ravio** for any field and employee. Support copies the exact current value itself.
- Current location, country, job title, level, FTE, salary and currency for any employee.
- Existing overrides and what they change.
- Employee IDs for people the customer has named.
- Which field we currently read, and earlier adjustments for this customer (check the recent tickets line).

## Information we need

### Must have

1. **Which field is wrong in Ravio**, in plain terms, if it isn't clear.
   - Ask: "Which information is showing incorrectly in Ravio?"
2. **The value it should be.** We can see the current value. For locations, a country is enough for country-level benchmarking. Ask for a city only if they named an ambiguous city, or want city-level benchmarking without saying which city.
   - Ask: "What should it show instead?"
3. **Who it applies to**, if it isn't clear: specific people (examples, unless already named) or everyone who has a particular value.
   - Ask: "Should this apply to specific employees, or to everyone who currently shows that value?"
4. **Whether the value can be corrected in their HR system.** Only ask if the ticket gives no sign either way. Skip if they've said it must stay as it is (tied to payroll, or a contractor platform such as Deel).
   - Ask: "Is the value correct in your HR system? If not, would you be able to update it there, or does it need to stay as it is?"
5. **For removals: which adjustments to remove.** Skip if they or a colleague have already said.
   - Ask: "Which adjustments would you like removed: all of them, those for a particular field, or those for specific employees?"

### Helpful if missing

6. **Whether it's temporary**, for example until they update their HR system next quarter.
7. **Whether the rule should also apply to future employees** with the same value (rule-based requests only, and only if unclear).
8. **For FTE or salary inputs:** the FTE % or hours, and whether the figure is monthly or annual, if not given.

### Extra questions by scenario

- **Location:** ask for the target country (and a city only if needed) and whether it applies to everyone with that value. Ask whether the field is reliable for everyone only for rule-based requests.
- **Single person's value:** who the person is (if not already given), the field and the target value.
- **"The adjustment isn't working":** ask for one example where it's not showing correctly, if none given.
- **Removal after an HR system fix:** ask which field was fixed, if not given.

## Enough context to resolve

Don't draft an email when the ticket has the field and the desired value, plus who it applies to (named people, examples or "everyone with value X"). For rule-based requests, there should be no open question about fixing the HR system instead. For removals: a clear statement of which adjustments to remove. Also don't draft for unexplained level or position overrides.

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

Ask for examples, not lists. Don't ask for exported lists of employees with salaries. Never repeat names back in the email.

## Example of a good "information missing" list

- What it should show instead (for locations, the country, or the city and country for city level)
- Whether this applies to specific employees or everyone with that value
