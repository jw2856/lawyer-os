---
name: amend
description: "Draft an amendment to an existing agreement — identify downstream effects, draft precise modification language, ensure consistency with the original. Use when the user needs to modify, update, or amend an existing contract or agreement."
---

# Draft Amendment

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Draft an amendment to an existing agreement. Review the original agreement's amendment mechanism, identify downstream effects of the proposed changes, and produce a ready-to-execute amendment document.

## Workflow

### Step 1: Accept the Original Agreement

Accept the original agreement in any of these formats:
- **File path**: Local PDF, DOCX, or other document
- **URL**: Link to a document in ~~cloud storage or other document system
- **Pasted text**: Agreement text pasted directly into the conversation
- **Reference**: Description of the agreement (e.g., "our MSA with Vendor X dated January 2025") -- if not sufficient, ask for the actual document

The original agreement **must** be provided or accessible before drafting. If the user references an agreement by name without a file, ask for it.

### Step 2: Gather Context

Ask the user for context before beginning the amendment:

1. **What needs to change?** (specific sections, terms, pricing, scope, parties, etc.)
2. **Why is the change needed?** (business reason -- helps draft recitals and ensures the amendment captures intent)
3. **Is this the first amendment?** (affects numbering and references to prior amendments)
4. **Effective date**: When should the changes take effect? (signing date, specific date, retroactive)
5. **Are there related documents?** (SOWs, Order Documents, DPAs, SLAs that may also need updating)
6. **Counterparty alignment**: Has the counterparty agreed to the changes in principle, or is this a proposal?
7. **Any new terms to add?** (not just modifications -- entirely new provisions)

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the amendment:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/standards.md` — Default clause positions
- `knowledge/playbooks/amendment-drafting.md` — Amendment process and structure

**Load contextual knowledge:**
- Load relevant context file for the counterparty (if exists)
- Load the original agreement (required)
- Load any prior amendments to the agreement (if they exist)
- Load relevant legal knowledge from `knowledge/reference/legal-knowledge/` based on subject matter of the changes

If a context file has a **Standards Overrides** section, those override `standards.md` defaults for new or modified terms.

### Step 4: Review the Original Agreement

Before drafting, examine the original agreement for:

| Review Point | Details |
|-------------|---------|
| **Amendment mechanism** | What does the agreement require for amendments? (written consent, board approval, specific form, notice period) |
| **Prior amendments** | How many amendments exist? What numbering convention is used? |
| **Defined terms** | Which defined terms are affected by the proposed changes? |
| **Cross-references** | Which other sections reference the sections being amended? |
| **Consistency checks** | Will the change create any conflicts with other provisions? |
| **Downstream effects** | Does the change affect exhibits, schedules, SOWs, or incorporated documents? |

### Step 5: Analyze Downstream Effects

For each proposed change, map the ripple effects:

| Proposed Change | Sections Directly Affected | Cross-References to Update | Defined Terms Impacted | Downstream Documents | Unintended Consequences |
|----------------|---------------------------|--------------------------|----------------------|---------------------|----------------------|
| [change 1] | [section numbers] | [sections that reference these] | [terms] | [SOWs, DPAs, etc.] | [potential issues] |

Flag any change that:
- Alters the economic terms without updating the corresponding payment/fee provisions
- Changes defined terms that appear throughout the agreement
- Affects provisions that have been the subject of prior negotiation (check context file)
- Could trigger consent or notice requirements under the original agreement

### Step 6: Draft the Amendment

Use standard amendment structure with precise references:

**Amendment components:**
1. **Title and numbering**: Amendment No. [X] to [Agreement Name]
2. **Recitals**: Identify parties, original agreement (with date), purpose of amendment
3. **Definitions**: Any new or modified defined terms
4. **Amendments**: Section-by-section changes with exact references to the original
5. **Representations**: If needed (e.g., authority to amend, no other changes)
6. **No Other Changes**: Confirmation that all other terms remain in full force
7. **Effective Date**: When the amendment takes effect
8. **Counterparts**: Standard counterparts and electronic signature clause
9. **Signature Blocks**: Party names and signature lines matching the original

For each amendment section, use precise modification language:
- **Deletion**: "Section [X] of the Agreement is hereby deleted in its entirety."
- **Replacement**: "Section [X] of the Agreement is hereby deleted and replaced with the following: [new language]"
- **Addition**: "A new Section [X.Y] is hereby added to the Agreement as follows: [new language]"
- **Modification**: "Section [X] of the Agreement is hereby amended by [replacing/adding/deleting] the [first/second/etc.] sentence [of paragraph [Y]] with/as follows: [language]"

### Step 7: Review for Consistency

Before finalizing, verify:
- All section references in the amendment match the original agreement
- Defined terms are used consistently between the amendment and the original
- The amendment does not create any internal conflicts
- The amendment mechanism requirements have been satisfied
- Date references and party names are accurate

### Step 8: Generate Output (If Connected)

If ~~office suite is connected, offer to:
- Generate the amendment as a formatted document (DOCX)
- Create a redlined version of the original agreement showing the effect of the amendment

If ~~cloud storage is connected, offer to save the draft to the appropriate location.

## Output Format

```
## Amendment Summary

**Original Agreement**: [agreement name, date, parties]
**Amendment Number**: [X]
**Purpose**: [brief description of what is being changed and why]
**Effective Date**: [date or placeholder]
**Sections Modified**: [list of section numbers]
**Downstream Effects**: [list of any ripple effects identified]

---

AMENDMENT NO. [X] TO [AGREEMENT NAME]

This Amendment No. [X] ("Amendment") to the [Agreement Name] dated [date] (the "Agreement") is entered into as of [effective date] by and between:

[Party A full legal name] ("[short name]")

and

[Party B full legal name] ("[short name]")

(each a "Party" and together, the "Parties").

## Recitals

WHEREAS, the Parties entered into the Agreement on [date];

WHEREAS, [if applicable: the Agreement was previously amended by Amendment No. [X-1] dated [date]];

WHEREAS, the Parties desire to amend the Agreement to [brief description of purpose];

NOW, THEREFORE, in consideration of the mutual covenants and agreements set forth herein, and for other good and valuable consideration, the receipt and sufficiency of which are hereby acknowledged, the Parties agree as follows:

## 1. Definitions

[Any new or modified defined terms. If none: "Capitalized terms used but not defined herein shall have the meanings given to them in the Agreement."]

## 2. Amendments

### 2.1 [Section Reference]
[Precise modification language]

### 2.2 [Section Reference]
[Precise modification language]

[Repeat for each change]

## 3. No Other Changes

Except as expressly set forth in this Amendment, all terms and conditions of the Agreement shall remain in full force and effect. In the event of any conflict between this Amendment and the Agreement, this Amendment shall control.

## 4. Counterparts

This Amendment may be executed in counterparts, each of which shall be deemed an original, and all of which together shall constitute one and the same instrument. Electronic signatures shall be deemed original signatures for all purposes.

IN WITNESS WHEREOF, the Parties have executed this Amendment as of the date first written above.

[PARTY A NAME]                    [PARTY B NAME]

By: _________________________     By: _________________________
Name:                             Name:
Title:                            Title:
Date:                             Date:

---

## Consistency Check Results

| Check | Status | Notes |
|-------|--------|-------|
| Section references accurate | [pass/fail] | [details] |
| Defined terms consistent | [pass/fail] | [details] |
| No internal conflicts | [pass/fail] | [details] |
| Amendment mechanism satisfied | [pass/fail] | [details] |
| Downstream documents addressed | [pass/fail] | [details] |

## Next Steps

| Action Item | Owner | Deadline |
|------------|-------|----------|
| [action] | [who] | [when] |
```

## Notes

- The original agreement must be provided or accessible before drafting. Do not draft an amendment based on assumptions about the original terms.
- Always verify the amendment mechanism in the original agreement -- some require written consent of both parties, board approval, or specific notice periods.
- If the effective date is not specified, use "[DATE]" as a placeholder for the parties to fill in.
- If the amendment affects economic terms, double-check that payment, invoice, and fee provisions are consistent.
- For complex amendments touching many sections, consider whether a full amendment and restatement would be cleaner than a piecemeal amendment.
- If ~~office suite is connected, offer to generate the formatted DOCX directly.
- If the agreement is governed by non-US law, note any jurisdiction-specific requirements for amendment execution.

## After Completion

Suggest knowledge updates if relevant:
- **Context update**: "Should I update the context file for [counterparty] to reflect this amendment?"
- **Clause language**: "This amendment language could be reusable -- should I add it to the clause library?"
- **Decision log**: "Should I log this amendment in memory?"
- **Standards gap**: "This amendment addressed a scenario not covered in standards -- should I add it?"
