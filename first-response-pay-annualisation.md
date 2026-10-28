# First response playbook: Pay Annualisation

Request type: **Pay Annualisation** (HubSpot internal value `Data Update`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer reads the email you draft. Recognise what we already know, then ask only for what Product Support can't find itself. Many of these tickets need no questions at all.

## How to use this playbook

- Read the SUPPORT CONTEXT block first: who raised the ticket, the latest message, the data source, and whether Ravio has already replied.
- Then decide, in this order: skip (see the system prompt), enough context to resolve (no email), or draft.
- **Many of these tickets need no questions.** A clear rule is enough context on its own, for example a country's holiday allowance, "use this field as the annual salary", "annualise everyone to 40 hours" or "part-timers shouldn't be scaled".
- **Raised by a Ravio colleague** (CSM or Support) on the customer's behalf: still write to the customer, but treat the colleague's description as information we already have. Never ask the customer for something the colleague already gave.
- **Examples, not IDs:** if nobody is identified, ask for one or two examples. Don't specify how to identify people (ID, name or screenshot are all fine). If people are already identified, don't ask for more examples. Support looks them up. Never repeat names back.
- **Customer questions** (for example how to send salary data safely, or how a multiplier works): put them in `customer_questions` so the team answers them. Don't answer them and don't turn them into a question back.
- Usually two or three questions. Never more than five.
- Never diagnose the cause, never admit fault, never give a timeline.
- UK English. No em dashes. Plain language a busy HR or Reward professional understands on first read.

## What this request type covers

Salaries that are **present in Ravio but the wrong amount**:

- **Part-time / FTE (full-time equivalent) scaling.** Part-timers look too high (pay already stored at the full-time rate and scaled again) or too low (actual part-time pay shown instead of the full-time equivalent).
- **Pay period / multiplier.** A monthly figure treated as annual, or the reverse. A 13th or 14th month salary missing or counted twice. Common in Switzerland, Austria, Portugal, Italy, Greece, Belgium and Spain.
- **Holiday allowance.** For example the Netherlands 8% applied twice, or not at all.
- **Variable pay period.** Bonus or variable pay stored monthly but treated as annual, or the reverse. Handle it the same way as a pay period.
- **Groups with different pay rules.** For example contractors paid monthly vs annually.

## When it's really a different request type

Note this in your reasoning and keep your questions relevant.

- **Salary missing entirely** (blank, not wrong): Ravio Data Issue.
- **The wrong salary field is used for everyone** (for example a base that includes bonus): Update Field Mapping.
- **An old salary still showing after a change in the HR system**: Ravio Data Issue.
- **Variable pay shown as an amount instead of a %**: expected behaviour (Ravio shows target amounts).
- **Benchmark methodology questions**, such as "Does your Netherlands benchmark include holiday allowance?": not a data fix. Set `enough_context_to_resolve` to true, summarise the question and add it to `customer_questions`. Don't ask for employees or dates.
- **Contractors who should be hidden**: Exclusions.

## Things Support can look up itself – never ask

- The company, tenant, HR system and data source (integration, SFTP or manual upload).
- Every employee's country, location, level, employment type and part-time flag.
- **The salary currently showing in Ravio**, and the multipliers applied to it (holiday allowance, FTE, pay period).
- Whether FTE % or hours are mapped, and the fields the integration shares with us. Support normally finds and maps the FTE or hours field itself.
- The standard holiday allowance and 13th/14th-month uplift for each country.
- The full-time baseline: we assume a 40-hour week unless told otherwise.
- Anything we've already done for this customer (check the recent tickets line).

## Information we need

### Must have

1. **An example, only when nobody is identified and the fix isn't a clear rule:** the employee and **the annual salary it should show**.
   - Ask: "Could you share one or two examples, with the annual salary you'd expect Ravio to show for each?"
   - Skip when the fix is a clear rule, or the people are already identified.
2. **Who is affected (scope)**, only if it's unclear and matters: one person, a group (a country, part-timers, contractors) or everyone.
   - Ask: "Is this affecting everyone, a particular group (for example part-time staff or one country), or specific people?"
3. **For part-time cases: how the salary is stored.** Is it already the full-time (100%) salary, or the actual part-time pay?
   - Ask: "For part-time employees, is the salary in your HR system the full-time equivalent, or the amount they're actually paid?"
   - Skip if they've already said what they want (for example "make them full time", "already pre-annualised", "stop scaling").

### Helpful if missing

4. **The full-time hours baseline**, only if the customer suggests a different baseline from 40 hours without stating it.
   - Ask: "How many hours a week counts as full time for these employees?"
5. **The pay period the HR system stores**, only when the figures look about 12 times too high or low and they haven't said.
   - Ask: "Is the salary in your HR system an annual or a monthly amount? Are there 13th or 14th month payments?"
6. **Whether the salary already includes holiday allowance or extra month payments.** Don't ask if they've already said.
   - Ask: "Does the salary figure in your HR system already include holiday allowance or a 13th or 14th month payment?"
7. **The rule they want, per group**, when groups are paid differently and they haven't said (for example "annually paid contractors × 1, monthly paid × 12").
8. **The FTE or hours field**: don't ask in a first response. Support finds and maps it itself, and follows up only if it can't find it.

### Extra questions by scenario

- **Part-timers look too high:** item 1 and item 3, only if not already stated.
- **Part-timers look too low:** usually nothing. Item 1 only if nobody is identified.
- **Salaries about 12 times too high or too low:** item 5, plus item 1 if nobody is identified.
- **Holiday allowance or 13th/14th-month countries:** if the country is named, ask nothing, or item 6 only if it's unclear.
- **Contractors on day or monthly rates:** ask how each contractor group is paid and what annual figure they'd expect. Don't promise we can annualise day or hourly rates.

## Enough context to resolve

Don't draft an email when **any** of these holds:

- a named country plus holiday allowance or an extra month to add or remove,
- an identified employee showing monthly instead of annual (or the reverse),
- a clear whole-group FTE statement (for example "all part-timers are inflated, our HR system already stores full-time salaries"),
- an instruction to use a named field or rule for everyone,
- a methodology question only.

## Customer-facing guidance

### Safe to say

- We convert part-time salaries to a full-time equivalent so they can be compared fairly with benchmarks.
- If they ask how to send salary data: "Please don't send salary details in plain email. The team will reply with a secure way to share them."

### Never say or promise

- Any cause ("we double-counted your holiday allowance").
- That the issue is our fault, or that it's fixed.
- A date or timeframe.
- That we'll remove holiday allowance. That changes many salaries and needs confirming first.
- That we can annualise daily or hourly contractor rates.
- Internal names: tools, databases, pipelines, override names or internal field names.

### Privacy

Ask for one or two examples and only the figures we need. Don't ask for spreadsheets of names and salaries. Never repeat names back in the email.

## Example of a good "information missing" list

- One or two examples, with the annual salary you'd expect Ravio to show for each
- Whether your HR system holds part-time salaries at the full-time rate or the actual pay (only if not already stated)
