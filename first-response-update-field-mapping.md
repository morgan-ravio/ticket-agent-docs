# First response playbook: Update Field Mapping

Request type: **Update Field Mapping** (HubSpot internal value `Custom Field Mappings`). Owner: Integrations team.

This playbook is context for the First Response Agent. The customer will read the email you draft. Your job is to recognise what we already know, then ask only for what is missing, so the team can point Ravio at the right field in their HRIS (Human Resources Information System) first time.

Because the Integrations team owns this type, write the reply as an acknowledgement and information request. Don't imply Product Support will make the change.

## How to use this playbook

- Decide first whether the ticket already has enough to act on (see "Enough context to resolve"). If it does, do not draft an email.
- Ask only for items that are genuinely missing. Group them into one short list. Five questions is a sensible ceiling.
- Always ask for **employee IDs (or employee numbers), not names**.
- One issue per ticket. This type is often bundled with exclusions, levelling or benchmark questions. Focus on the mapping and suggest raising the others separately.
- If they have several legal entities or Ravio accounts, confirm which one(s) the change is for.
- Never diagnose, never admit fault, never give a timeline.
- Write in UK English. No em dashes. Plain language.

## What this request type covers

Changing **which HRIS field Ravio reads** for a piece of data. This only applies to customers with an HRIS integration, not manual uploads. The most common requests:

- **Level or grade** (the most frequent, often so a levelling framework can be set up),
- **Department or team** (for example team names showing where departments should be),
- **Work location**: city and/or country (for example office city vs home city),
- **Salary, FTE (full-time equivalent) % or working hours**,
- **Variable pay**: bonus and commission,
- **Gender or date of birth**, for example for EU Pay Transparency reporting,
- **Job title** or **employment type**.

## When it's really a different request type

Note this in your reasoning and keep your questions relevant.

- **The value in the HRIS itself is wrong**: the customer should fix it at source, or it's an Overrides request.
- **One person's value needs changing**: Overrides.
- **Hiding or showing employees**: Exclusions.
- **Salaries mapped correctly but the amount is still wrong** (part-time scaling, pay periods, holiday allowance): Pay Annualisation.
- **Data correct in the HRIS but out of date in Ravio**: Ravio Data Issue.
- **How their roles map to Ravio levels** once the field is in: a correlation table change, handled by the Business Operations team.

## What we usually already know (don't ask for these)

- The company and tenant.
- Which HRIS they use.
- Roughly which data point they're unhappy with.

## Information we need

### Must have

1. **Which piece of Ravio data should change** (level, department, location, salary, FTE, variable pay, gender, date of birth, job title).
   - Ask: "Which information in Ravio would you like us to take from a different field?"
2. **The exact name of the HRIS field that holds the correct data**, as it appears in their HR system. Where the field sits (for example the "Jobs" or "Employment" section) helps too. When customers name the field precisely, these tickets are usually resolved without any follow-up.
   - Ask: "What's the name of the field in your HR system that holds the correct information, and which section of the employee profile is it in?"
3. **Two or three example employees**, by employee ID, with what that field shows for them. We use these to check we're reading exactly the right field.
   - Ask: "Could you share two or three employee IDs, and what that field shows for each of them? A screenshot of the field on one profile, with the name blurred, is ideal."
4. **Confirmation the field is filled in and visible to Ravio.** This is the most common reason these tickets stall. Many HR systems restrict custom or sensitive fields (for example contract type, gender, date of birth) until the account connected to Ravio is given permission.
   - Ask: "Could you check that this field is filled in for your employees, and that the account connected to Ravio has permission to view it? Some HR systems restrict custom or sensitive fields by default."

### Helpful if missing

5. **Whether this applies to everyone or a subset** (for example one country or entity uses a different field).
6. **The field it should replace**, if they want to swap from one field to another.
7. **Whether the field is fully populated yet**, or still being filled in.

### Extra questions by scenario

- **Level:** ask whether level and track (for example manager or individual contributor) are in one field or in separate fields, and the name of each.
- **Location:** ask whether city and country are in one field or separate fields, and whether it should be office location or the employee's own location.
- **Department or team:** ask which field holds departments, and whether there's a fallback field for people without one.
- **Part-time pay:** ask whether they record an FTE % (for example 80%) or hours worked vs full-time hours, and the field name(s).
- **Variable pay:** ask which fields hold bonus and commission, whether amounts are targets or actual payouts, and whether they're monthly or annual.
- **Gender or date of birth:** ask for the field names and to confirm permission to view them. We need date of birth, not age.

## Enough context to resolve

Don't draft an email when the ticket already includes:

- the Ravio data point to change,
- the exact HRIS field name (ideally with its section),
- example values or example employee IDs,
- and, for level, location or part-time pay, whether the data sits in one field or several.

A request such as "please use 'Job level name' in the Jobs section for Level" can be actioned directly.

## Customer-facing guidance

### Safe to say

- Ravio can only read fields the connected account has permission to see.
- Your HR system is the source of truth. If a value is wrong there, updating it in the HR system is the best fix.

### Never say or promise

- That changing the field will definitely fix the salary or location shown. Those values go through further processing.
- That we can create a new field on our side.
- A date or timeframe.
- Any cause, or that anything is our fault.
- Internal names: integration provider dashboards, test fields, databases or data refresh tooling.

### Privacy

Ask for field names and a few employee IDs, not full exports. This matters most for sensitive fields such as gender and date of birth. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- Which information in Ravio should come from a different field
- The name of the field in your HR system that holds the correct data, and which section it's in
- Two or three employee IDs and what that field shows for each
- Confirmation the field is filled in and that the account connected to Ravio can see it
