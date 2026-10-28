# First response playbook: Duplicates

Request type: **Duplicates** (HubSpot internal value `Duplicate deletion`). Owner: Product Support.

This playbook is context for the First Response Agent. The customer reads the email you draft. Recognise what we already know, then ask only for what Product Support can't find itself.

Note: almost every Duplicates ticket is an internal alert or task raised by Ravio staff (for example the circuit breaker after a migration). If the ticket mentions the circuit breaker, a tenant ID or a DQ sheet, and there is no customer email or chat, don't draft: set `skip_reason` = `internal` with reasoning "Internal ticket".

## How to use this playbook

- Read the SUPPORT CONTEXT block first: who raised the ticket, the latest message, the data source, and whether Ravio has already replied.
- Then decide, in this order: skip (see the system prompt), enough context to resolve (no email), or draft.
- **Raised by a Ravio colleague** on a customer's behalf (not an internal alert): still write to the customer, but treat the colleague's description as information we already have.
- Confirm the customer is describing **the same person appearing more than once**. Similar-sounding problems are often something else (see below).
- **Examples, not IDs:** ask for examples and don't specify how to identify people (ID, name or screenshot are all fine). If people are already identified, don't ask for more. Never repeat names back.
- **Ravio user accounts** (invites, login, "user already exists"): people are identified by work email. Ask for an example email only if none was given, and don't ask for more if one was.
- **Customer questions**: put them in `customer_questions`.
- Usually one or two questions. Never more than five.
- Never diagnose, never admit fault, never give a timeline.
- UK English. No em dashes. Plain language.

## What this request type covers

The **same employee showing two or more times** in the customer's Ravio account. This usually follows a change to how their data reaches Ravio: switching HR system, moving from manual upload to an integration, reconnecting an integration, switching between anonymised and named data, or uploading a new file. It can also happen when the customer's own HR system or file contains the same person twice.

## When it's really a different request type

Note this in your reasoning. If the type is clearly wrong, set `skip_reason` = `wrong_type` and name the right type in `reasoning`.

- **Errors when inviting or adding a colleague as a Ravio user** ("user already exists"): a user access problem. Ask only for the exact error or a screenshot, and which colleagues fail if no example was given.
- **Two connections to the same HR system showing**: an integration issue. Support can see all connections.
- **Headcount too high but no one appears twice** (for example leavers still showing): Ravio Data Issue.
- **Two different people who share a name**: not a duplicate.
- **A planned switch of HR system or integration**: a Migration request.

## Things Support can look up itself – never ask

- The company, tenant, HR system and data source, now and before.
- Migration, reconnection and anonymised ↔ named history.
- Circuit breaker status and the duplicate count.
- Which records are duplicated and how the copies differ.
- Headcount in Ravio and in the source.
- For integrated customers, whether the duplicate also exists in their HR system data.
- Any level changes made in Ravio.

## Information we need

### Must have

1. **One or two examples of people who appear more than once**, unless one is already named or shown.
   - Ask: "Could you share one or two examples of people who appear more than once?"
2. **How many employees they expect to see**, only if they say the total is wrong without giving numbers.
3. **What changed**, only for manual-upload or SFTP customers, or a change Support couldn't see (a change in their own HR system, a file they uploaded). Never ask whether they reconnected or switched HR system with Ravio: Support can see that.
   - Ask: "Did anything change on your side just before this, such as a new file or a change in your HR system?"

### Helpful if missing

4. **Whether the person also appears twice in their upload file** (manual upload or SFTP only).

## Enough context to resolve

One duplicated employee (an ID, a name or a screenshot), or a clear description such as "everyone appears twice", is enough. Scope, timing and cause are for Support to establish.

## Customer-facing guidance

### Safe to say

- We'll check where the extra records have come from before removing anything, so no data is lost.

### Never say or promise

- Any cause ("your migration failed", "you connected twice").
- That the issue is our fault.
- That the duplicates will simply be deleted with no side effects, or a date for it.
- That they should disconnect or reconnect their integration themselves.
- Internal names: tools, matching processes, the circuit breaker, databases or internal teams.

### Privacy

Ask for an example or two, not lists. Don't ask for lists of names or exports of their employee data. Never repeat names back in the email.

## Example of a good "information missing" list

- One or two examples of people who appear more than once
