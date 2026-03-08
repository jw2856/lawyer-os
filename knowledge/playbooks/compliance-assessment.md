# Compliance Assessment Playbook

## When This Applies

When assessing compliance requirements for a new partnership, corridor, jurisdiction, or business activity.

## Required Context

- **Always**: `core/principles.md`, `core/organization.md`
- **Legal knowledge**: `reference/legal-knowledge/compliance-and-licensing.md`, `reference/legal-knowledge/payments-and-money-transmission.md`
- **Situational**: Relevant partner/deal context

## Process

### Step 1: Define the Scope

- What activity or relationship is being assessed?
- What jurisdictions are involved? (both your organization and counterparty — see `core/organization.md`)
- What type of payments/services? (on-ramp, off-ramp, payin, payout)
- What currencies and settlement mechanisms?
- Who are the end users? (consumers, businesses, both)

### Step 2: Licensing & Registration

- Is your organization licensed/registered to operate in the relevant jurisdictions? (check `core/organization.md` for current status)
- Does the counterparty have required licenses?
- Are there licensing gaps that need to be addressed before signing?
- Are there jurisdictions where we cannot operate (sanctions, restricted)?

### Step 3: KYC/AML Requirements

- What KYC/KYB requirements apply?
- Who is responsible for customer due diligence? (us, partner, both)
- What transaction monitoring is required?
- Are there volume thresholds that trigger enhanced due diligence (CTR, SAR)?

### Step 4: Data & Privacy

- What personal data will be processed?
- What data protection laws apply? (GDPR, CCPA, local equivalents)
- Is a DPA required?
- What cross-border transfer mechanisms are needed?

### Step 5: Sanctions & Restricted Jurisdictions

- Are any parties or jurisdictions on sanctions lists?
- Are there secondary sanctions considerations?
- Are there country-specific restrictions on crypto/digital asset activities?

### Step 6: Document Requirements

- What contractual provisions are required for compliance? (see `core/standards.md`)
- What representations and warranties are needed from the counterparty?
- What ongoing compliance obligations should be included?

### Output Format

```
## Compliance Assessment: [Subject]
Date: [date]

### Overall Status: [GREEN / YELLOW / RED]

### Licensing
- [Status by jurisdiction]

### KYC/AML
- [Requirements and responsibility allocation]

### Data Protection
- [Applicable laws and requirements]

### Sanctions
- [Screening results and considerations]

### Gaps & Actions Required
- [ ] [Gap 1] — [action needed] — [priority]
- [ ] [Gap 2] — [action needed] — [priority]

### Recommendation
[Proceed / proceed with conditions / do not proceed]
```
