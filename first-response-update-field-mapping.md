# First response playbook: Update Field Mapping

Request type: **Update Field Mapping** (HubSpot internal value `Custom Field Mappings`). Owner: Integrations team.

This playbook is context for the First Response Agent. The customer reads the email you draft. Recognise what we already know, then ask only for what is missing, so the team can point Ravio at the right field first time. When the customer has already named the field, the team can usually map it with no reply needed.

Because the Integrations team owns this type, write the reply as an acknowledgement and information request. Don't imply Product Support will make the change.

## How to use this playbook

- Read the SUPPORT CONTEXT block first: who raised the ticket, the latest message, the data source, and whether Ravio has already replied.
- Then decide, in this order: skip (see the system prompt), enough context to resolve (no email), or draft.
- **If the latest message is from Ravio** saying it's done, or asking the customer to confirm, don't draft (`skip_reason` = `existing_thread`).
- **Raised by a Ravio colleague** (many are, often in shorthand such as "Map in city" or "Please can we map in their levels"): still write to the customer if something is genuinely missing, but treat the colleague's text as information we already have. Shorthand that names the data point and the source field is enough context.
- **Examples of people:** only ask when specific people are wrong and the customer hasn't said who, and don't specify how to identify them. Never ask for examples just to check a field: Support can see the values in every field the integration shares.
- **Customer questions** (for example "how is location populated?"): put them in `customer_questions`. Don't answer them and don't turn them into a question back.
- Usually one or two questions. Never more than five.
- Never diagnose, never admit fault, never give a timeline.
- UK English. No em dashes. Plain language.

## What this request type covers

Changing **which field Ravio reads** for a piece of data. Mainly HR system integrations. For SFTP customers, the mapping is to a column in their file: ask only whether a recent file includes that column. For manual uploads there's nothing to map. The most common requests:

- **Level or grade** (the most frequent, often so a levelling framework can be set up),
- **Department or team**,
- **Work location**: city and/or country (for example office city vs home city),
- **Salary, FTE (full-time equivalent) % or working hours**,
- **Variable pay**: bonus and commission,
- **Gender or date of birth**, for example for EU Pay Transparency reporting,
- **Job title** or **employment type**.

## When it's really a different request type

Note this in your reasoning. If the type is clearly wrong, set `skip_reason` = `wrong_type` and name the right type in `reasoning`.

- **Changing which Ravio position or Ravio level a job title or level maps to** ("bulk update Ravio mappings", "remap levels for 100 employees", "where is the correlation table"): position mapping or the correlation table, not a field mapping.
- **Levels corrected by hand in Ravio that now don't update**: likely Overrides.
- **Location values changed without the customer doing anything**: Support investigates. Ask nothing about fields or Ravio screens.
- **The value in the HR system itself is wrong**: the customer should fix it at source, or it's Overrides.
- **One person's value needs changing**: Overrides.
- **Hiding or showing employees**: Exclusions.
- **Salaries mapped correctly but the amount is still wrong**: Pay Annualisation.
- **Data correct in the HR system but out of date in Ravio**: Ravio Data Issue.

## Things Support can look up itself – never ask

- The HR system, integration type and data source.
- The fields the integration shares with us and the values in each.
- Which field is currently mapped to what, and the value showing in Ravio.
- Whether a field is visible to Ravio. Support checks first.
- Any employee's country, location, level, title and department.
- Field names and decisions already given in the ticket, including a colleague's shorthand.

**Field names:** we see the integration's version of each field, which doesn't always match the label the customer sees in their HR system (custom fields especially). So the field name, as the customer sees it, is the one thing we often do need. Treat any reasonable naming ("Site", "Job Level Name", "levels") as given. Don't ask them to confirm it or to say which section of the profile it's in.

## Information we need

### Must have

1. **Which piece of Ravio data should change**, if it isn't clear.
   - Ask: "Which information in Ravio would you like us to take from a different field?"
2. **The name of the field that holds the correct data**, as it appears in their HR system, if they haven't named it. An example of a value it holds helps us match it to what we see.
   - Ask: "What's the field called in your HR system, and what does it show for one employee (for example 'Senior 2')?"
3. **Confirmation the field is visible to Ravio**, only if the field is sensitive (gender, date of birth, contract type) or newly created.
   - Ask: "If this field is new or restricted, could you check the account connected to Ravio has permission to view it?"

### Helpful if missing

4. **Whether this applies to everyone or a subset** (for example one country or entity uses a different field), only if they hint at it.
5. **The field it should replace**, only if it's unclear.
6. **Examples of people who are wrong**, only if they say particular people are wrong and haven't said who.

### Extra questions by scenario

- **Level:** ask whether level and track (for example manager or individual contributor) are in one field or separate fields, unless it can be inferred. Ask whether the values follow their existing level framework or a new one. If new, ask them to share it (levels with short descriptions) so we can update how it maps to Ravio levels.
- **Location:** ask whether city and country are in one field or separate fields, and whether it should be the office or the employee's own location, if unclear. If locations changed without them doing anything, ask nothing about fields.
- **Department or team:** ask which field holds departments, if not named.
- **Part-time pay:** ask whether they record an FTE % or hours worked vs full-time hours, and the field name, if not given.
- **Variable pay:** ask which fields hold bonus and commission, whether amounts are targets or actual payouts, and whether they're monthly or annual, if not given.
- **Gender or date of birth:** ask for the field names and to confirm permission to view them. We need date of birth, not age. For SFTP customers, ask only for a recent file that includes the column.

## Enough context to resolve

Don't draft an email when the ticket has the Ravio data point **and** a named source field (for level, also whether track is in the same field, unless it can be inferred). Examples of people aren't required. "Please use 'Job level name' for Level" can be actioned directly, whether a customer or a colleague wrote it.

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

Ask for field names and, at most, one example value, not exports. This matters most for sensitive fields such as gender and date of birth. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- Which information in Ravio should come from a different field
- The name of the field in your HR system that holds the correct data, and what it shows for one employee
- For levels: whether level and track are in one field, and whether these values follow a new framework (if so, please share it)
