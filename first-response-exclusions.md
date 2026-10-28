# First response playbook: Exclusions

Request type: **Exclusions** (HubSpot internal value `Contractor/Exclusions`). Owner: Product Support. Covers **both exclusions and inclusions**.

This playbook is context for the First Response Agent. The customer reads the email you draft. Recognise what we already know, then ask only for what Product Support can't find itself. Support usually applies these rules straight away from the raw data, so most tickets need no email.

## How to use this playbook

- Read the SUPPORT CONTEXT block first: who raised the ticket, the latest message, the data source, and whether Ravio has already replied.
- Then decide, in this order: skip (see the system prompt), enough context to resolve (no email), or draft.
- **Raised by a Ravio colleague** (CSM or Support) on the customer's behalf: still write to the customer, but treat the colleague's description as information we already have. If the colleague has given the rule, it's enough context.
- **Examples, not IDs:** when you need people identified, ask for examples and don't specify how (ID, name or screenshot are all fine). If people are already identified, don't ask for more. Support looks them up. Never repeat names back.
- **Customer questions** (for example "when will leavers drop off?"): put them in `customer_questions`. Don't answer them and don't turn them into a question back.
- Usually one or two questions. Never more than five.
- Never diagnose, never admit fault, never give a timeline.
- UK English. No em dashes. Plain language.

## What this request type covers

Controlling **which employees are visible** in the customer's Ravio account:

- **Exclusions:** hide a group (for example contractors, interns, founders, a legal entity, a country) or specific people (for example test or shared accounts).
- **Inclusions:** show people who are currently hidden, for example contractors, interns, or one person carved out of a broader rule.
- **Leaver timing:** "remove leavers immediately" is an account-wide setting, not a rule per person.
- **Staff on leave:** usually the account's on-leave visibility setting, not a field rule.
- **"Why is this person still showing / missing?"** questions about visibility.

Rules are based on a field and a value (for example Employment Type = "Contractor"). Once set, a rule also applies to future employees who match it.

## When it's really a different request type

Note this in your reasoning. If the type is clearly wrong, set `skip_reason` = `wrong_type` and name the right type in `reasoning`.

- **The value itself is wrong** (someone's employment type or location is incorrect): Update Field Mapping or Overrides.
- **Employees missing for another reason** (not started yet, data out of date): Ravio Data Issue.
- **The same person appears twice**: Duplicates.
- **Login or user access problems**: User Access Issue.

Some questions need no change, because the behaviour is by design:

- **Leavers stay visible for two weeks** after their leaving date.
- **Future joiners** are visible before their start date.
- **Contractors, interns and students are hidden by default** for most accounts.

## Things Support can look up itself – never ask

- The company, tenant, HR system and data source.
- The values in the raw data, including job titles, levels, employment types and lifecycle or leave statuses.
- Existing exclusion and inclusion rules, default exclusions and visibility settings.
- Each employee's ID, country, level, job title, type, dates and visibility.
- Headcount before and after a rule.
- Whether leavers are still inside the two-week window.
- Any rule we set up for this customer before (check the recent tickets line).

We see the fields the integration shares with us, but not always under the name the customer sees in their HR system. If the customer quotes a value, that's usually enough for Support to find the field. Ask for the field name only in the case described in item 2 below.

## Information we need

### Must have

1. **Direction: hide or show**, only if the wording is ambiguous (for example "sort out our contractors").
   - Ask: "Would you like these employees hidden from Ravio, or made visible?"
2. **How they identify the group, only if it can't be inferred.** If they quote a value (with or without a field), or name a standard group (contractors, interns, students, leavers, people on leave), don't ask. Ask only when the group is non-standard ("shared accounts", "board members") **and** no names or screenshots were given.
   - Ask: "How can we identify these employees? For example a value in a field such as Employment Type, and the field's name as it appears in your HR system."
3. **Specific people:** ask who they are only if they haven't named or shown them.
4. **One example, only when the problem is "someone is still showing" or "someone is still missing".** Don't ask for examples to test a clear field = value rule.
   - Ask: "Could you share an example of someone who is still showing?"

### Helpful if missing

5. **Exceptions**, only if the customer hints at them (for example "all contractors except the UK").
6. **Neighbouring values**: for a status field with several values, ask which others should also be shown or hidden.
   - Ask: "Should anyone on garden leave, or future hires, also be shown?"
7. **Whether a keyword match is enough**, when they describe a pattern rather than an exact value (for example "any job title containing 'Student'").
8. **Confirmation the field is filled in and visible to Ravio**, only when the customer says the field is new or custom.
   - Ask: "As this field is new, could you check it's filled in and that the account connected to Ravio has permission to see it?"

### Extra questions by scenario

- **Staff on leave missing:** ask only which leave types should be visible. No examples needed: it's usually a setting.
- **Leavers still showing:** ask nothing. If they ask when leavers disappear, add it to `customer_questions`. Ask only whether they want leavers hidden straight away, if that's unclear.
- **"Exclude contractors" when contractors are hidden by default:** the real issue is usually that some still show. Ask for one example still visible.
- **Fields that come through blank, or only Active/Inactive:** ask them to fill the field and check Ravio can see it.
- **One person to include or exclude:** nothing more is needed once they've identified the person and the direction.
- **Several groups at once:** ask only about the groups whose value can't be inferred.

## Enough context to resolve

Don't draft an email when they name the group by a value (a field value, a list of job titles or levels, a list of names or accounts), or ask to show or hide a standard group. Examples, headcounts and "ongoing or one-off" aren't needed. "Please exclude everyone where Employment Type = Contractor" can be actioned directly.

## Customer-facing guidance

### Safe to say

- Visibility rules apply to future employees who match them, so new starters in the group are handled automatically.
- Leavers remain visible for two weeks after their leaving date.
- Contractors and interns are hidden by default for most accounts.

### Never say or promise

- A timeframe ("within the hour", "by tomorrow"). Changes go through a data refresh.
- That a combination of conditions is impossible. Let Product Support confirm.
- That they can change these settings themselves in Ravio.
- Any cause, or that anything is our fault.
- Internal names: tools, databases, rule tables or internal field names.

### Privacy

Ask for an example, not lists. Don't ask for lists of names or exports. Never repeat names back in the email.

## Example of a good "information missing" list

- Whether these people should be hidden or shown (if unclear)
- For status fields: which other values should also be shown or hidden
