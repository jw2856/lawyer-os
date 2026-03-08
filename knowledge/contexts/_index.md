# Contexts Index

> This directory contains situational knowledge organized by relationship type.
> The sub-organization is flexible -- add new categories as needed.
>
> **How to use**: Create a context file for each counterparty, deal, or relationship
> that has specific positions, history, or nuances worth tracking. Context files can
> include a "Standards Overrides" section to override defaults from `core/standards.md`.

## Partners

### [Partner Category 1] (e.g., "Strategic Partners", "Channel Partners", "Payment Partners")
[Description of this partner category]

| Partner | Type | Coverage/Scope | Status | Context File |
|---------|------|---------------|--------|-------------|
| [Example Partner] | [type] | [scope] | [status] | `partners/[category]/[name].md` |

### Vendors
SaaS and service vendors.
> See `partners/vendors/_overview.md` for vendor management standards

### Customers
Customer agreements.
> See `partners/customers/_overview.md` for customer agreement standards

## Deals
Active negotiations and matters.
> Per-deal context files created as needed in `deals/`

## Routing Hints

- **[Partner type]** by name → load specific partner file + category overview
- **Vendor** → load `partners/vendors/_overview.md` + specific vendor file if it exists
- **Customer** → load `partners/customers/_overview.md` + specific customer file if it exists
- **New relationship** → load relevant category overview + `core/standards.md`
- **Active deal** → load the deal-specific file from `deals/`
