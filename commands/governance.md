---
description: Handle board matters, resolutions, corporate governance, and entity management — draft resolutions, minutes, formation documents, and compliance filings
argument-hint: "<governance task type>"
---

# /lawyer-os:governance -- Board & Governance

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Handle corporate governance tasks including board resolutions, board minutes, entity formation, annual compliance, officer/director changes, equity issuances, and other corporate actions. Draft the appropriate documents, identify filing requirements, and track deadlines.

## Invocation
```
/lawyer-os:governance [task type] [relevant details]
```

## Workflow

### Step 1: Accept Governance Materials

Accept governance materials in any of these formats:
- **File path**: Existing bylaws, prior resolutions, formation documents, or other corporate records (PDF, DOCX)
- **URL**: Link to corporate records in ~~cloud storage or entity management system
- **Pasted text**: Meeting notes, proposed actions, or other governance content
- **Description**: Description of the governance task to be performed

Not all tasks require input documents -- some (like entity formation) start from scratch.

### Step 2: Gather Context

Ask the user for context before beginning:

1. **What type of governance task?** (board resolution, board minutes, entity formation, annual compliance, officer/director change, equity issuance, dividend/distribution, intercompany agreement, subsidiary management, other corporate action)
2. **Which entity?** (parent entity, specific subsidiary, new entity to be formed — see `core/organization.md`)
3. **What is the corporate action?** (specific action requiring board approval, meeting to be documented, entity to be formed, etc.)
4. **Timeline**: When does this need to be completed? Any statutory or contractual deadlines?
5. **Approval chain**: Who needs to approve? (board, stockholders, specific officers, parent company consent)
6. **Related transactions**: Is this governance action part of a larger transaction? (funding round, acquisition, partnership, restructuring)
7. **Prior documents**: Are there existing bylaws, certificate of incorporation, prior resolutions, or board packages to reference?

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/organization.md` — Entity structure, current officers/directors, governance framework
- `knowledge/playbooks/board-and-governance.md` — Governance processes and standards
- `knowledge/reference/legal-knowledge/corporate-and-governance.md` — Corporate law, fiduciary duties, governance requirements

**Load by task type:**
- Entity formation --> relevant jurisdiction-specific formation requirements
- Equity issuance --> securities law, cap table implications
- Compliance filings --> jurisdiction-specific filing requirements and deadlines

**Load contextual knowledge:**
- Existing bylaws, certificate of incorporation, or operating agreement for the entity
- Prior resolutions or minutes for the same entity (for consistency of form and numbering)

### Step 4: Identify the Governance Task and Follow the Appropriate Path

| Task Type | Path | Key Output |
|-----------|------|-----------|
| **Board Resolution** | Step 5 | Written consent or resolution with recitals and operative provisions |
| **Board Minutes** | Step 6 | Structured meeting record with all actions documented |
| **Entity Formation** | Step 7 | Formation filings, organizational documents, post-formation checklist |
| **Annual Compliance** | Step 8 | Filing checklist with deadlines, fees, and responsible parties |
| **Officer/Director Changes** | Step 9 | Appointment/resignation documents, filing requirements |
| **Equity Issuance** | Step 10 | Board approval, stock purchase agreements, securities filings |
| **Other Corporate Action** | Step 11 | Appropriate documentation for the specific action |

### Step 5: Board Resolution

Draft a board resolution for the specified corporate action:

| Element | Details |
|---------|---------|
| **Action requiring approval** | [description of the corporate action] |
| **Authority** | [bylaw provision, statute, or other authority for the action] |
| **Prior approvals** | [any prerequisite approvals already obtained] |
| **Quorum requirements** | [quorum for this type of action] |
| **Voting threshold** | [majority, supermajority, unanimous, as required] |
| **Form** | [written consent / meeting resolution] |

Resolution structure:
1. **Header**: Entity name, date, type (written consent / meeting resolution)
2. **Recitals**: WHEREAS clauses establishing context and authority
3. **Operative provisions**: RESOLVED clauses authorizing specific actions
4. **Officer authorization**: Authorization for officers to take implementing actions
5. **Attachments**: Exhibits for any agreements, certificates, or other documents being approved
6. **Signature blocks**: All directors signing (for written consent) or secretary certification (for meeting)

### Step 6: Board Minutes

Draft board meeting minutes:

| Element | Details |
|---------|---------|
| **Meeting details** | Date, time, location (or virtual platform) |
| **Attendees** | Directors present, directors absent, quorum confirmed |
| **Other attendees** | Officers, counsel, guests (with purpose for attendance) |
| **Agenda items** | Numbered list of items discussed and acted upon |

Minutes structure:
1. **Call to order**: Time, quorum confirmation, chair designation
2. **Approval of prior minutes**: If applicable
3. **Reports**: Management reports, committee reports
4. **Action items**: Each resolution or action taken, with vote recorded
5. **Discussion items**: Topics discussed but not requiring formal action
6. **Executive session**: If applicable (note that session occurred, not content)
7. **Adjournment**: Time of adjournment, next meeting date

### Step 7: Entity Formation

Evaluate and execute entity formation:

| Decision | Options | Recommendation | Rationale |
|----------|---------|---------------|-----------|
| **Entity type** | Corporation / LLC / LP / other | [recommendation] | [tax, liability, governance considerations] |
| **Jurisdiction** | Delaware / [state] / [foreign jurisdiction] | [recommendation] | [tax, regulatory, operational considerations] |
| **Name** | [proposed names, availability check needed] | [recommendation] | [trademark, availability considerations] |

Formation deliverables:
1. **Formation filing**: Certificate of Incorporation / Articles of Organization / Certificate of LP
2. **Organizational documents**: Bylaws / Operating Agreement / LP Agreement
3. **Initial resolutions**: Appointing officers, authorizing accounts, adopting policies
4. **Post-formation checklist**:

| Task | Deadline | Status | Responsible |
|------|----------|--------|-------------|
| Obtain EIN from IRS | Within 30 days | [status] | [who] |
| Open bank account | Within 30 days | [status] | [who] |
| Foreign qualification filings | Before doing business in other states | [status] | [who] |
| Registered agent designation | At formation | [status] | [who] |
| State tax registrations | Varies by state | [status] | [who] |
| Business licenses | Varies by jurisdiction | [status] | [who] |
| Insurance procurement | Before operations | [status] | [who] |
| IP assignment from parent | At formation | [status] | [who] |
| Intercompany agreements | At formation | [status] | [who] |

### Step 8: Annual Compliance

Generate a comprehensive compliance filing checklist:

| Entity | Jurisdiction | Filing Type | Deadline | Fee | Status | Responsible |
|--------|-------------|------------|----------|-----|--------|-------------|
| [entity name] | [state/jurisdiction] | Annual report | [date] | [$amount] | [filed/pending/overdue] | [who] |
| [entity name] | [state/jurisdiction] | Franchise tax | [date] | [$amount] | [filed/pending/overdue] | [who] |
| [entity name] | [state/jurisdiction] | Registered agent renewal | [date] | [$amount] | [filed/pending/overdue] | [who] |
| [entity name] | [state/jurisdiction] | Foreign qualification renewal | [date] | [$amount] | [filed/pending/overdue] | [who] |

Flag any overdue filings or upcoming deadlines within 30 days.

### Step 9: Officer/Director Changes

Document officer or director appointments, resignations, or removals:

| Element | Details |
|---------|---------|
| **Change type** | Appointment / Resignation / Removal |
| **Individual** | [name, title] |
| **Effective date** | [date] |
| **Board approval required?** | [yes/no -- check bylaws] |
| **Filing requirements** | [state filings, SEC filings if applicable] |

Deliverables:
- Board resolution approving the change
- Resignation letter (if resignation)
- Indemnification agreement (for new directors)
- D&O questionnaire (for new directors)
- State filings updating officer/director information

### Step 10: Equity Issuance

Document equity issuance:

| Element | Details |
|---------|---------|
| **Issuance type** | Common stock / Preferred stock / Options / Warrants / SAFEs / Convertible notes |
| **Amount** | [shares/units, price, total consideration] |
| **Recipient** | [name, relationship] |
| **Authorization** | [available authorized shares, board/stockholder approval needed] |
| **Securities exemption** | [Section 4(a)(2), Rule 506(b), Reg D, etc.] |

Deliverables:
- Board resolution authorizing issuance
- Stock purchase agreement / Option agreement / SAFE / Convertible note
- Accredited investor questionnaire (if applicable)
- Blue sky filings
- Cap table update

### Step 11: Generate Output (If Connected)

If ~~office suite is connected, offer to:
- Generate governance documents as formatted DOCX files
- Create templates for recurring governance tasks

If ~~cloud storage is connected, offer to save documents to the corporate records folder.

If ~~chat is connected and the user requests it:
- Post a governance action summary (what was done, filing deadlines, action items) to the relevant channel

## Output Format

```
## Governance Action Summary

**Entity**: [entity name]
**Task Type**: [board resolution / minutes / formation / compliance / officer change / equity / other]
**Date**: [date of action]
**Related Transaction**: [if applicable]

---

### Draft Document

[Full draft appropriate to the task type: resolution, minutes, formation documents, or compliance checklist]

---

### Filing Requirements and Deadlines

| Filing | Jurisdiction | Deadline | Fee | Responsible | Status |
|--------|-------------|----------|-----|-------------|--------|
| [filing type] | [jurisdiction] | [date] | [$amount] | [who] | [pending/filed] |

### Approval Chain

| Approval | Required? | Status | Date |
|----------|----------|--------|------|
| Board resolution | [yes/no] | [obtained/pending] | [date] |
| Stockholder approval | [yes/no] | [obtained/pending/N/A] | [date] |
| Parent company consent | [yes/no] | [obtained/pending/N/A] | [date] |
| Officer execution | [yes/no] | [obtained/pending] | [date] |

### Follow-Up Action Items

| # | Action Item | Owner | Deadline | Priority |
|---|------------|-------|----------|----------|
| 1 | [action] | [who] | [when] | [high/medium/low] |
```

## Notes

- Task types include: board resolution, board minutes, entity formation, annual compliance, officer/director changes, equity issuances, dividend/distribution, intercompany agreements, subsidiary management, and other corporate actions
- Board resolutions should follow the company's existing format and bylaws requirements. If prior resolutions are available, match the form.
- Entity formation jurisdiction selection should consider tax, regulatory, and operational factors. Delaware is default for US corporations unless there is a specific reason to choose another jurisdiction.
- Annual compliance deadlines are jurisdiction-specific and missing them can result in penalties, interest, or loss of good standing. Flag any overdue filings immediately.
- For equity issuances, always verify authorized share count before proceeding. If additional authorization is needed, this requires a separate board/stockholder action.
- Written consents require unanimous consent unless the certificate of incorporation provides otherwise (for Delaware corporations).
- If the governance action is part of a larger transaction (e.g., board approval for an acquisition), coordinate with the transaction timeline.

## After Completion

Suggest knowledge updates if relevant:
- **Organization update**: "Should I update organization.md to reflect this governance change (new entity, new officers, etc.)?"
- **Decision log**: "Should I log this corporate action in memory?"
- **Template creation**: "This [resolution/minutes/formation document] could serve as a template -- should I save it?"
- **Compliance tracking**: "Should I update the annual compliance calendar with new filing deadlines?"
- **Context update**: "Should I create/update a context file for the new entity?"
