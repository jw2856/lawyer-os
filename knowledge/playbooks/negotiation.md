# Negotiation Playbook

## When This Applies

When negotiating the terms of an agreement — whether responding to a counterparty's paper, proposing modifications to standard T&Cs, or drafting counter-proposals.

## Required Context

- **Always**: `core/principles.md`, `core/standards.md`
- **By topic**: Relevant legal knowledge from `reference/legal-knowledge/`
- **By entity**: Check `contexts/_index.md` for the relationship type, load relevant context files

## Methodology

This process is adapted from our standard review methodology:

### Step 1: Understand the Structure

- What's the agreement structure? (Single agreement, MSA + SOW, T&C + Order Document, etc.)
- Where do modifications go? (Direct redlines to the agreement, or via a separate amendment/order document?)
- What's their paper vs our paper? (Counterparty template requires more scrutiny)
- What's the timeline? (Urgency affects how aggressive we negotiate)

### Step 2: Section-by-Section Review

Go through the agreement section by section:

1. Read the section
2. Compare to our standard position in `core/standards.md`
3. Compare to positions in comparable executed agreements (check `contexts/` for precedents)
4. Identify gaps, risks, or terms less favorable than our standards
5. Classify each finding as GREEN / YELLOW / RED

### Step 3: Propose Revisions

For each YELLOW/RED item, prepare:

- **The issue**: What the current language says and why it's problematic
- **Our proposed revision**: Specific language to replace or supplement
- **Rationale**: Why we're asking for the change (brief, professional)
- **Fallback position**: What we'd accept if they reject our proposal
- **Business context**: Whether this is a deal-breaker or a negotiation point

### Step 4: Apply Standard Patterns

Apply these recurring negotiation patterns:

#### One-Sided Indemnity Carve-Outs
Wherever we are required to indemnify the counterparty, add carve-out excluding losses caused by:
- Counterparty's negligence, error, or willful misconduct
- Counterparty's failure to comply with applicable law or the agreement
- Acts/omissions of counterparty's network partners, sub-processors, or third-party providers

#### Missing Protections
Check that the agreement includes provisions we expect even if not explicitly in their template:
- Cure period before termination for cause
- Notice requirements for material changes
- Confidentiality survival post-termination
- Data protection / DPA
- Fund segregation (if applicable per `core/standards.md`)
- Non-exclusivity

#### Problematic Provisions
Flag and push back on:
- Unilateral amendment rights
- Exclusivity or non-compete
- Uncapped liability
- Immediate termination without cure
- Auto-renewal without adequate notice period
- Broad assignment rights without consent

### Step 5: Package the Output

Depending on the negotiation structure:

**For direct redlines:**
- Prepare a clause-by-clause markup with tracked changes
- Include brief margin comments explaining each change

**For Order Document / Amendment modifications:**
- Group changes by section reference
- For each change: state the T&C provision, describe the issue, propose the Order Document variation
- Include rationale for each variation

**For a negotiation memo (internal):**
```
## Negotiation Summary: [Agreement Name]

### Overall Assessment
[HIGH/MEDIUM/LOW concern]

### Key Issues (Priority Order)

#### 1. [Issue — Tier 1]
- Current: [what they want]
- Proposed: [what we want]
- Fallback: [minimum acceptable]
- Rationale: [why this matters]

[Repeat for each issue]

### Concessions Available
[Items where we have flexibility and could offer as part of a package deal]

### Business Questions
[Items requiring business input]

### Recommended Strategy
[Approach for the negotiation — what to lead with, what to hold back, what to concede]
```

## Negotiation Principles

- **Lead with high-priority items** — don't dilute important asks with trivial ones
- **Bundle concessions** — give ground on Tier 3 items when asking for Tier 1 items
- **Reference market standard** — "this is consistent with market practice" carries weight
- **Reference our other agreements** — "we've agreed to this structure with X other partners" (use carefully)
- **Avoid ultimatums** — always frame requests as reasonable and commercial
- **Document everything** — keep a running record of what was proposed, accepted, rejected
