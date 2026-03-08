---
description: Onboard and evaluate a new vendor through the TPRM process — risk assessment, due diligence, agreement review, approval, and ongoing management
argument-hint: "<vendor name>"
---

# /lawyer-os:onboard-vendor -- Vendor Onboarding

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Onboard a new vendor through the Third-Party Risk Management (TPRM) process. Gather vendor information, assess risk tier, perform scaled due diligence, review the vendor agreement, make an approval recommendation, and set up ongoing management.

## Invocation
```
/lawyer-os:onboard-vendor [vendor name] [service/product description] [optional: internal business owner] [optional: data access scope]
```

## Workflow

### Step 1: Accept Vendor Materials

Accept vendor materials in any of these formats:
- **File path**: Vendor contract, security questionnaire, SOC 2 report, or other documents (PDF, DOCX)
- **URL**: Link to vendor materials in ~~cloud storage or vendor's document portal
- **Pasted text**: Vendor information or contract terms pasted directly into the conversation
- **Description**: Vendor name and service description to begin the intake process

Not all materials are needed upfront -- the workflow will identify what is required based on risk tier.

### Step 2: Gather Context

Ask the user for context before beginning the onboarding:

1. **Vendor name**: Full legal name of the vendor entity
2. **What service/product?** (specific service, software, platform, professional service)
3. **Who is the internal business owner?** (which team/person requested this vendor)
4. **What data will the vendor access?** (personal data, financial data, proprietary/trade secret data, transaction data, source code, none)
5. **How will the vendor access our systems?** (API integration, platform login, data export/import, no system access)
6. **Is this replacing an existing vendor?** (if so, which one -- affects transition planning)
7. **Urgency**: When does the business need this vendor operational?
8. **Budget**: Has budget been approved? What is the contract value?
9. **Existing relationship**: Have we worked with this vendor before? (check for existing context file)

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly.

### Step 3: Load Knowledge

Read these files before starting the onboarding:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/standards.md` — Default clause positions for vendor agreements
- `knowledge/playbooks/vendor-onboarding.md` — Vendor onboarding process
- `knowledge/reference/checklists/vendor-onboarding-checklist.md` — Onboarding checklist

**Load vendor context:**
- `knowledge/contexts/partners/vendors/_overview.md` — Vendor management standards and tiers
- Load specific vendor context file if one already exists (check `knowledge/contexts/partners/vendors/`)

**Load by risk area:**
- `knowledge/reference/legal-knowledge/data-privacy.md` — If vendor will access personal data
- `knowledge/reference/legal-knowledge/compliance-and-licensing.md` — If vendor is in a regulated space
- `knowledge/reference/legal-knowledge/intellectual-property.md` — If vendor will access or develop IP

### Step 4: Vendor Intake

Collect and document vendor information:

| Field | Details |
|-------|---------|
| **Vendor Legal Name** | [full legal name] |
| **DBA / Trade Name** | [if different] |
| **Jurisdiction** | [where incorporated, primary operations] |
| **Service Description** | [what they provide] |
| **Internal Business Owner** | [name, team] |
| **Contract Value** | [annual spend / total contract value] |
| **Contract Term** | [proposed duration] |
| **Data Access Scope** | Personal data / Financial data / Proprietary data / Transaction data / Source code / None |
| **System Access** | API / Platform login / Data export / None |
| **Criticality** | Could the business function without this vendor for 30 days? [yes/no] |
| **Regulatory Exposure** | Does this vendor operate in a regulated space? [yes/no -- details] |

### Step 5: Risk Tier Classification

Classify the vendor into a risk tier based on data access, criticality, and regulatory exposure:

| Risk Factor | Assessment | Weight |
|------------|-----------|--------|
| **Data sensitivity** | [none/low/medium/high/critical] | High |
| **System access level** | [none/read-only/read-write/admin] | High |
| **Business criticality** | [non-critical/important/critical/essential] | Medium |
| **Regulatory exposure** | [none/low/medium/high] | Medium |
| **Contract value** | [<$X / $X-$Y / >$Y] | Low |
| **Vendor maturity** | [startup/growth/established/enterprise] | Low |

**Risk Tier Determination:**

| Tier | Criteria | DD Scope | Review Frequency |
|------|----------|----------|-----------------|
| **HIGH** | Access to personal/financial data, OR business-critical, OR regulated activity | Full security review, compliance assessment, financial review, legal review | Annual |
| **MEDIUM** | Moderate data access, OR important but not critical, OR moderate regulatory exposure | Security questionnaire, compliance basics, legal review | Biennial |
| **LOW** | No sensitive data access, non-critical, no regulatory exposure | Basic information gathering, standard contract terms | Triennial |

### Step 6: Due Diligence -- Scaled to Risk Tier

Perform due diligence appropriate to the assigned risk tier:

**HIGH Tier Due Diligence:**

| DD Element | Status | Finding | Action Required |
|-----------|--------|---------|----------------|
| SOC 2 Type II report review | [received/pending/N/A] | [findings] | [action] |
| Security questionnaire | [completed/pending] | [findings] | [action] |
| Penetration test results | [received/pending/N/A] | [findings] | [action] |
| Business continuity / DR plan | [received/pending] | [findings] | [action] |
| Compliance certifications | [received/pending] | [findings] | [action] |
| Financial stability assessment | [completed/pending] | [findings] | [action] |
| Insurance coverage verification | [received/pending] | [findings] | [action] |
| Reference checks | [completed/pending] | [findings] | [action] |
| Sanctions / adverse media screening | [completed/pending] | [findings] | [action] |

**MEDIUM Tier Due Diligence:**

| DD Element | Status | Finding | Action Required |
|-----------|--------|---------|----------------|
| Security questionnaire | [completed/pending] | [findings] | [action] |
| SOC 2 or equivalent (if available) | [received/pending/N/A] | [findings] | [action] |
| Compliance basics verification | [completed/pending] | [findings] | [action] |
| Insurance coverage verification | [received/pending] | [findings] | [action] |

**LOW Tier Due Diligence:**

| DD Element | Status | Finding | Action Required |
|-----------|--------|---------|----------------|
| Basic company information verified | [yes/no] | [findings] | [action] |
| Standard contract terms acceptable | [yes/no] | [findings] | [action] |

### Step 7: Agreement Review

Trigger the `/lawyer-os:review` command for the vendor's contract, with vendor-specific focus:

| Contract Element | Standard Requirement | Vendor's Position | Status |
|-----------------|---------------------|------------------|--------|
| **Data protection / DPA** | Required for HIGH/MEDIUM | [present/absent/non-compliant] | [GREEN/YELLOW/RED] |
| **Security obligations** | Scaled to risk tier | [adequate/inadequate] | [GREEN/YELLOW/RED] |
| **Liability cap** | Per standards.md | [their position] | [GREEN/YELLOW/RED] |
| **Indemnification** | Mutual with carve-outs | [their position] | [GREEN/YELLOW/RED] |
| **Insurance requirements** | Scaled to risk tier | [their position] | [GREEN/YELLOW/RED] |
| **Termination rights** | For convenience with reasonable notice | [their position] | [GREEN/YELLOW/RED] |
| **Transition assistance** | Required for HIGH/MEDIUM | [present/absent] | [GREEN/YELLOW/RED] |
| **Subcontractor restrictions** | Required for data access | [their position] | [GREEN/YELLOW/RED] |
| **Audit rights** | Required for HIGH | [present/absent] | [GREEN/YELLOW/RED] |
| **IP ownership** | Company owns work product | [their position] | [GREEN/YELLOW/RED] |

For detailed contract review, invoke `/lawyer-os:review` on the vendor agreement.

### Step 8: Approval Recommendation

Based on risk tier, due diligence findings, and agreement review:

| Recommendation | Criteria |
|---------------|----------|
| **Approve** | DD complete, findings acceptable, agreement meets standards |
| **Approve with Conditions** | DD has minor gaps or agreement needs targeted changes -- list specific conditions |
| **Do Not Approve** | Material DD findings, unacceptable agreement terms, or unresolved HIGH-severity issues |

### Step 9: Set Up Ongoing Management

Define the ongoing management schedule:

| Management Element | Frequency | Next Due | Responsible |
|-------------------|-----------|----------|-------------|
| Performance review | [per risk tier] | [date] | [business owner] |
| Security reassessment | [per risk tier] | [date] | [security team] |
| Compliance verification | [per risk tier] | [date] | [legal/compliance] |
| Contract renewal review | [before expiration] | [date] | [legal] |
| Insurance certificate renewal | [annual] | [date] | [business owner] |

### Step 10: Post to Chat (If Connected)

If ~~chat is connected and the user requests it:
- Post the vendor onboarding summary (risk tier, approval recommendation, key findings) to the relevant channel
- Include any conditions or action items that need stakeholder attention

## Output Format

```
## Vendor Onboarding Summary

**Vendor**: [full legal name]
**Service**: [description]
**Business Owner**: [name, team]
**Data Access**: [scope]
**System Access**: [type]
**Contract Value**: [amount]
**Date**: [onboarding date]

## Risk Tier: [HIGH / MEDIUM / LOW]

**Rationale**: [why this tier was assigned]

| Risk Factor | Assessment |
|------------|-----------|
| Data sensitivity | [level] |
| System access | [level] |
| Business criticality | [level] |
| Regulatory exposure | [level] |

## Due Diligence Findings

### Overall DD Status: [Complete / In Progress / Blocked]

| DD Element | Status | Finding | Severity |
|-----------|--------|---------|----------|
| [element] | [status] | [finding] | [HIGH/MEDIUM/LOW/N/A] |

### Key Findings
[Narrative summary of the most important DD findings]

## Agreement Review

### Overall Agreement Status: [Acceptable / Needs Changes / Unacceptable]

[Summary of contract review findings -- detailed review via /lawyer-os:review]

| Contract Element | Status | Action Required |
|-----------------|--------|----------------|
| [element] | [GREEN/YELLOW/RED] | [action if needed] |

## Approval Recommendation: [Approve / Approve with Conditions / Do Not Approve]

**Rationale**: [explanation]

### Conditions (If Applicable)
| # | Condition | Owner | Deadline |
|---|-----------|-------|----------|
| 1 | [condition] | [who] | [when] |

## Ongoing Management Schedule

| Element | Frequency | Next Due | Responsible |
|---------|-----------|----------|-------------|
| [element] | [frequency] | [date] | [who] |

## Next Steps

| # | Action Item | Owner | Deadline | Priority |
|---|------------|-------|----------|----------|
| 1 | [action] | [who] | [when] | [high/medium/low] |
```

## Notes

- Data access scope is critical to risk classification. Vendors with access to personal or financial data are automatically at least MEDIUM risk.
- The agreement review step should invoke `/lawyer-os:review` if a vendor contract is available. If no contract is available yet, flag this as a blocker.
- If the vendor already has a context file, check for any historical issues, prior assessments, or notes from previous engagements.
- For vendors replacing an existing vendor, include transition planning (data migration, contract wind-down, parallel running period) in the next steps.
- If the vendor is a startup or early-stage company, additional DD on financial stability may be warranted even for MEDIUM-tier vendors.
- If the vendor operates in a jurisdiction with specific data localization or regulatory requirements, flag these in the compliance section.

## After Completion

- **Create a vendor context file** in `knowledge/contexts/partners/vendors/` for the new vendor with key terms, risk tier, and review schedule
- Suggest additional knowledge updates if relevant:
  - **Standards update**: "This vendor's terms revealed a gap in our vendor standards -- should I update?"
  - **Checklist improvement**: "This onboarding surfaced a DD element not on the standard checklist -- should I add it?"
  - **Decision log**: "Should I log this vendor approval decision in memory?"
