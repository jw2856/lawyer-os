# Vendor Onboarding Playbook

## When This Applies

When evaluating and onboarding a new vendor — third-party risk management (TPRM), vendor due diligence, and agreement review.

## Required Context

- **Always**: `core/principles.md`, `core/standards.md`
- **Context**: `contexts/partners/vendors/_overview.md`
- **Playbook**: Also use `playbooks/contract-review.md` for the agreement review step

## Process

### Step 1: Intake

- What service/product is being procured?
- Who is the internal business owner?
- What data will the vendor access? (personal data, financial data, proprietary data, none)
- What systems will the vendor connect to?
- Is this a critical dependency? (would we be unable to operate if the vendor failed?)

### Step 2: Risk Assessment

Classify the vendor by risk tier:

- **High risk**: Accesses personal data, financial data, or critical systems. Handles regulated activities. Single point of failure.
- **Medium risk**: Accesses non-sensitive business data. Provides important but replaceable services.
- **Low risk**: No data access. Commodity service. Easily replaceable.

### Step 3: Due Diligence (scaled to risk tier)

**High risk vendors:**
- Security questionnaire or certification review (SOC 2 Type II, ISO 27001)
- Privacy assessment (DPA review, data flow mapping)
- Financial stability check
- Reference checks
- Insurance verification

**Medium risk vendors:**
- Security questionnaire (abbreviated)
- Privacy assessment if data is involved
- Standard contract review

**Low risk vendors:**
- Standard contract review
- Basic vendor information collection

### Step 4: Agreement Review

- Run the contract review playbook (`playbooks/contract-review.md`)
- Pay special attention to: data handling, security, liability, termination/portability
- Ensure DPA is in place if personal data is involved
- Verify insurance requirements are met (if applicable)

### Step 5: Approval and Onboarding

- Obtain required approvals based on contract value/risk tier
- Execute agreement
- Set up vendor in tracking system
- Schedule periodic review (annual for high risk, biennial for medium)

### Step 6: Ongoing Management

- Monitor vendor performance against SLAs
- Annual security/compliance review for high-risk vendors
- Track contract renewal dates
- Reassess risk tier if scope changes
