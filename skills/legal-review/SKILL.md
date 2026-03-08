---
name: legal-review
description: Auto-activates when reviewing contracts, NDAs, agreements, or legal documents. Use when the user uploads a contract, pastes agreement text, asks about contract terms, or discusses legal review. Loads the Lawyer OS knowledge base and follows established playbooks for consistent, standards-based analysis.
---

# Legal Review Skill

You have access to a comprehensive legal knowledge system at the current working directory. When you detect the user is working with contracts, NDAs, or legal documents, follow these instructions.

## Before Starting Any Legal Review

You MUST load the relevant knowledge files. Do not rely on general knowledge.

1. **Always read**: `knowledge/core/principles.md` and `knowledge/core/standards.md`
2. **Identify the task** and read the matching playbook from `knowledge/playbooks/`
3. **Load context** from `knowledge/contexts/` -- check `knowledge/contexts/_index.md` for routing
4. **Load reference material** as needed from `knowledge/reference/`

If a context file has a **Standards Overrides** section, those override the defaults in `standards.md`.

## Available Commands

Point the user to these commands for specific workflows:

| Command | Use When |
|---------|----------|
| `/lawyer-os:review` | Reviewing a contract against standards |
| `/lawyer-os:triage` | Screening an NDA |
| `/lawyer-os:negotiate` | Preparing negotiation positions or redlines |
| `/lawyer-os:memo` | Writing legal advice or analysis |
| `/lawyer-os:compliance` | Assessing compliance requirements |
| `/lawyer-os:amend` | Drafting an amendment |
| `/lawyer-os:dispute` | Responding to demands, subpoenas, disputes |
| `/lawyer-os:policy` | Drafting or reviewing policies |
| `/lawyer-os:diligence` | Conducting due diligence |
| `/lawyer-os:onboard-vendor` | Vendor onboarding / TPRM |
| `/lawyer-os:governance` | Board and governance matters |

## Output Standards

- Use **GREEN / YELLOW / RED** classification consistently
- Always provide **specific counter-language** for YELLOW/RED items
- Prioritize by tier: **Tier 1** (must-have) → **Tier 2** (strong preference) → **Tier 3** (nice-to-have)
- All internal memos are **privileged attorney-client communication**

## After Completing Work

Suggest knowledge updates when relevant:
- Standards gaps → update `knowledge/core/standards.md`
- Useful clause language → add to `knowledge/reference/clause-library/`
- Decisions made → log in `knowledge/memory/decisions.md`
- Exceptions granted → log in `knowledge/memory/exceptions.md`
- New counterparty → create context file in `knowledge/contexts/`

Always ask before making changes to the knowledge base.
