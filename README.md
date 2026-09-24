# Ticket agent docs

First-response playbooks used by the HubSpot Ticketing Agent in n8n. For each request type, the `First Response Router` node loads one doc as context for the First Response Agent. The agent then drafts a customer-facing acknowledgement that asks only for the information Product Support still needs.

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
4. What we usually already know
5. Information we need: must have, helpful if missing, and extra questions by scenario
6. Enough context to resolve (when no email should be drafted)
7. Customer-facing guidance: safe to say, never say or promise, privacy
8. An example "information missing" list

## Sources

The checklists come from the verified Product Support Knowledge Base guides (Pay Annualisation Overview and SOP, Exclusions & Inclusions, Overrides, Field Mapping, Integration Issues, Migrations, Circuit Breaker, Data Quality Check Overview). They were also checked against a review of about 150 recent HubSpot tickets of these types. The ticket review looked at what Support actually had to ask customers for before each ticket could be resolved.

## Editing

- Keep each doc focused on what to ask the customer. Internal procedures belong in Notion, not here.
- Never add internal tool, table or field names in a way the agent could repeat to a customer.
- UK English, no em dashes, and employee IDs rather than names.
