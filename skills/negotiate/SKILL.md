---
name: negotiate
description: "Negotiate, redline, or propose changes to an agreement — generate position-by-position markup with business rationale and fallback positions. Use when the user needs to negotiate contract terms, create redlines, or develop a negotiation strategy."
---

# Agreement Negotiation

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Negotiate an agreement by analyzing counterparty terms against your standards, generating redlines or proposed variations, and building a negotiation strategy with prioritized positions and fallbacks.

## Workflow

### Step 1: Accept the Agreement

Accept the agreement in any of these formats:
- **File path**: Local PDF, DOCX, or other document
- **URL**: Link to a document in ~~cloud storage or other document system
- **Pasted text**: Agreement text pasted directly into the conversation

If no agreement is provided, prompt the user to supply one.

### Step 2: Gather Context

Ask the user for context before beginning the negotiation analysis:

1. **Which side are you on?** (vendor/supplier, customer/buyer, licensor, licensee, partner -- or other)
2. **What is the negotiation structure?** (direct redlines to their paper, Order Document/schedule of variations, amendment, or separate counter-proposal)
3. **What is the priority?** (speed-to-close, maximum protection, balanced/market, or relationship-preserving)
4. **Redlines vs. fresh paper**: Are we marking up their draft, or should we propose our own template?
5. **Deal context**: Deal size, strategic importance, existing relationship, leverage dynamics
6. **Focus areas**: Any specific concerns or must-haves? (e.g., "IP ownership is non-negotiable", "we need unlimited liability carve-outs for IP infringement")

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the negotiation analysis:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/standards.md` — Default clause positions
- `knowledge/playbooks/negotiation.md` — Negotiation process and tactics

**Load by agreement type** (infer from document, or use the user's override):
- Check `knowledge/contexts/_index.md` to determine the relationship type
- Load the relevant overview file and specific entity file if one exists

If a context file has a **Standards Overrides** section, those override `standards.md` defaults.

**Load reference material as needed:**
- `knowledge/reference/comparison-tables/` — Cross-entity precedent (what have we accepted before?)
- `knowledge/reference/clause-library/` — Pre-approved counter-language
- Relevant legal knowledge from `knowledge/reference/legal-knowledge/` based on subject matter

### Step 4: Understand the Agreement Structure

Before marking up, determine:
- Where do modifications go? (direct redlines, Order Document, amendment, exhibit, side letter)
- Does the agreement have a hierarchy clause? (e.g., "in case of conflict, the Order Document prevails")
- Are there incorporated documents? (e.g., DPA, SLA, AUP that may also need review)
- What is the amendment mechanism? (for existing agreements being renegotiated)

### Step 5: Section-by-Section Analysis

Analyze the agreement systematically against standards (with overrides):

| Clause Category | Key Negotiation Points |
|----------------|----------------------|
| **Limitation of Liability** | Cap amount, carve-outs, mutual vs. unilateral, consequential damages, super-cap items |
| **Indemnification** | Scope, mutual vs. unilateral, cap, IP infringement, data breach, carve-outs for counterparty fault |
| **IP Ownership** | Pre-existing IP, developed IP, work-for-hire, license grants, assignment, background IP protection |
| **Data Protection** | DPA requirement, processing terms, sub-processors, breach notification, cross-border transfers |
| **Confidentiality** | Scope, term, carve-outs, return/destruction obligations, residuals |
| **Representations & Warranties** | Scope, compliance with laws, authority, disclaimers, knowledge qualifiers |
| **Term & Termination** | Duration, renewal, termination for convenience/cause, cure periods, wind-down, transition assistance |
| **Governing Law & Dispute Resolution** | Jurisdiction, venue, arbitration vs. litigation, prevailing party fees |
| **Insurance** | Coverage requirements, minimums, evidence of coverage |
| **Assignment & Change of Control** | Consent requirements, thresholds, exceptions for affiliates/restructuring |
| **Force Majeure** | Scope, notification, termination rights, fee relief |
| **Fees & Payment Terms** | Net terms, fee changes, late fees, taxes, minimum commitments, most-favored-customer |
| **SLA & Service Levels** | Uptime commitments, credits, measurement methodology, exclusions |

For each clause, classify as GREEN / YELLOW / RED and note the gap between their position and your standard.

### Step 6: Propose Revisions

For each YELLOW and RED item, provide:
- **Their language**: Quote the relevant contract text
- **Your standard position**: What your standards say
- **Proposed revision**: Specific alternative language ready to insert
- **Rationale for counterparty**: Explanation suitable for sharing with the other side
- **Fallback position**: Minimum acceptable alternative if they push back
- **Priority**: Tier 1 (must-have), Tier 2 (strong preference), or Tier 3 (nice-to-have / tradeable concession)

Apply the **one-sided indemnity pattern**: wherever you must indemnify, add carve-out for counterparty's own negligence, error, willful misconduct, or failure to comply with law/agreement.

### Step 7: Business Impact Summary

Provide a summary covering:
- **Overall assessment**: How far is this agreement from your standards?
- **Top 3 issues**: The most important items to negotiate
- **Exposure analysis**: What is the practical business impact of accepting each RED/YELLOW item as-is?
- **Negotiation strategy**: Which issues to lead with, what to concede, sequencing of asks
- **Leverage assessment**: What is your bargaining position? What does the counterparty likely care most about?
- **Timeline considerations**: Can this be negotiated within the deal timeline?

### Step 8: Package Output

Package the negotiation output in the format matching the negotiation structure:

**If redlines**: Generate a clause-by-clause markup with tracked-changes-style formatting. If ~~office suite is connected, offer to apply redlines directly to the document.

**If Order Document / Schedule of Variations**: Generate a structured table of section references and proposed variation language.

**If counter-proposal**: Generate a complete counter-draft using the appropriate template from the clause library.

**If internal negotiation memo**: Generate a priority-ordered issues list with positions, fallbacks, and strategy.

### Step 9: Post to Chat (If Connected)

If ~~chat is connected and the user requests it:
- Post a negotiation summary to the relevant channel
- Include overall assessment, top issues, and recommended next steps

## Output Format

Depending on negotiation structure, produce one of:

**Redlines:**
```
## Negotiation Summary

**Document**: [agreement name/identifier]
**Parties**: [party names and roles]
**Your Side**: [vendor/customer/etc.]
**Negotiation Structure**: [redlines/Order Document/counter-proposal]
**Priority**: [speed/protection/balanced/relationship]
**Review Basis**: [Standards + any overrides applied]

## Key Findings

[Top 3-5 issues with severity flags and business impact]

## Clause-by-Clause Markup

### [Clause Category] -- [GREEN/YELLOW/RED] -- [Tier 1/2/3]
**Their language**: "[quote from agreement]"
**Your standard**: [from standards.md]
**Proposed revision**: "[specific alternative language]"
**Rationale**: [explanation for counterparty]
**Fallback**: [minimum acceptable position]
**Business impact if accepted as-is**: [practical consequence]

[Repeat for each clause requiring changes]

## Negotiation Strategy

**Lead with**: [which issues to raise first]
**Concession candidates**: [Tier 3 items you can trade]
**Sequencing**: [recommended order of discussion]
**Leverage points**: [what strengthens your position]

## Next Steps

[Specific actions to take]
```

**Order Document / Amendment:**
```
## Proposed Variations to [Agreement Name]

| Section Reference | Current Provision | Proposed Variation | Rationale | Priority |
|------------------|-------------------|-------------------|-----------|----------|
| [section number] | [summary of current] | [proposed language] | [why] | [Tier 1/2/3] |

## Strategy Notes

[Overall approach and key talking points]
```

**Internal Negotiation Memo:**
```
PRIVILEGED AND CONFIDENTIAL

## Priority-Ordered Issues

### Issue 1: [Name] -- [RED/YELLOW] -- Tier [1/2/3]
**Proposed position**: [what to ask for]
**Fallback position**: [minimum acceptable]
**Walk-away point**: [when to escalate]
**Concessions available**: [what to trade if needed]

[Repeat for each issue]

## Recommended Strategy

[Overall negotiation approach, sequencing, tone, and timeline]

## Concession Map

[What you can give up and what you should get in return]
```

## Notes

- If the agreement is in a language other than English, note this and ask if the user wants negotiation analysis in the original language or translated
- For very long agreements (50+ pages), offer to prioritize the most material sections first
- If the user specifies focus areas, prioritize those but still flag material issues in other sections
- Cross-reference precedent from comparison tables where available -- knowing what you have accepted before strengthens or constrains your position
- Always provide rationale for each proposed change suitable for sharing with the counterparty's counsel
- If ~~office suite is connected, offer to generate the redlined document directly

## After Completion

Suggest knowledge updates if relevant:
- **Clause language**: "This counter-language worked well -- should I add it to the clause library?"
- **Negotiation pattern**: "This negotiation approach was effective -- should I note it in lessons-learned?"
- **Precedent**: "We accepted [position] with [counterparty] -- should I update the comparison table?"
- **New context**: "First time negotiating with [counterparty] -- should I create a context file?"
- **Decision/exception**: "Should I log this negotiation outcome in memory?"
