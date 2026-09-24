# First response playbook: Pay Annualisation

Request type: **Pay Annualisation** (HubSpot internal value `Data Update`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer will read the email you draft. Your job is to recognise what we already know, then ask only for what is missing, so Product Support can fix the salaries in as few replies as possible.

## How to use this playbook

- Decide first whether the ticket already has enough to act on (see "Enough context to resolve"). If it does, do not draft an email.
- Ask only for items that are genuinely missing. Group them into one short list. Five questions is a sensible ceiling.
- Always ask for **employee IDs (or employee numbers), not names**. We avoid handling personal data we don't need.
- One issue per ticket. If the email also raises unrelated topics (missing variable pay, headcount, product feedback), say we'll focus this ticket on the salary issue and suggest raising the others separately.
- Never diagnose the cause, never admit fault, never give a timeline.
- Write in UK English. No em dashes. Plain language a busy HR or Reward professional understands on first read.

## What this request type covers

Salaries that are **present in Ravio but wrong**. In practice nearly every ticket falls into one of these:

- **Part-time / FTE (full-time equivalent) scaling.** Part-timers show inflated salaries (their pay was already stored at the full-time rate and was scaled up again) or deflated salaries (their actual part-time pay shows instead of the full-time equivalent).
- **Pay period / multiplier.** A monthly figure treated as annual (or the reverse), or a 13th or 14th month salary missing or double-counted. Common in Switzerland, Austria, Portugal, Italy, Greece, Belgium and Spain.
- **Holiday allowance.** For example the Netherlands 8% holiday allowance applied twice, or not at all, when the customer expects it.
- **Groups with different pay rules.** For example contractors paid monthly vs annually.

## When it's really a different request type

Note this in your reasoning. Don't lecture the customer; just keep your questions relevant.

- **Salary missing entirely** (blank, not wrong): Ravio Data Issue.
- **The wrong salary field is used for everyone** (for example a base that includes bonus): Update Field Mapping.
- **An old salary still showing after a change in the HRIS (Human Resources Information System)**: Ravio Data Issue or Integration – Data Refresh.
- **Variable pay shown as an amount instead of a %**: expected behaviour (Ravio shows target amounts). Not an annualisation fault.
- **"Does your Netherlands benchmark include holiday allowance?"**: a benchmark methodology question for the Customer Success Manager, not a data fix.
- **Contractors who should be hidden**: Exclusions.

## What we usually already know (don't ask for these)

- The company and tenant.
- Whether they use an HRIS integration or manual upload.
- A rough statement that "salaries look wrong", often from their Customer Success Manager.

## Information we need

### Must have

1. **At least one worked example: the employee ID, the salary Ravio shows now, and the salary it should show.** This is the single most important item. Without a correct figure we can't tell which field or multiplier is wrong, or confirm the fix worked. Two or three examples is ideal.
   - Ask: "Could you share one or two examples, with the employee ID, the salary you currently see in Ravio, and the salary you'd expect to see?"
2. **Who is affected (scope).** One person, a group (a country, part-timers, contractors), or everyone. This decides whether we adjust a single employee, a country rule, or the whole account.
   - Ask: "Is this affecting everyone, a particular group (for example part-time staff or one country), or only specific people?"
3. **The country or countries of the affected employees.** Pay conventions (holiday allowance, 13th and 14th month) are set per country.
   - Ask: "Which country or countries are the affected employees based in?"
4. **For part-time cases: how the salary is stored in their HRIS.** Is the figure already the full-time (100%) salary, or the actual part-time pay? This decides whether we add or remove scaling.
   - Ask: "For part-time employees, is the salary in your HR system the full-time equivalent, or the amount they're actually paid?"

### Helpful if missing

5. **Where FTE % or working hours are recorded**, and the field name as it appears in the HRIS (for example "FTE %", "Weekly hours", "Working pattern"). We often can't find this field ourselves, either because it has an unusual name or the integration can't see it.
   - Ask: "Which field in your HR system holds each person's FTE % or weekly hours?"
6. **The full-time hours baseline** if they record hours (for example 38 or 40 hours a week counts as full time).
   - Ask: "How many hours a week counts as full time for these employees?"
7. **The pay period the HRIS stores**: annual, monthly, or another period such as "monthly × 14".
   - Ask: "Is the salary in your HR system held as an annual or a monthly amount? Are there 13th or 14th month payments?"
8. **Whether the salary already includes holiday allowance or extra month payments.** If it does and Ravio adds it too, it's counted twice.
   - Ask: "Does the salary figure in your HR system already include holiday allowance or a 13th or 14th month payment?"
9. **The rule they want, per group**, when groups are paid differently (for example "annually paid contractors × 1, monthly paid × 12").
10. **A screenshot** of the employee's record in the HRIS and of the figure in Ravio. Ask them to blur names.

### Extra questions by scenario

- **Part-timers look too high:** ask items 1, 4 and 5. The most common cause is pay stored at 100% and scaled again, but don't say so.
- **Part-timers look too low:** ask items 1, 5 and 6.
- **Salaries look about 12 times too high or too low:** ask items 1 and 7.
- **Netherlands, Belgium, or 13th/14th month countries:** ask items 1, 7 and 8.
- **Contractors on day or monthly rates:** ask how each contractor group is paid and what annual figure they'd expect. Don't promise we can annualise day or hourly rates.

## Enough context to resolve

Don't draft an email when the ticket already includes:

- at least one example with an **employee ID, the current Ravio salary and the expected salary**,
- the **scope** (who is affected) and **country**,
- and, for part-time cases, a clear statement of how pay is stored (for example "salaries are already at 100% FTE, stop scaling them").

An obvious whole-group statement such as "all part-timers are inflated by their FTE %, our HRIS already stores full-time salaries" is enough even without examples.

## Customer-facing guidance

### Safe to say

- We'd like an example with a correct figure so we can check our fix against it.
- We handle part-time salaries by converting them to a full-time equivalent, so they can be compared fairly with benchmarks.

### Never say or promise

- Any cause ("we double-counted your holiday allowance", "our system over-annualised").
- That the issue is our fault, or that it's fixed.
- A date or timeframe.
- That we'll remove holiday allowance. That changes many salaries and needs confirmation with their Customer Success Manager first.
- That we can annualise daily or hourly contractor rates.
- Internal names: tools, databases, pipelines, override names or internal field names.

### Privacy

Ask for employee IDs and only the figures we need. Don't ask for spreadsheets of names and salaries. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- One or two examples: employee ID, the salary you see in Ravio, and the salary you'd expect
- Whether this affects all part-time staff, one country, or specific people
- Whether the salary in your HR system is the full-time figure or the actual part-time pay
- The field in your HR system that holds FTE % or weekly hours
