# First response playbook: Ravio Data Issue

Request type: **Ravio Data Issue** (HubSpot internal value `E2E`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer reads the email you draft. Recognise what we already know, then ask only for what Product Support can't find itself. Support usually solves these from Ravio and the raw data, so keep questions to the minimum.

## How to use this playbook

- Read the SUPPORT CONTEXT block first: who raised the ticket, the latest message, the data source, and whether Ravio has already replied.
- Then decide, in this order: skip (see the system prompt), enough context to resolve (no email), or draft.
- **Follow-ups and live conversations:** if this is a follow-up or reopened issue, or a Ravio colleague has already asked the customer something, don't draft (`skip_reason` = `existing_thread`).
- **Raised by a Ravio colleague** (CSM or Support) on the customer's behalf: still write to the customer, but treat the colleague's description as information we already have. Never ask the customer for something the colleague already gave.
- Work out **which symptom** the customer means before asking anything (see "Extra questions by scenario").
- **Examples, not IDs:** if nobody is identified, ask for one or two examples. Don't specify how to identify people (ID, name or screenshot are all fine). If people are already identified, don't ask for more. Support looks them up. Never repeat names back.
- **Customer questions**: put them in `customer_questions`. Don't answer them and don't turn them into a question back.
- Two or three questions is normal; never more than four. If the customer is frustrated or the issue has been open a long time, ask one at most, or none.
- Match the data source. For manual upload say "the file you uploaded", for SFTP "the file you send us", and only say "your HR system" for integrations.
- Never diagnose the cause, never admit fault, never give a timeline.
- UK English. No em dashes. Plain language.

## What this request type covers

Data in Ravio that **doesn't match the customer's HR system** or what they expect, other than salary scaling:

- **Missing employees** or a headcount that looks too low.
- **Wrong or blank values**: job title, department, location, level, manager, employment type.
- **Data that looks out of date** after a change in the HR system.
- **People showing as numbers or anonymous** instead of names.
- **Salary missing entirely** (blank, rather than the wrong amount).
- **Benchmark or band problems caused by data** ("no market target", "not in a band", missing benchmark): Support investigates from Ravio. At most ask which employees, if none are identified.
- **Almost everyone missing, or nothing updating**: an account-level problem Support checks first. Ask nothing per employee.

## When it's really a different request type

Note this in your reasoning and keep your questions relevant. If the type is clearly wrong, set `skip_reason` = `wrong_type` and name the right type in `reasoning`.

- **Salary present but the wrong amount** (part-time, monthly vs annual, holiday allowance), or "make them full-time like before": Pay Annualisation.
- **They ask us to read a different HR system field**: Update Field Mapping.
- **They want to hide or show a group**: Exclusions.
- **They want a specific value changed on Ravio's side**: Overrides.
- **The same person appears twice**: Duplicates.
- **The Ravio level itself** (the levelling decision, not a missing level field): levelling.
- **Bonus or commission**: Variable Pay.
- **Turning a module on or off** (pay equity, gender data): not a data issue.
- If the SUPPORT CONTEXT shows a different **suggested request type**, consider it and say so in `reasoning`.

## Things Support can look up itself – never ask

- The company, tenant, HR system and data source (integration, SFTP or manual upload).
- Everything Ravio shows for an employee: job title, level, Ravio position and level, location, country, department, salary, band, market target, employment type, dates, and status as received.
- Headcount and who is visible or hidden.
- Whether the integration is connected, when it last synced, and whether data is blocked.
- Existing exclusions and field mappings, and previous tickets for this customer.
- The fields the integration shares with us and their values. Once we have an example, Support can find which field holds a value.
- Files and screenshots already attached.

## Information we need

### Must have

1. **What exactly looks wrong or missing**, if it isn't clear: the field, or which people are missing.
   - Ask: "Which information looks wrong or missing, for example job titles, locations, levels, or particular employees?"
2. **One or two affected people and the value they expect**, only if nobody is identified. Any way of identifying them is fine. We can see what Ravio shows.
   - Ask: "Could you share one or two examples, and what you'd expect to see for each?"
3. **Who is affected (scope)**, only if it matters and is unclear. Skip if they've given a rule ("everyone in Greater London") or an example.
   - Ask: "Is this affecting everyone, or a particular group such as one country or department?"
4. **If they changed something recently: when, and whether it has a future effective date.**
   - Ask: "If you changed this recently, when was it changed and is it effective now or from a future date?"

### Helpful if missing

5. **The field that holds the correct information.** Only for SFTP or manual-upload customers, or if they say it's a custom field. We see the integration's fields, but not always under the name the customer sees, so if they mention a field we can't place, ask for its name as it appears in their HR system or file.
6. **Where in Ravio they see it** (which page or view), if it isn't clear, ideally with a screenshot with names blurred.
7. **Expected headcount**: only if they report a count mismatch without giving numbers.

### Extra questions by scenario

- **A few named people missing:** ask nothing. Support checks status, start date, type and exclusions. Not identified: ask for one or two examples. HiBob customers only: it's fine to ask whether they're on leave.
- **Almost everyone missing, or nothing updating:** ask nothing.
- **Wrong location, department or job title:** ask for one example with the value they expect (if none given), and whether one rule applies to everyone.
- **Wrong or missing level:** ask for one example and the level they expect. Ask whether level and track sit in one field or two only for manual upload or SFTP. If they mean the **Ravio** level (benchmark level), that's levelling: ask nothing.
- **People who shouldn't be there** (open roles, non-HR users, contractors): ask whether they're real people who haven't started yet, or not employees at all, unless a colleague has already asked.
- **Data out of date:** ask what changed and when, if not given.
- **Names showing as numbers:** ask for one example, if none given.

## Enough context to resolve

Don't draft an email when the ticket has the field or the missing people **plus** one identifiable example (an ID, a name or a screenshot) with the expected value or a clear rule, **or** a request Support can act on directly. Scope, field names, Ravio values and HR system status are not required.

## Customer-facing guidance

### Safe to say

Documented behaviours. Save them for later replies unless they directly answer the question:

- Leavers stay visible in Ravio for two weeks after their leaving date.
- Contractors and interns are hidden by default for most accounts.
- Changes with a future effective date show once that date passes.
- Your HR system is the source of truth. Where the data is wrong at source, updating it there is the most reliable fix.

### Never say or promise

- Any cause ("your data refresh is blocked", "your mapping broke").
- That the issue is our fault, or that it's fixed.
- A date or timeframe.
- That Ravio will change data in their HR system.
- That we'll manually change values on our side.
- That reconnecting or re-syncing the integration themselves will fix it.
- Internal names: tools, databases, pipelines, dashboards or internal field names.

### Privacy

Ask for one or two examples, not lists. Don't ask for exported lists of employees or salaries. Never repeat names back in the email.

## Example of a good "information missing" list

- One or two examples, with what you'd expect to see for each
- If you changed this in your HR system recently, when, and whether it's effective yet
