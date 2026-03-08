# Contract Review Playbook

## When This Applies

Any time you're reviewing a contract, agreement, or set of terms for your organization — whether partner, vendor, customer, or other.

## Required Context

Before starting, load:
- **Always**: `core/principles.md`, `core/standards.md`
- **By topic**: Relevant legal knowledge from `reference/legal-knowledge/` based on the subject matter of the agreement
- **By entity**: The relevant partner/vendor context file if it exists in `contexts/`
- **Checklist**: `reference/checklists/contract-review-checklist.md`

## Process

### Step 1: Identify & Classify

Before reading the contract in detail, establish context:

- **What type of agreement is this?** Check `contexts/_index.md` for your relationship categories (e.g., partner, vendor, customer, NDA, corporate, advisory)
- **Who is the counterparty?** Do we have existing context in `contexts/`?
- **Which entity should sign?** (see `core/organization.md` for entity routing guidance)
- **What is the business context?** Why are we entering this agreement? What's the strategic importance?
- **What's the importance level?** Strategic/high-value → full scrutiny. Routine/low-value → focus on Tier 1 items.

### Step 2: Read & Extract Key Terms

Read the full agreement and extract a structured summary of key terms:

- Parties and effective date
- Term, renewal, and termination provisions
- Services/scope description
- Fees, payment terms, and commercial structure
- Limitation of liability (cap amount, carveouts, consequential damages exclusion)
- Indemnification (mutual vs one-sided, triggers, caps)
- Termination rights (for cause, for convenience, cure periods, notice requirements)
- SLAs/performance standards (if applicable — uptime, latency, settlement times)
- Data protection (DPA, breach notification, security requirements, controller/processor)
- IP and confidentiality (ownership, license scope, survival period)
- Dispute resolution (governing law, mechanism, seat/venue)
- Assignment and change of control
- Insurance requirements
- Exclusivity or non-compete provisions
- Force majeure
- Notable, unusual, or problematic provisions

### Step 3: Compare Against Standards

For each extracted term, compare against `core/standards.md`:

- **GREEN**: Aligns with or better than our standard position
- **YELLOW**: Deviation from standard but within acceptable range per `standards.md`
- **RED**: Outside acceptable range, or an escalation trigger is hit

Also identify:
- Terms **missing** from the agreement that our standards require
- Terms **present** that shouldn't be (non-competes, exclusivity, unilateral amendments)
- Provisions that are **ambiguous** and could be interpreted unfavorably

### Step 4: Generate Recommendations

For each YELLOW or RED item:

1. **State the issue clearly** — what the contract says and why it's a problem
2. **Explain the business impact** — what could go wrong in plain language
3. **Propose specific counter-language** — actual contract text we'd want to see
4. **Note a fallback position** — what we'd accept if the counter is rejected
5. **Classify priority** — Tier 1 (must-have), Tier 2 (strong preference), Tier 3 (nice-to-have)

Apply the **one-sided indemnity pattern** from `principles.md`: wherever we're required to indemnify, add carve-out for counterparty's own negligence, error, willful misconduct, or failure to comply with law/agreement.

### Step 5: Write the Output

Format as a structured review memo:

```
## Contract Review: [Agreement Name]
Date: [date]
Reviewer: [name]
Status: PRIVILEGED — Attorney-Client Communication

### Executive Summary
Overall classification: [GREEN / YELLOW / RED]
[2-3 sentence summary of key findings and recommendation]

### Key Issues

#### [Issue 1 — RED/YELLOW]
**Current language**: [quote from contract]
**Issue**: [what's wrong and why]
**Business impact**: [plain language risk]
**Recommended change**: [specific counter-language]
**Fallback**: [minimum acceptable alternative]
**Priority**: Tier [1/2/3]

[Repeat for each issue]

### Full Term Summary
[Structured extraction from Step 2]

### Business Questions
[Items requiring business team input or escalation]

### Recommended Next Steps
[Specific actions: redline and return, negotiate specific items, escalate, approve as-is]
```

## Calibration by Deal Type

- **Strategic/high-value deals**: Every clause gets full scrutiny. Run all checklist items. Consider running debate mode on RED items.
- **Routine/low-value deals**: Focus on Tier 1 items. Flag but don't deep-dive Tier 2-3 unless something jumps out.
- **Renewals/amendments**: Focus on what's changed from the original. Review any new terms against standards.
- **Counterparty paper** (their template): More scrutiny needed — their template will favor them. Pay extra attention to indemnification asymmetry, liability imbalances, and unusual provisions.
- **Our paper** (your organization's template): Lighter review — focus on counterparty's requested modifications.
