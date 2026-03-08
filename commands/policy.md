---
description: Draft or review a policy, terms of service, or similar governance document — identify legal requirements, draft provisions, flag stakeholder decisions
argument-hint: "<policy type>"
---

# /lawyer-os:policy -- Policy Drafting

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Draft or review a policy document (privacy policy, terms of service, acceptable use policy, etc.). Identify all applicable legal requirements, draft provisions meeting those requirements, and flag areas needing stakeholder input.

## Invocation
```
/lawyer-os:policy [policy type] [optional: internal or external-facing] [optional: existing version file path or URL]
```

## Workflow

### Step 1: Accept Existing Policy (If Updating)

If updating an existing policy, accept it in any of these formats:
- **File path**: Local PDF, DOCX, or other document
- **URL**: Link to the current policy in ~~cloud storage or on the company website
- **Pasted text**: Policy text pasted directly into the conversation

If drafting from scratch, no input document is needed.

### Step 2: Gather Context

Ask the user for context before beginning the draft:

1. **What type of policy?** (privacy policy, terms of service, acceptable use policy, code of conduct, data retention policy, incident response policy, cookie policy, DMCA policy, other)
2. **Internal or external-facing?** (affects tone, detail level, and legal requirements)
3. **Who is the audience?** (users/customers, employees, vendors, developers, all)
4. **What products/services does this cover?** (specific product, all products, specific feature)
5. **Which jurisdictions?** (US only, US + EU, global -- affects which legal frameworks apply)
6. **New draft or update?** (if update, what triggered the change? regulatory update, product change, legal development)
7. **Stakeholder review process**: Who needs to approve? (legal, product, engineering, executive, board)
8. **Timeline**: When does this need to be live?

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the draft:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/organization.md` — Entity structure, products, services
- `knowledge/playbooks/policy-drafting.md` — Policy process and structure

**Load by policy type:**
- Privacy policy --> `knowledge/reference/legal-knowledge/data-privacy.md`
- Terms of service --> `knowledge/reference/legal-knowledge/consumer-protection.md`
- AUP / code of conduct --> relevant governance and compliance references
- Payment terms --> `knowledge/reference/legal-knowledge/payments-and-money-transmission.md`
- Compliance policy --> `knowledge/reference/legal-knowledge/compliance-and-licensing.md`
- IP policy --> `knowledge/reference/legal-knowledge/intellectual-property.md`

**If updating an existing policy:**
- Read the existing version
- If available, read any prior change logs or version history

### Step 4: Identify Legal Requirements

Map all applicable legal requirements for the policy type and jurisdictions:

| Requirement | Source | Jurisdiction | Mandatory? | Current Coverage |
|------------|--------|-------------|-----------|-----------------|
| [e.g., data collection disclosure] | [CCPA Cal. Civ. Code 1798.100] | [California] | [yes] | [covered/missing/partial] |
| [e.g., cookie consent] | [ePrivacy Directive] | [EU] | [yes] | [covered/missing/partial] |
| [e.g., arbitration clause] | [FAA / state law] | [US] | [no -- optional] | [covered/missing/partial] |
| [e.g., DMCA safe harbor] | [17 USC 512] | [US] | [yes for safe harbor] | [covered/missing/partial] |

### Step 5: Define Policy Structure

Determine the appropriate structure based on policy type:

**Privacy Policy structure:**
| Section | Legal Basis | Content Requirements |
|---------|-----------|---------------------|
| Information We Collect | GDPR Art. 13-14, CCPA 1798.100 | Categories of data, sources, purposes |
| How We Use Information | GDPR Art. 6, CCPA 1798.100 | Purposes, legal bases for processing |
| How We Share Information | GDPR Art. 13(1)(e), CCPA 1798.115 | Categories of recipients, purposes |
| Your Rights | GDPR Art. 15-22, CCPA 1798.100-125 | Access, deletion, correction, opt-out |
| Data Retention | GDPR Art. 13(2)(a) | Retention periods by data type |
| International Transfers | GDPR Art. 44-49 | Transfer mechanisms, safeguards |
| Security | GDPR Art. 32 | Security measures description |
| Children's Privacy | COPPA, GDPR Art. 8 | Age restrictions, parental consent |
| Changes to Policy | Best practice | Notification mechanism |
| Contact Information | GDPR Art. 13(1)(a) | Controller identity, DPO contact |

**Terms of Service structure:**
| Section | Legal Basis | Content Requirements |
|---------|-----------|---------------------|
| Acceptance of Terms | Contract formation | How users accept, age/capacity requirements |
| Description of Service | Contract terms | What is being provided |
| User Responsibilities | Contract terms | Prohibited conduct, compliance obligations |
| Fees and Payment | Contract terms, state law | Pricing, billing, refund policy |
| Intellectual Property | Copyright, TM law | Ownership, licenses, restrictions |
| User Content | Contract terms, DMCA | Licenses, responsibility, takedown |
| Disclaimers | UCC, consumer protection | AS-IS, warranty disclaimers |
| Limitation of Liability | State law, consumer protection | Caps, exclusions, carve-outs |
| Indemnification | Contract terms | Scope, triggers, process |
| Dispute Resolution | FAA, state law | Arbitration, class waiver, venue |
| Termination | Contract terms | Grounds, process, effect |
| Governing Law | Conflict of laws | Jurisdiction, choice of law |
| Miscellaneous | Contract terms | Severability, assignment, notices, entire agreement |

Adapt the structure to the specific policy type if not privacy or ToS.

### Step 6: Draft the Policy

Write the full policy document:
- Use clear, plain language appropriate for the audience
- For external-facing policies: prioritize readability while meeting legal requirements
- For internal policies: can be more technical and prescriptive
- Include all legally required provisions identified in Step 4
- Flag provisions where business decisions are needed with [DECISION NEEDED: description]

### Step 7: If Updating -- Generate Change Summary

If updating an existing policy, provide:

| Section | Change Type | Description | Reason |
|---------|-----------|-------------|--------|
| [section] | Added / Modified / Deleted | [what changed] | [why -- legal requirement, product change, clarification] |

### Step 8: Flag Stakeholder Decisions

Identify provisions requiring business or executive input:

| Decision | Options | Recommendation | Stakeholder |
|----------|---------|---------------|-------------|
| [e.g., arbitration vs. litigation] | [option A / option B] | [recommended option with rationale] | [legal / product / executive] |
| [e.g., data retention period] | [30 days / 90 days / 1 year] | [recommended with rationale] | [product / security / legal] |

### Step 9: Generate Output (If Connected)

If ~~office suite is connected, offer to:
- Generate the policy as a formatted document (DOCX)
- If updating, generate a redlined version showing changes

If ~~cloud storage is connected, offer to save the draft to the appropriate location.

If ~~chat is connected and the user requests it:
- Post a summary of the policy draft and items requiring stakeholder input to the relevant channel

## Output Format

```
## Policy Draft Summary

**Policy Type**: [privacy policy / ToS / AUP / other]
**Audience**: [external users / employees / vendors / other]
**Jurisdictions**: [which jurisdictions covered]
**Status**: [new draft / update to version dated [date]]
**Legal Frameworks Applied**: [GDPR, CCPA, COPPA, DMCA, etc.]

## Legal Requirements Matrix

| Requirement | Source | Mandatory? | Addressed in Section |
|------------|--------|-----------|---------------------|
| [requirement] | [law/regulation] | [yes/no] | [section reference] |

---

## [POLICY TITLE]

**Effective Date**: [date or placeholder]
**Last Updated**: [date]

[Full draft policy document with all sections]

---

## Legal Requirements Notes

[Provisions driven by specific legal requirements, with citations to the applicable law]

## Change Summary (If Update)

| Section | Change | Reason |
|---------|--------|--------|
| [section] | [what changed] | [why] |

## Items Requiring Stakeholder Review

| # | Decision | Options | Recommendation | Stakeholder | Deadline |
|---|----------|---------|---------------|-------------|----------|
| 1 | [decision] | [options] | [recommendation] | [who] | [when] |

## Implementation Steps

| Step | Owner | Deadline |
|------|-------|----------|
| [e.g., engineering review for data practices accuracy] | [who] | [when] |
| [e.g., update website/app] | [who] | [when] |
| [e.g., notify users of changes] | [who] | [when] |
```

## Notes

- Policy type can include: privacy policy, terms of service, acceptable use policy, code of conduct, data retention policy, incident response policy, cookie policy, DMCA policy, whistleblower policy, and others
- External-facing policies (e.g., privacy policy, ToS) have specific legal content requirements that vary by jurisdiction. Missing a required provision can create regulatory exposure.
- If updating an existing policy, identify and explain all changes from the prior version. Some changes may require user notification (e.g., material changes to privacy policy or ToS).
- For policies that require user consent, ensure the consent mechanism meets applicable legal standards (e.g., GDPR requirements for consent).
- If the policy covers multiple jurisdictions, note where requirements conflict and how the policy resolves those conflicts.
- For very long policies (e.g., comprehensive ToS), consider whether a layered approach (short summary + full terms) would be more effective.
- If the policy is in a language other than English or needs translation, note this and flag translation requirements.

## After Completion

Suggest knowledge updates if relevant:
- **Legal knowledge update**: "This policy required research into [topic] -- should I update the legal knowledge base?"
- **Template creation**: "This policy could serve as a template for future use -- should I add it to templates?"
- **Decision log**: "Should I log the stakeholder decisions made during this policy draft in memory?"
- **Compliance update**: "This policy creates new compliance obligations -- should I update the compliance tracking?"
