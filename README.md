# Lawyer OS

A personal legal operating system for Claude Code. Review contracts, triage NDAs, negotiate redlines, write memos, assess compliance, and more -- all grounded in your own standards, playbooks, and institutional memory.

## What It Does

11 skills for the legal workflows you do every day:

| Skill | What It Does |
|-------|-------------|
| `/lawyer-os:review` | Review a contract against your standards (GREEN/YELLOW/RED) |
| `/lawyer-os:triage` | Screen and classify an NDA for quick routing |
| `/lawyer-os:negotiate` | Generate redlines with rationale and fallback positions |
| `/lawyer-os:memo` | Write a privileged legal memo with risk assessment |
| `/lawyer-os:compliance` | Assess licensing, KYC/AML, privacy, sanctions requirements |
| `/lawyer-os:amend` | Draft an amendment with downstream effect analysis |
| `/lawyer-os:dispute` | Respond to demand letters, subpoenas, regulatory inquiries |
| `/lawyer-os:policy` | Draft or review policies and terms of service |
| `/lawyer-os:diligence` | Conduct or respond to due diligence |
| `/lawyer-os:onboard-vendor` | Third-party risk management workflow |
| `/lawyer-os:governance` | Board resolutions, minutes, entity management |

Every skill follows a structured playbook, loads your specific standards and context, and produces consistent output with GREEN/YELLOW/RED classification, specific counter-language, and tiered prioritization.

## How It Works

A 4-layer knowledge system that mirrors how lawyers actually think:

```
knowledge/
  core/           -- Your identity: principles, org context, standards, writing style
  playbooks/      -- Step-by-step processes for each task type
  contexts/       -- Counterparty-specific positions, deal history, relationship overrides
  reference/      -- 13 legal knowledge topics, clause library, checklists, templates
  memory/         -- Decision log, exceptions log, lessons learned
```

Before any legal work, the system loads relevant knowledge files so responses are grounded in YOUR standards and YOUR organization's context -- not generic legal advice.

## Quick Start

### Option A: Claude Code (CLI)

```bash
# Clone the repo
git clone <repo-url> ~/lawyer-os
cd ~/lawyer-os

# Open it as your project directory
claude
```

### Option B: Claude Desktop (Cowork)

1. **Download** the plugin as a `.zip` file (or zip it yourself from the repo)
2. **Open Claude Desktop** and go to **Cowork > Customize > Browse plugins**
3. **Upload** the `.zip` file -- it installs automatically
4. **Start a new conversation** in Cowork mode -- the plugin is now active

To edit the plugin after installing in Cowork:
1. Go to **Cowork > Customize** and find the Lawyer OS plugin
2. Click **Edit** to open the plugin editor
3. Navigate to `knowledge/core/` and edit `organization.md`, `principles.md`, `standards.md`, and `style.md`
4. Edit `CLAUDE.md` to update the Identity section with your name and org
5. Changes save automatically -- they take effect in your next conversation

### Option C: Claude Code Plugin

```bash
# If distributed via the plugin marketplace
claude plugin add lawyer-os
```

### Personalize (5 files to edit)

| File | What to Fill In | Priority |
|------|----------------|----------|
| `knowledge/core/organization.md` | Your company, entities, team, products, regulatory posture | Required |
| `knowledge/core/principles.md` | Your legal philosophy, risk appetite, priorities, negotiation style | Required |
| `knowledge/core/standards.md` | Your default positions for each clause type | Required (can build over time) |
| `knowledge/core/style.md` | Your writing voice, tone, formatting preferences | Recommended |
| `CLAUDE.md` | Update the Identity section with your name and org | Required |

Each file has placeholder text with examples showing you exactly what to fill in.

You can edit these files manually, or have Claude help you fill them in interactively (see below).

### Let Claude Help You Personalize

Instead of editing the placeholder files by hand, you can have a conversation with Claude to fill them in. This works in both Claude Code and Cowork.

**In Cowork (Claude Desktop):**

1. Install the plugin (see Option B above)
2. Start a new Cowork conversation with the plugin active
3. Say something like:

> "Help me set up this plugin. I'm [your name], [your title] at [your company]. We do [what your company does]."

or

> "Read knowledge/core/organization.md and interview me to fill it in."

or

> "Walk me through personalizing this plugin for my practice."

Claude will read the placeholder files, ask you questions about your organization, legal philosophy, and standard positions, and write the completed files for you. You can go file by file or do them all in one session.

**Example prompts for each file:**

| File | What to say |
|------|------------|
| `organization.md` | "Help me fill in organization.md -- here's what my company does..." |
| `principles.md` | "Interview me about my legal philosophy so you can fill in principles.md" |
| `standards.md` | "Let's build out my standards. Start with liability caps -- here's what I typically ask for..." |
| `style.md` | "Here are a few memos I've written. Analyze my writing style and fill in style.md." |
| `CLAUDE.md` | "Update the Identity section of CLAUDE.md with my info" |

You don't need to do everything at once. `standards.md` in particular is designed to be built up over time -- you can start with a few clause types and add more as you review real agreements.

**In Claude Code (CLI):**

Same approach, but from the terminal. Open the project directory and ask Claude to help:

```bash
cd ~/lawyer-os
claude
> "Help me personalize this plugin. Read the knowledge/core/ files and interview me."
```

### Start Using It

```
/lawyer-os:review path/to/contract.pdf
/lawyer-os:triage path/to/nda.pdf
/lawyer-os:memo "Can we do X under Y regulation?"
```

Skills also auto-activate when Claude detects relevant context -- upload a contract and it will automatically load your standards and playbooks.

The system learns as you work -- after each task, it suggests updates to your standards, clause library, and institutional memory.

## What's Included

**Ready to use:**
- 11 skills with structured workflows (invocable and auto-activating)
- 1 additional auto-activating knowledge skill
- 11 playbooks with step-by-step processes
- 13 legal knowledge reference files (payments, privacy, IP, compliance, etc.)
- 6 checklists (contract review, NDA screening, vendor onboarding, due diligence, partner terms, litigation hold)
- 6 clause library files (populate with your proven language)
- 3 memory logs (decisions, exceptions, lessons learned)

**You provide:**
- Your organization context
- Your legal principles and risk appetite
- Your standard positions for contract clauses
- Your counterparty context files (built over time)
- Your clause library (built through use)

## Adding Context Over Time

As you work with the system, you'll naturally build out:

- **Context files** for counterparties (`knowledge/contexts/partners/`)
- **Clause library** entries from successful negotiations (`knowledge/reference/clause-library/`)
- **Decision log** entries capturing your reasoning (`knowledge/memory/decisions.md`)
- **Exceptions** when you deviate from standards (`knowledge/memory/exceptions.md`)
- **Lessons learned** from past work (`knowledge/memory/lessons-learned.md`)

The system prompts you to save these after each task.

## License

MIT

---

## Built by Eigen Legal

lawyer-os is a free, open source tool built by [Eigen Legal](https://eigenlegal.com). We help law firms and in-house legal teams build custom AI workflows — trained on your standards, your playbooks, and your judgment.

Want a custom version built for your practice? [Book a free consultation →](https://eigenlegal.com)
