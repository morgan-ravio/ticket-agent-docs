# Ticket agent docs

First-response playbooks used by the HubSpot Ticketing Agent in n8n. For each request type, the `First Response Router` node loads one doc as context for the First Response Agent. The agent then decides whether to skip, whether the ticket already has enough to act on, or drafts a customer-facing acknowledgement that asks only for the information Product Support can't find itself.

| Request type (HubSpot label) | Internal value (`bops_request_type`) | Owner | Doc |
|---|---|---|---|
| Pay Annualisation | `Data Update` | Product Support | `first-response-pay-annualisation.md` |
| Ravio Data Issue | `E2E` | Product Support | `first-response-ravio-data-issue.md` |
| Duplicates | `Duplicate deletion` | Product Support | `first-response-duplicates.md` |
| Exclusions | `Contractor/Exclusions` | Product Support | `first-response-exclusions.md` |
| Overrides | `Overrides` | Product Support | `first-response-overrides.md` |
| Update Field Mapping | `Custom Field Mappings` | Integrations | `first-response-update-field-mapping.md` |

Raw URL pattern for the router's `doc_url`:

`https://raw.githubusercontent.com/morgan-ravio/ticket-agent-docs/refs/heads/main/<file name>`

## Every doc follows the same structure

1. How to use the playbook (rules that apply to every draft)
2. What the request type covers
3. When it's really a different request type
4. Things Support can look up itself – never ask
5. Information we need: must have, helpful if missing, and extra questions by scenario
6. Enough context to resolve (when no email should be drafted)
7. Customer-facing guidance: safe to say, never say or promise, privacy
8. An example "information missing" list

## Rules shared by every playbook

These also live in the First Response Agent's system prompt, so each playbook only repeats what matters for its type.

- Read the SUPPORT CONTEXT block first (who raised the ticket, latest message, data source, existing Ravio reply).
- Tickets raised by a Ravio colleague still get a first response to the customer, but the colleague's text counts as information we already have.
- Never ask for anything Support can look up. We see the fields the integration shares and their values, but not always under the name the customer sees, so a field name can be asked for when it's genuinely needed and not given.
- Ask for **examples**, not specifically employee IDs. The customer can identify people however suits them (ID, name or screenshot). If people are already identified, don't ask for more. Never repeat names back.
- Customer questions go in `customer_questions` for the team to answer.
- Usually two or three questions, never more than five.

## Sources

The checklists come from the verified Product Support Knowledge Base guides (Pay Annualisation Overview and SOP, Holiday allowance by country, Exclusions & Inclusions, Overrides, Field Mapping, Integration Issues, Circuit Breaker, "User already exists" SOP). They were then revised (October 2026) after reviewing 117 AI first-response notes against what Support actually needed to resolve each ticket.

## Editing

- Keep each doc focused on what to ask the customer. Internal procedures belong in Notion.
- Keep each doc under 16,000 characters (the workflow trims anything longer).
- Never add internal tool, table or field names in a way the agent could repeat to a customer.
- UK English, no em dashes, and ask for "examples" rather than employee IDs.
