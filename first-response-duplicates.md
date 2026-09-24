# First response playbook: Duplicates

Request type: **Duplicates** (HubSpot internal value `Duplicate deletion`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer will read the email you draft. Your job is to recognise what we already know, then ask only for what is missing, so Product Support can clean up the duplicate records safely.

Note: most Duplicates tickets are raised internally by Ravio staff, for example after a data migration. If the ticket has no customer contact, or reads like an internal task, don't draft a customer email. Say so in your reasoning.

## How to use this playbook

- Decide first whether the ticket already has enough to act on (see "Enough context to resolve"). If it does, do not draft an email.
- Confirm the customer is describing **the same person appearing more than once**. Similar-sounding problems are often something else (see below).
- Ask only for items that are genuinely missing. Group them into one short list. Five questions is a sensible ceiling.
- Always ask for **employee IDs (or employee numbers), not names**.
- Never diagnose the cause, never admit fault, never give a timeline.
- Write in UK English. No em dashes. Plain language.

## What this request type covers

The **same employee showing two or more times** in the customer's Ravio account. This usually follows a change to how their data reaches Ravio, for example:

- switching HRIS (Human Resources Information System),
- moving from manual upload to an integration,
- reconnecting an integration, or connecting a second one,
- switching between an anonymised and a named integration,
- uploading a new file or a manual refresh.

It can also happen when the customer's own HRIS or upload file contains the same person twice.

## When it's really a different request type

Note this in your reasoning and keep your questions relevant.

- **Headcount looks too high but no one appears twice** (for example leavers still showing): Ravio Data Issue.
- **Two different people who share a name**: not a duplicate. Their IDs and details will differ.
- **"User already exists" when inviting a colleague to Ravio**: a user access problem, not employee duplicates.
- **A planned switch of HRIS or integration**: a Migration request.
- **Data generally out of date or missing**: Ravio Data Issue.

## What we usually already know (don't ask for these)

- The company and tenant.
- Which HRIS or upload method they currently use.
- Often, whether a migration or reconnection happened recently (Support can check this internally).

## Information we need

### Must have

1. **Two or three examples of people who appear more than once, by employee ID.** If the two copies show different IDs, ask for both.
   - Ask: "Could you share the employee IDs of two or three people who appear more than once? If each copy shows a different ID, please send both."
2. **How many people are affected.** A handful, a particular group, or most of the company. An expected vs shown headcount is ideal.
   - Ask: "Roughly how many people are showing twice? If it's easier, how many employees do you expect to see, and how many does Ravio show?"
3. **When they first noticed, and whether anything changed just before.** For example switching or reconnecting their HR system, going from anonymised to named data, or uploading a new file.
   - Ask: "When did you first notice this? Did anything change around then, such as switching or reconnecting your HR system, or uploading a new file?"

### Helpful if missing

4. **How the copies differ.** For example one shows a name and the other a number, one looks older, or they have different job titles.
   - Ask: "Do the two entries look different in any way, for example one showing a name and the other a number?"
5. **Whether the person also appears twice in their HRIS or upload file**, or only in Ravio.
   - Ask: "Does the person appear twice in your HR system or upload file as well, or only in Ravio?"
6. **Where in Ravio they see it** (which page), with a screenshot with names blurred.
7. **Whether they've made changes to these employees in Ravio**, such as level adjustments. A clean-up can affect them, so it's useful to know in advance.

## Enough context to resolve

Don't draft an email when the ticket already includes:

- at least one or two duplicated employee IDs (or a clear expected vs shown headcount),
- the scope,
- and when it started, or the change that came just before it.

## Customer-facing guidance

### Safe to say

- We'll check where the extra records have come from before removing anything, so we don't lose any of their data.

### Never say or promise

- Any cause ("your migration failed", "you connected twice").
- That the issue is our fault.
- That the duplicates will simply be deleted with no side effects, or a date for it. A clean-up needs care, and some changes can't be undone.
- That they should disconnect or reconnect their integration themselves. Reconnecting can create more duplicates. Only suggest it if Product Support asks.
- Internal names: tools, matching processes, databases or internal teams.

### Privacy

Ask for employee IDs rather than names. Don't ask for lists of names or exports of their employee data. If they send screenshots, ask them to blur names.

## Example of a good "information missing" list

- The employee IDs of two or three people who appear more than once (both IDs if the copies differ)
- Roughly how many people are affected, or how many employees you expect vs how many Ravio shows
- When you first noticed, and whether anything changed around then, such as switching or reconnecting your HR system
