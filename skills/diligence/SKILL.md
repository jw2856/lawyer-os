---
name: diligence
description: "Conduct or respond to due diligence for transactions — generate request lists, review documents, flag issues, and produce DD reports. Use when the user is involved in a transaction requiring due diligence, either conducting or responding."
---

# Due Diligence

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Conduct or respond to due diligence for transactions. Generate or customize request lists, review documents by category, flag issues by severity, and produce comprehensive DD summary reports or document trackers.

## Workflow

### Step 1: Accept DD Materials

Accept due diligence materials in any of these formats:
- **File path**: Local folder or specific documents (PDF, DOCX, spreadsheets)
- **URL**: Link to a data room or document repository in ~~cloud storage
- **Pasted text**: DD request list, findings summary, or specific document content
- **Description**: Transaction description for generating a DD request list from scratch

If conducting DD and no data room is available yet, proceed with generating the request list.

### Step 2: Gather Context

Ask the user for context before beginning:

1. **Are we conducting DD or responding to DD?** (conducting = we're the buyer/investor; responding = we're the target/seller)
2. **What type of transaction?** (acquisition, investment/funding round, partnership, licensing, joint venture, merger)
3. **Who is the other party?** (counterparty name, industry, size)
4. **What is the transaction size/value?** (affects materiality thresholds)
5. **Key risk areas**: Any areas of particular concern? (IP, litigation, regulatory, financial, contracts, employment)
6. **Scope limitations**: Is this full DD or focused on specific areas?
7. **Timeline**: When is the DD period ending? When are reports due?
8. **Confidentiality**: Any special handling requirements? (clean team, outside counsel eyes only)

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/playbooks/due-diligence.md` — DD process and methodology
- `knowledge/reference/checklists/due-diligence-checklist.md` — Comprehensive DD checklist

**Load by transaction type and risk area:**
- `knowledge/reference/legal-knowledge/corporate-and-governance.md` — Corporate structure, governance, equity
- `knowledge/reference/legal-knowledge/intellectual-property.md` — IP ownership, licenses, open source
- `knowledge/reference/legal-knowledge/compliance-and-licensing.md` — Regulatory, licensing
- `knowledge/reference/legal-knowledge/litigation-and-disputes.md` — Litigation history, pending claims
- `knowledge/reference/legal-knowledge/data-privacy.md` — Data practices, privacy compliance
- `knowledge/reference/legal-knowledge/international-trade.md` — Cross-border, sanctions
- `knowledge/core/organization.md` — If responding to DD about your organization

**Load contextual knowledge:**
- Load relevant context file for the counterparty (if exists)

### Step 4: Determine Direction

| Direction | Role | Primary Output |
|-----------|------|---------------|
| **Conducting DD** | Buyer / Investor / Acquirer | DD request list, document review, findings report, recommended deal protections |
| **Responding to DD** | Target / Seller / Fundraiser | Document tracker, privilege log, gap analysis, disclosure schedule |

### Step 5: Conducting DD -- Request List and Document Review

#### 5a: Generate or Customize DD Request List

Produce a categorized request list scaled to transaction type and size:

| Category | Request Items | Materiality Threshold | Priority |
|----------|--------------|----------------------|----------|
| **Corporate** | Formation docs, bylaws, board minutes, cap table, org chart, good standing | All | High |
| **Equity & Capitalization** | Stock ledger, option plans, warrants, SAFEs, convertible notes, 409A valuations | All | High |
| **Material Contracts** | Customer agreements, vendor agreements, partnerships, licenses (above threshold) | [$X+ or strategic] | High |
| **Intellectual Property** | Patent portfolio, trademark registrations, trade secret policies, open source audit, IP assignment agreements | All | High |
| **Litigation** | Pending/threatened litigation, regulatory actions, settlements (last 5 years) | All | High |
| **Employment** | Employee agreements, offer letters, benefit plans, PIIA/invention assignments, org chart, key person dependencies | All | Medium |
| **Financial** | Audited financials, tax returns, outstanding debt, liens, security interests | Last 3 years | High |
| **Regulatory & Compliance** | Licenses, registrations, compliance programs, audits, government investigations | All | High |
| **Insurance** | Current policies, claims history, coverage limits | All | Medium |
| **Data & Privacy** | Privacy policies, DPAs, data flow maps, breach history, DPIA records | All | Medium |
| **Real Property & Assets** | Leases, owned property, key equipment, encumbrances | Material items | Low |

#### 5b: Review Documents by Category

For each category of documents received, assess:

| Document/Item | Category | Severity | Finding | Risk | Recommended Action |
|--------------|----------|----------|---------|------|-------------------|
| [document name] | [category] | HIGH/MEDIUM/LOW | [what was found] | [what it means] | [what to do about it] |

**Severity classification:**
- **HIGH**: Material risk that could affect deal terms, valuation, or go/no-go decision
- **MEDIUM**: Notable issue requiring attention but not deal-affecting
- **LOW**: Minor issue for awareness, standard follow-up

#### 5c: Produce Findings Report

Aggregate findings into a comprehensive DD summary.

### Step 6: Responding to DD -- Document Tracking and Privilege Review

#### 6a: Organize Response by Request Category

| Request Category | Status | Documents Provided | Documents Pending | Privileged/Withheld | Notes |
|-----------------|--------|-------------------|------------------|-------------------|-------|
| Corporate | Complete / Partial / Not Started | [list] | [list] | [list] | [notes] |
| [category] | [status] | [list] | [list] | [list] | [notes] |

#### 6b: Identify Privileged Materials

Flag documents that should NOT be disclosed:

| Document | Privilege Type | Basis | Recommendation |
|----------|--------------|-------|---------------|
| [document] | Attorney-client / Work product / Joint defense | [why privileged] | Withhold / Redact / Seek waiver |

#### 6c: Track Gaps and Sensitive Items

| Gap/Sensitive Item | Category | Risk of Disclosure | Risk of Non-Disclosure | Recommended Approach |
|-------------------|----------|-------------------|----------------------|---------------------|
| [item] | [category] | [what happens if we share] | [what happens if we don't] | [recommendation] |

### Step 7: Business Impact Summary

Provide a summary covering:
- **Overall DD assessment**: Clean / issues identified / material concerns
- **Top findings**: Most significant issues discovered or disclosed
- **Deal impact**: How findings affect valuation, structure, or go/no-go
- **Recommended deal protections**: Specific reps, warranties, indemnities, escrows, or conditions to address findings
- **Timeline status**: On track to complete DD within the allotted period?

### Step 8: Save or Share (If Connected)

If ~~cloud storage is connected, offer to:
- Save the DD request list, findings report, or document tracker to the data room or shared folder
- Organize documents by category in the data room

If ~~chat is connected and the user requests it:
- Post a DD status summary (completion percentage, top findings, blockers) to the relevant channel

## Output Format

**If conducting DD:**
```
## Due Diligence Summary

**Transaction**: [type and description]
**Target**: [company name]
**Transaction Value**: [if known]
**DD Period**: [start date -- end date]
**Scope**: [full / focused on specific areas]
**Materiality Threshold**: [$X or qualitative]

## DD Request List

### [Category]
| # | Request | Priority | Status | Notes |
|---|---------|----------|--------|-------|
| 1 | [request item] | [high/medium/low] | [received/pending/N/A] | [notes] |

[Repeat for each category]

## Overall Assessment: [Clean / Issues Identified / Material Concerns]

## Key Findings Summary

| # | Finding | Category | Severity | Deal Impact | Recommended Action |
|---|---------|----------|----------|-------------|-------------------|
| 1 | [finding] | [category] | HIGH/MEDIUM/LOW | [impact on deal] | [action] |

## Detailed Findings by Category

### [Category] -- [# of issues found]
[Detailed discussion of findings in this category]

### [Category] -- [# of issues found]
[Detailed discussion]

## Recommended Deal Protections

| Finding | Protection Type | Proposed Language/Approach |
|---------|---------------|--------------------------|
| [finding] | [rep & warranty / indemnity / escrow / condition / price adjustment] | [specific proposal] |

## Business Impact

[Summary of how findings affect the transaction: valuation, structure, conditions, timeline]

## Next Steps

| Action Item | Owner | Deadline | Priority |
|------------|-------|----------|----------|
| [action] | [who] | [when] | [high/medium/low] |
```

**If responding to DD:**
```
## Due Diligence Response Summary

**Transaction**: [type and description]
**Requesting Party**: [company name]
**DD Period**: [start date -- end date]
**Completion Status**: [X% complete]

## Document Tracker

### [Category] -- [Complete / Partial / Not Started]
| # | Request Item | Status | Documents Provided | Notes |
|---|-------------|--------|-------------------|-------|
| 1 | [request] | [provided/pending/N/A/privileged] | [document names] | [notes] |

[Repeat for each category]

## Privileged Materials Log

| Document | Privilege Type | Basis |
|----------|--------------|-------|
| [document] | [type] | [basis for withholding] |

## Gaps and Sensitive Items

| Item | Risk Assessment | Recommended Approach |
|------|----------------|---------------------|
| [item] | [risk of disclosure vs. non-disclosure] | [recommendation] |

## Disclosure Considerations

[Any items that require careful framing, context, or discussion before disclosure]

## Next Steps

| Action Item | Owner | Deadline | Priority |
|------------|-------|----------|----------|
| [action] | [who] | [when] | [high/medium/low] |
```

## Notes

- Transaction types include: acquisition, investment, partnership, licensing, joint venture, merger, and others
- Materiality thresholds should be set based on transaction size and type. For acquisitions, typically 1-5% of deal value. For investments, often lower.
- Privileged materials should never be disclosed without explicit approval; flag them clearly and create a privilege log
- The scope parameter helps focus the review on the most relevant risk areas. If the user says "focus on IP", prioritize IP but still flag obvious issues in other categories.
- For large data rooms (hundreds of documents), offer to prioritize the most material categories first and then work through the remainder
- If conducting DD and documents are missing or incomplete, flag the gaps and assess whether the missing information is material
- If responding to DD, track all documents shared and maintain version control

## After Completion

Suggest knowledge updates if relevant:
- **Context file**: "Should I create/update a context file for [target/counterparty] with these DD findings?"
- **Decision log**: "Should I log this DD outcome and any deal protections in memory?"
- **Checklist improvement**: "This DD surfaced a category not in the standard checklist -- should I add it?"
- **Lesson learned**: "This DD process revealed [insight] -- should I note it for future transactions?"
