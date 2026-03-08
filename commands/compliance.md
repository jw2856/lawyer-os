---
description: Assess compliance requirements for a partnership, corridor, or activity — licensing, KYC/AML, data privacy, sanctions screening, and contractual provisions
argument-hint: "<activity or jurisdiction>"
---

# /lawyer-os:compliance -- Compliance Assessment

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Assess compliance requirements for a business activity, partnership, or corridor. Identify licensing, KYC/AML, data protection, and sanctions requirements across jurisdictions, flag gaps, and recommend actions.

## Invocation
```
/lawyer-os:compliance [activity or relationship] [jurisdictions] [optional: compliance area]
```

## Workflow

### Step 1: Accept the Compliance Question

Accept the compliance question in any of these formats:
- **Direct description**: Activity, relationship, or corridor described in the conversation
- **File path**: Background document (PDF, DOCX) describing the proposed activity
- **URL**: Link to a document in ~~cloud storage with deal or activity details
- **Pasted text**: Description of the activity or regulatory question

If the question is too vague, prompt the user for specifics before proceeding.

### Step 2: Gather Context

Ask the user for context before beginning the assessment:

1. **What is the activity?** (new partnership, new corridor, new product feature, expansion into new jurisdiction, change to existing activity)
2. **Which entities are involved?** (which of your entities, which counterparty, any intermediaries — see `core/organization.md`)
3. **Which jurisdictions?** (origin, destination, intermediary jurisdictions, user locations — include both your jurisdictions and counterparty's)
4. **What is the data flow?** (what data is collected, processed, stored, and where)
5. **What is the money flow?** (who sends, who receives, through which channels, which currencies/assets)
6. **Timeline**: When does this need to launch? Is there a contractual deadline?
7. **Focus area**: Is this a full compliance assessment or focused on a specific area (licensing, sanctions, data privacy, KYC/AML)?

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the assessment:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/organization.md` — Entity structure and regulatory posture
- `knowledge/playbooks/compliance-assessment.md` — Step-by-step assessment process

**Load by compliance area** (infer from the question, or load all if full assessment):
- `knowledge/reference/legal-knowledge/compliance-and-licensing.md` — Licensing, registration, regulatory frameworks
- `knowledge/reference/legal-knowledge/payments-and-money-transmission.md` — Payments, money transmission, MTL (if payments-related)
- `knowledge/reference/legal-knowledge/data-privacy.md` — Data protection, GDPR, CCPA (if data-related)
- `knowledge/reference/legal-knowledge/international-trade.md` — Sanctions, export controls, cross-border (if cross-border)

**Load contextual knowledge:**
- Load relevant context file for the entity, partner, or deal
- If a context file has a **Compliance Notes** section, incorporate those requirements

### Step 4: Define Scope

Map the activity to applicable regulatory frameworks:

| Dimension | Details |
|-----------|---------|
| **Activity Type** | [payment processing, data handling, lending, custody, exchange, other] |
| **Entities Involved** | [your entity (see `core/organization.md`), counterparty, intermediaries] |
| **Jurisdictions** | [origin, destination, intermediary, user locations] |
| **Applicable Frameworks** | [state MTL, federal regulations, EU PSD2, GDPR, etc.] |
| **Data Types** | [personal data, financial data, transaction data, none] |
| **Money/Asset Flow** | [fiat, crypto, Lightning, stablecoins, direction of flow] |

### Step 5: Assess Licensing and Registration

For each jurisdiction, determine:

| Jurisdiction | Required License/Registration | Current Status | Gap | Action Required | Timeline |
|-------------|------------------------------|---------------|-----|----------------|----------|
| [jurisdiction] | [license type] | [held/pending/not held] | [description] | [what to do] | [urgency] |

Flag any jurisdictions where the activity cannot proceed without a license.

### Step 6: Assess KYC/AML Requirements

Evaluate know-your-customer and anti-money-laundering obligations:

| Requirement | Applicable? | Current Compliance | Gap | Action Required |
|------------|------------|-------------------|-----|----------------|
| Customer identification | [yes/no] | [status] | [gap] | [action] |
| Customer due diligence (CDD) | [yes/no] | [status] | [gap] | [action] |
| Enhanced due diligence (EDD) | [yes/no] | [status] | [gap] | [action] |
| Transaction monitoring | [yes/no] | [status] | [gap] | [action] |
| Suspicious activity reporting | [yes/no] | [status] | [gap] | [action] |
| Travel Rule compliance | [yes/no] | [status] | [gap] | [action] |
| Recordkeeping | [yes/no] | [status] | [gap] | [action] |

### Step 7: Assess Data Protection

Identify data protection requirements:

| Requirement | Framework | Applicable? | Current Compliance | Gap | Action Required |
|------------|-----------|------------|-------------------|-----|----------------|
| Lawful basis for processing | [GDPR/CCPA/other] | [yes/no] | [status] | [gap] | [action] |
| Data processing agreement | [GDPR Art. 28] | [yes/no] | [status] | [gap] | [action] |
| Cross-border transfer mechanism | [SCCs/adequacy/BCRs] | [yes/no] | [status] | [gap] | [action] |
| Data subject rights | [GDPR/CCPA] | [yes/no] | [status] | [gap] | [action] |
| Breach notification | [72-hour/varies] | [yes/no] | [status] | [gap] | [action] |
| Privacy impact assessment | [DPIA] | [yes/no] | [status] | [gap] | [action] |

### Step 8: Screen Sanctions and Restricted Jurisdictions

Check against sanctions lists and restricted jurisdiction policies:

| Screen | Result | Details |
|--------|--------|---------|
| **OFAC SDN List** | [clear/hit/potential match] | [details] |
| **OFAC Sectoral Sanctions** | [clear/hit/potential match] | [details] |
| **EU Sanctions** | [clear/hit/potential match] | [details] |
| **UN Sanctions** | [clear/hit/potential match] | [details] |
| **Restricted Jurisdictions** | [clear/restricted] | [which jurisdictions, which restrictions] |
| **Secondary Sanctions Risk** | [low/medium/high] | [details] |

### Step 9: Document Required Contractual Provisions

Identify compliance clauses that must be included in any agreements:

| Provision | Requirement Source | Draft Language Available? |
|-----------|-------------------|------------------------|
| [e.g., sanctions representations] | [OFAC guidance] | [yes -- see clause library / no -- needs drafting] |
| [e.g., AML cooperation] | [BSA/FinCEN] | [yes/no] |
| [e.g., DPA] | [GDPR Art. 28] | [yes/no] |

### Step 10: Business Impact Summary

Provide a summary covering:
- **Overall compliance status**: GREEN (proceed) / YELLOW (proceed with conditions) / RED (do not proceed until resolved)
- **Top compliance risks**: Most material gaps or requirements
- **Cost and timeline estimate**: What will it take to close the gaps (licensing fees, implementation time, legal costs)
- **Go/no-go recommendation**: Can the activity launch as planned, or does it need to be scoped, delayed, or restructured?
- **Ongoing obligations**: What continuing compliance requirements will the activity create?

### Step 11: Post to Chat (If Connected)

If ~~chat is connected and the user requests it:
- Post the compliance status summary (GREEN/YELLOW/RED) and top findings to the relevant channel
- Include action items and timeline

## Output Format

```
## Compliance Assessment Summary

**Activity**: [description of the activity or relationship]
**Entities**: [your entity (see `core/organization.md`), counterparty, intermediaries]
**Jurisdictions**: [all applicable jurisdictions]
**Compliance Areas Assessed**: [licensing, KYC/AML, data protection, sanctions, all]
**Date**: [assessment date]

## Overall Status: [GREEN / YELLOW / RED]

## Findings by Category

### Licensing & Registration
[Requirements table, current status, gaps, and required actions]

### KYC/AML
[Requirements table, current status, gaps, and required actions]

### Data Protection
[Requirements table, current status, gaps, and required actions]

### Sanctions & Restricted Jurisdictions
[Screening results table, restrictions, and required actions]

### Required Contractual Provisions
[Provisions table with requirement sources]

## Business Impact

**Cost to comply**: [estimated cost and resources]
**Timeline to comply**: [estimated timeline]
**Ongoing obligations**: [continuing requirements]
**Risk of proceeding without full compliance**: [exposure]

## Gaps and Required Actions

| # | Gap | Category | Severity | Action Required | Owner | Deadline |
|---|-----|----------|----------|----------------|-------|----------|
| 1 | [gap] | [category] | [high/medium/low] | [action] | [who] | [when] |

## Recommendation

[Proceed / Proceed with conditions / Do not proceed]
[Specific conditions or prerequisites if conditional]

## Next Steps

| Action Item | Owner | Deadline | Priority |
|------------|-------|----------|----------|
| [action] | [who] | [when] | [high/medium/low] |
```

## Notes

- If the user specifies a compliance area (e.g., "just check sanctions"), focus on that area but flag if other areas appear material
- Compliance requirements vary significantly by jurisdiction; always identify which jurisdictions apply and note any uncertainty
- Cross-border activities may trigger requirements in multiple jurisdictions simultaneously
- For novel activities (e.g., new asset types, new payment rails), note where regulatory guidance is unclear or evolving
- If the assessment reveals a need for outside counsel opinion (e.g., foreign law, novel regulatory question), recommend specific expertise needed
- Sanctions screening results should be treated as preliminary; flag any potential matches for manual review

## After Completion

Suggest knowledge updates if relevant:
- **Compliance finding**: "This assessment identified a new requirement -- should I update the legal knowledge base?"
- **Jurisdiction gap**: "We don't have detailed compliance knowledge for [jurisdiction] -- should I create a reference?"
- **Decision log**: "Should I log this compliance determination in memory?"
- **Context update**: "Should I update the context file for [entity/partner] with these compliance findings?"
