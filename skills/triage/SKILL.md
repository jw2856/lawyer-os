---
name: triage
description: "Screen and triage an NDA for quick classification and routing — flag risk areas, generate counter-language, provide business impact analysis. Use when the user uploads or shares an NDA for screening or quick triage."
---

# NDA Triage

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Screen an NDA against your organization's standards. Classify each section, flag deviations, generate counter-language for problem areas, and recommend routing.

## Workflow

### Step 1: Accept the NDA

Accept the NDA in any of these formats:
- **File path**: Local PDF, DOCX, or other document
- **URL**: Link to a document in ~~cloud storage or other document system
- **Pasted text**: NDA text pasted directly into the conversation

If no NDA is provided, prompt the user to supply one.

### Step 2: Gather Context

Ask the user for context before beginning the triage:

1. **Who is the counterparty?** (company name, industry, size if known)
2. **What is the business relationship?** (potential partner, vendor, customer, investor, acquirer, other)
3. **Who sent it?** (did they send their paper, or is this our template?)
4. **Urgency**: How quickly does this need to be turned around?
5. **Special concerns**: Anything specific to watch for? (e.g., "they want broad non-solicit", "we're sharing source code")

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the triage:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/standards.md` — Default clause positions
- `knowledge/playbooks/nda-triage.md` — Step-by-step triage process
- `knowledge/reference/checklists/nda-screening-checklist.md` — 11-section screening checklist

**Load contextual knowledge:**
- If counterparty has an existing context file, load it
- `knowledge/reference/templates/_overview.md` — For template references if a counter-proposal is needed
- `knowledge/reference/clause-library/` — For counter-language on flagged items

If a context file has a **Standards Overrides** section, those override `standards.md` defaults.

### Step 4: Run the 11-Section Screening Checklist

Follow `knowledge/playbooks/nda-triage.md` step by step. Analyze each section systematically:

| Section | Key Screening Points |
|---------|---------------------|
| **Definition of Confidential Information** | Scope breadth, carve-outs, residuals clause, exclusions |
| **Permitted Use / Purpose** | Narrow vs. broad purpose, alignment with deal context |
| **Obligations of Receiving Party** | Standard of care, permitted disclosures, compelled disclosure |
| **Term & Duration** | NDA term, survival of obligations, perpetual vs. time-limited |
| **Non-Solicitation** | Scope (employees, customers, vendors), duration, breadth |
| **Non-Compete** | Presence, scope, enforceability concerns |
| **Residuals** | Knowledge retained in unaided memory, scope of carve-out |
| **Return / Destruction** | Trigger, timeline, certification requirement, backup exceptions |
| **Remedies** | Injunctive relief presumption, liquidated damages, indemnification |
| **Governing Law & Venue** | Jurisdiction, venue, arbitration vs. litigation |
| **Miscellaneous** | Assignment, amendment, integration, counterparts, notices |

For each section, classify as GREEN / YELLOW / RED.

### Step 5: Determine Overall Classification

Aggregate section ratings into an overall classification:

**GREEN -- Standard Approval**
- All sections GREEN, or minor YELLOW items only
- Can be signed with minimal or no changes
- Routing: standard approval workflow

**YELLOW -- Single Review**
- One or more YELLOW items requiring attention
- Changes recommended but not deal-breaking
- Routing: single reviewer sign-off with suggested edits

**RED -- Full Review + Counter-Proposal**
- One or more RED items present
- Requires substantive negotiation or counter-proposal
- Routing: full legal review with counter-language

### Step 6: Generate Counter-Language

For each YELLOW and RED item, provide:
- **Current language**: Quote the relevant NDA text
- **Issue**: What is wrong and why it matters
- **Suggested counter-language**: Specific alternative language ready to insert
- **Rationale**: Brief explanation suitable for sharing with counterparty
- **Priority**: Tier 1 (must-have), Tier 2 (strong preference), or Tier 3 (nice-to-have)

If RED items are present, identify the appropriate template from `knowledge/reference/templates/` and generate a full counter-proposal.

### Step 7: Business Impact Summary

Provide a summary covering:
- **Overall risk assessment**: What accepting this NDA as-is would mean for the business
- **Top issues**: The most important items to address before signing
- **Counterparty leverage assessment**: How much room is there to negotiate?
- **Recommended approach**: Sign as-is, request targeted edits, or send counter-proposal
- **Timeline considerations**: Can this be turned around within the stated urgency?

### Step 8: Post to Chat (If Connected)

If ~~chat is connected and the user requests it:
- Post a triage summary to the relevant channel
- Include overall classification, top issues, routing recommendation, and next steps

## Output Format

```
## NDA Triage Summary

**Document**: [NDA name/identifier]
**Counterparty**: [counterparty name]
**Relationship**: [partner/vendor/customer/etc.]
**Their Paper or Ours**: [who drafted it]
**Urgency**: [if provided]
**Triage Basis**: [Standards + any overrides applied]

## Overall Classification: [GREEN / YELLOW / RED]

## Per-Section Findings

| Section | Classification | Key Issue | Priority |
|---------|---------------|-----------|----------|
| Definition of Confidential Information | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Permitted Use / Purpose | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Obligations of Receiving Party | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Term & Duration | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Non-Solicitation | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Non-Compete | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Residuals | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Return / Destruction | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Remedies | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Governing Law & Venue | GREEN/YELLOW/RED | [summary] | [if applicable] |
| Miscellaneous | GREEN/YELLOW/RED | [summary] | [if applicable] |

## Risk Scores

[For each YELLOW/RED item: Severity x Likelihood scoring with brief explanation]

## Business Impact

[What accepting this NDA as-is means for the business relationship and operations]

## Routing Recommendation

[Standard approval / Single review / Full review + counter-proposal]
[Who should review and expected turnaround]

## Counter-Language

### [Section Name] -- [YELLOW/RED]
**Current language**: "[quote from NDA]"
**Suggested revision**: "[specific alternative language]"
**Rationale**: [brief explanation for counterparty]
**Priority**: [Tier 1/2/3]

[Repeat for each flagged item]

## Counter-Proposal

[If needed: full counter-proposal using the appropriate template from reference/templates/]

## Next Steps

[Specific actions to take, with owners and deadlines]
```

## Notes

- If the NDA is in a language other than English, note this and ask if the user wants a translation or triage in the original language
- For multi-party NDAs, flag additional complexity and adjust analysis accordingly
- If the counterparty name is not provided, infer it from the document
- The 11 screening sections are defined in the NDA screening checklist; adapt if the NDA has an unusual structure
- If the NDA includes non-standard provisions beyond the 11 sections (e.g., non-compete, standstill, exclusivity), flag these separately as they may require escalation

## After Completion

Suggest knowledge updates if relevant:
- **NDA pattern**: "This NDA had an unusual [clause] -- should I note this pattern in lessons-learned?"
- **Clause language**: "This counter-language worked well -- should I add it to the clause library?"
- **New context**: "First time triaging an NDA from [counterparty] -- should I create a context file?"
- **Decision/exception**: "Should I log this triage decision in memory?"
