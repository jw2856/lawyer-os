---
description: Review a contract against your standards — flag deviations, generate redlines, provide business impact analysis
argument-hint: "<contract file, URL, or text>"
---

# /lawyer-os:review -- Contract Review

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Review a contract against your organization's standards. Analyze each clause, flag deviations, generate redline suggestions, and provide business impact analysis.

## Invocation
```
/lawyer-os:review [file path, URL, or pasted text]
```

## Workflow

### Step 1: Accept the Contract

Accept the contract in any of these formats:
- **File path**: Local PDF, DOCX, or other document
- **URL**: Link to a contract in ~~cloud storage or other document system
- **Pasted text**: Contract text pasted directly into the conversation

If no contract is provided, prompt the user to supply one.

### Step 2: Gather Context

Ask the user for context before beginning the review:

1. **Which side are you on?** (vendor/supplier, customer/buyer, licensor, licensee, partner — or other)
2. **Deadline**: When does this need to be finalized? (Affects prioritization)
3. **Focus areas**: Any specific concerns? (e.g., "data protection is critical", "we need flexibility on term")
4. **Deal context**: Any relevant business context? (e.g., deal size, strategic importance, existing relationship)

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the review:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/standards.md` — Default clause positions
- `knowledge/playbooks/contract-review.md` — Step-by-step review process
- `knowledge/reference/checklists/contract-review-checklist.md` — Completeness checklist

**Load by agreement type** (infer from document, or use the user's override):
- Check `knowledge/contexts/_index.md` to determine the relationship type
- Load the relevant overview file and specific entity file if one exists
- Common patterns: partner agreements, vendor/SaaS, customer — but your organization may have different categories

If a context file has a **Standards Overrides** section, those override `standards.md` defaults.

**Load reference material as needed:**
- Relevant legal knowledge from `knowledge/reference/legal-knowledge/` based on subject matter
- Clause library from `knowledge/reference/clause-library/` for counter-language
- Comparison tables from `knowledge/reference/comparison-tables/` for cross-entity precedent

### Step 4: Clause-by-Clause Analysis

Analyze the contract systematically, following the playbook. Cover at minimum:

| Clause Category | Key Review Points |
|----------------|-------------------|
| **Limitation of Liability** | Cap amount, carveouts, mutual vs. unilateral, consequential damages |
| **Indemnification** | Scope, mutual vs. unilateral, cap, IP infringement, data breach |
| **IP Ownership** | Pre-existing IP, developed IP, work-for-hire, license grants, assignment |
| **Data Protection** | DPA requirement, processing terms, sub-processors, breach notification, cross-border transfers |
| **Confidentiality** | Scope, term, carveouts, return/destruction obligations |
| **Representations & Warranties** | Scope, compliance with laws, authority, disclaimers |
| **Term & Termination** | Duration, renewal, termination for convenience/cause, cure periods, wind-down |
| **Governing Law & Dispute Resolution** | Jurisdiction, venue, arbitration vs. litigation |
| **Insurance** | Coverage requirements, minimums, evidence of coverage |
| **Assignment & Change of Control** | Consent requirements, thresholds, exceptions |
| **Force Majeure** | Scope, notification, termination rights |
| **Fees & Payment Terms** | Net terms, fee changes, late fees, taxes, minimum commitments |

For each clause, assess against the standards (with overrides) and note whether it is present, absent, or unusual.

### Step 5: Flag Deviations

Classify each deviation using a three-tier system:

**GREEN — Acceptable**
- Aligns with or better than standard position
- Minor variations that are commercially reasonable
- No action needed; note for awareness

**YELLOW — Negotiate**
- Falls outside standard but within acceptable range
- Include: specific redline language to bring back to standard
- Include: fallback position if counterparty pushes back
- Include: business impact of accepting as-is vs. negotiating

**RED — Escalate**
- Falls outside acceptable range or triggers escalation criterion
- Include: why this is a RED flag (specific risk)
- Include: what the standard market position looks like
- Include: business impact and potential exposure
- Include: recommended escalation path

### Step 6: Generate Redline Suggestions

For each YELLOW and RED deviation, provide:
- **Current language**: Quote the relevant contract text
- **Suggested redline**: Specific alternative language ready to insert
- **Rationale**: Brief explanation suitable for sharing with counterparty
- **Priority**: Tier 1 (must-have), Tier 2 (strong preference), or Tier 3 (nice-to-have)

Apply the **one-sided indemnity pattern**: wherever we must indemnify, add carve-out for counterparty's own negligence, error, willful misconduct, or failure to comply with law/agreement.

### Step 7: Business Impact Summary

Provide a summary covering:
- **Overall risk assessment**: High-level view of the contract's risk profile
- **Top 3 issues**: The most important items to address
- **Negotiation strategy**: Which issues to lead with, what to concede
- **Timeline considerations**: Any urgency factors

### Step 8: Post to Chat (If Connected)

If ~~chat is connected and the user requests it:
- Post a summary of the review to the relevant channel
- Include overall classification, top issues, and next steps

## Output Format

```
## Contract Review Summary

**Document**: [contract name/identifier]
**Parties**: [party names and roles]
**Your Side**: [vendor/customer/etc.]
**Deadline**: [if provided]
**Review Basis**: [Standards + any overrides applied]

## Key Findings

[Top 3-5 issues with severity flags]

## Clause-by-Clause Analysis

### [Clause Category] — [GREEN/YELLOW/RED]
**Contract says**: [summary of the provision]
**Standard position**: [from standards.md]
**Deviation**: [description of gap]
**Business impact**: [what this means practically]
**Redline suggestion**: [specific language, if YELLOW or RED]
**Fallback**: [minimum acceptable alternative, if YELLOW or RED]

[Repeat for each major clause]

## Negotiation Strategy

[Recommended approach, priorities, concession candidates]

## Next Steps

[Specific actions to take]
```

## Notes

- If the contract is in a language other than English, note this and ask if the user wants a translation or review in the original language
- For very long contracts (50+ pages), offer to focus on the most material sections first and then do a complete review
- If the user specifies focus areas, prioritize those sections but still review the full agreement
- If the user overrides the agreement type, use that classification instead of inferring

## After Completion

Suggest knowledge updates if relevant:
- **Clause language**: "This counter-language worked well — should I add it to the clause library?"
- **Standards gap**: "This review surfaced a clause type not covered in standards — should I add it?"
- **New context**: "First time reviewing [counterparty] — should I create a context file?"
- **Decision/exception**: "Should I log this in memory?"
