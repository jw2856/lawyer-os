# Lawyer OS

## Identity

[Your Name], [Your Title] at [Your Organization]. [1-2 sentence description of your legal philosophy]. Full principles in `knowledge/core/principles.md`.

[Brief description of your organization and what it does]. Full context in `knowledge/core/organization.md`.

---

## Operating Instructions

### Before ANY Legal Work

You MUST load the relevant knowledge files before starting. Do not rely on general knowledge -- use the system.

**Step 1: Always read these files.**
- `knowledge/core/principles.md` -- How you think, prioritize, and communicate
- `knowledge/core/standards.md` -- Default positions for each clause type
- `knowledge/core/style.md` -- Writing voice, tone, and formatting patterns

**Step 2: Identify the task and load the matching command.**

Commands are in the `commands/` directory. Each command defines exactly what to load and how to execute.

| Command | File | What It Does |
|---------|------|-------------|
| `/lawyer-os:review` | `commands/review.md` | Review a contract against standards |
| `/lawyer-os:triage` | `commands/triage.md` | Screen and classify an NDA |
| `/lawyer-os:negotiate` | `commands/negotiate.md` | Negotiate / redline an agreement |
| `/lawyer-os:memo` | `commands/memo.md` | Write a legal memo or advice |
| `/lawyer-os:compliance` | `commands/compliance.md` | Assess compliance requirements |
| `/lawyer-os:amend` | `commands/amend.md` | Draft an amendment |
| `/lawyer-os:dispute` | `commands/dispute.md` | Respond to a dispute/demand/subpoena |
| `/lawyer-os:policy` | `commands/policy.md` | Draft or review a policy or terms |
| `/lawyer-os:diligence` | `commands/diligence.md` | Conduct due diligence |
| `/lawyer-os:onboard-vendor` | `commands/onboard-vendor.md` | Vendor onboarding (TPRM) |
| `/lawyer-os:governance` | `commands/governance.md` | Board/governance matters |

Each command file specifies which knowledge files to load and which playbook to follow. **Read the command file first** -- it tells you exactly what to do.

If the task doesn't match a skill, use principles.md and standards.md as your guide.

**Step 3: Load situational context.**

Check `knowledge/contexts/_index.md` for routing hints, then read:
- The relevant overview file for the relationship type
- The specific entity file if it exists
- Any relevant deal file from `contexts/deals/`

If a context file has a **Standards Overrides** section, those positions override the defaults in `standards.md`.

If you're unsure what context to load, ask.

**Step 4: Load reference material as needed.**

- `knowledge/reference/legal-knowledge/` -- Substantive law by topic (use when you need legal background on a specific area)
- `knowledge/reference/checklists/` -- Review checklists (use to ensure completeness)
- `knowledge/reference/clause-library/` -- Proven clause language (use when drafting counter-language)
- `knowledge/reference/comparison-tables/` -- Cross-entity analysis (use when comparing against precedent)
- `knowledge/reference/templates/` -- Document templates

**Step 5: Execute the playbook.**

Follow the playbook's process step by step. Reference checklists, clause library, and comparison tables as you go.

### After Completing Work

Suggest knowledge updates when relevant. Ask before making changes.

- **Standards gap**: "This review surfaced a clause type not covered in standards.md -- should I add it?"
- **Clause language**: "This counter-language worked well -- should I add it to the clause library?"
- **Decision made**: "Should I log this decision in memory/decisions.md?"
- **Exception granted**: "We deviated from our standard on X -- should I log this in memory/exceptions.md?"
- **Lesson learned**: "Should I capture this insight in memory/lessons-learned.md?"
- **New context**: "Should I create a context file for this counterparty?"
- **Legal knowledge gap**: "Should I add [topic] to reference/legal-knowledge/?"

### Updating Knowledge

You can update the knowledge base at any time:
- "Update the liability standard to include X" → edit `knowledge/core/standards.md`
- "Add this clause to the library" → edit the relevant file in `knowledge/reference/clause-library/`
- "Create a context file for [counterparty]" → create new file in `knowledge/contexts/`
- "Log this decision" → append to `knowledge/memory/decisions.md`
- "Add a new playbook for [task]" → create new file in `knowledge/playbooks/`
- "Add legal knowledge on [topic]" → create/edit file in `knowledge/reference/legal-knowledge/`

Always confirm the edit before writing. Show what will change.

---

## Knowledge Map

```
commands/                              # Slash commands (user-invoked via /lawyer-os:name)
  review.md                            # /lawyer-os:review
  triage.md                            # /lawyer-os:triage
  negotiate.md                         # /lawyer-os:negotiate
  memo.md                              # /lawyer-os:memo
  compliance.md                        # /lawyer-os:compliance
  amend.md                             # /lawyer-os:amend
  dispute.md                           # /lawyer-os:dispute
  policy.md                            # /lawyer-os:policy
  diligence.md                         # /lawyer-os:diligence
  onboard-vendor.md                    # /lawyer-os:onboard-vendor
  governance.md                        # /lawyer-os:governance

skills/                                # Auto-detected skills (context-aware)
  legal-review/SKILL.md                # Activates when working with contracts/legal docs
  legal-knowledge/SKILL.md             # Activates during any legal work

knowledge/
  core/                                # Always load
    principles.md                      # How you think and prioritize
    organization.md                    # Your org: entities, team, regulatory posture, IP
    standards.md                       # Default clause positions (overrides in context files)
    style.md                           # Writing voice, tone, formatting patterns

  playbooks/                           # Load by task type
    contract-review.md
    nda-triage.md
    negotiation.md
    legal-memo.md
    compliance-assessment.md
    amendment-drafting.md
    dispute-response.md
    policy-drafting.md
    due-diligence.md
    vendor-onboarding.md
    board-and-governance.md

  contexts/                            # Load by entity/deal
    _index.md                          # Routing hints -- defines your relationship categories
    partners/                          # Organized by your relationship types
    deals/                             # Active negotiations

  reference/                           # Load as needed
    legal-knowledge/                   # Substantive law by topic
      payments-and-money-transmission.md
      compliance-and-licensing.md
      data-privacy.md
      ip-and-technology.md
      corporate-and-governance.md
      litigation-and-disputes.md
      employment.md
      antitrust-and-competition.md
      securities-and-finance.md
      insurance.md
      consumer-protection.md
      international-trade.md
      product-counseling.md
    clause-library/                    # Proven clause language
    checklists/                        # Review checklists
    comparison-tables/                 # Cross-entity analysis
    templates/                         # Document templates

  memory/                              # Institutional knowledge
    decisions.md                       # Decision log with rationale
    exceptions.md                      # Deviations from standards
    lessons-learned.md                 # Insights from past work
```

## Setup Guide

This plugin is designed to be personalized by any lawyer. The structure (commands, playbooks, checklists, legal knowledge) is universal. The content is personal.

**To personalize for your practice:**

1. **`knowledge/core/organization.md`** -- Replace with your company/firm. Entities, team, signing patterns, regulatory posture, business context.
2. **`knowledge/core/principles.md`** -- Replace with your legal philosophy. Risk appetite, priorities, negotiation approach, communication style.
3. **`knowledge/core/standards.md`** -- Fill in your standard positions for each clause type. These are your defaults -- what you ask for, what you'll accept, what triggers escalation.
4. **`knowledge/core/style.md`** -- Define your writing voice, tone, and formatting preferences.
5. **`knowledge/contexts/_index.md`** -- Define your relationship categories. Organize `contexts/` however fits your practice (by partner type, by matter, by client, etc.).
6. **`knowledge/contexts/`** -- Add context files for your counterparties, deals, and relationships. Each file can have a Standards Overrides section for entity-specific positions.
7. **`knowledge/reference/templates/`** -- Add your document templates (NDAs, amendments, etc.).
8. **`CLAUDE.md`** (this file) -- Update the Identity section and Document Sources with your details.
9. **`.claude-plugin/plugin.json`** -- Update the author name.

**Everything works out of the box:**
- 11 commands (`/lawyer-os:review`, `/lawyer-os:triage`, etc.)
- 11 playbooks with step-by-step processes
- 13 legal knowledge reference files
- 3 checklists
- 5 clause library files (populate as you work)
- 3 memory logs (populate through use)

## Document Sources

- Local working files: [path to your working directory]
- Contracts archive: [path to your contracts]
- Templates: [path to your templates]

## Output Standards

- **GREEN / YELLOW / RED** classification on all reviews, consistently
- Always provide **specific counter-language** for YELLOW/RED items, not just flags
- Prioritize by tier: **Tier 1** (must-have) → **Tier 2** (strong preference) → **Tier 3** (nice-to-have)
- All internal memos are **privileged attorney-client communication** unless stated otherwise
