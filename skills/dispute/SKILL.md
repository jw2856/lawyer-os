---
name: dispute
description: "Handle a demand letter, subpoena, regulatory inquiry, or litigation matter — classify, assess exposure, develop response strategy, and draft response. Use when the user receives a legal threat, dispute, demand letter, subpoena, or regulatory inquiry."
---

# Dispute Response

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Handle incoming dispute communications including demand letters, subpoenas, regulatory inquiries, complaints, and litigation matters. Classify the communication, assess exposure, determine if a litigation hold is needed, develop a response strategy, and draft the response.

## Workflow

### Step 1: Accept the Communication

Accept the dispute communication in any of these formats:
- **File path**: Local PDF, DOCX, or other document (demand letter, subpoena, complaint, regulatory letter)
- **URL**: Link to a document in ~~cloud storage or other document system
- **Pasted text**: Communication text pasted directly into the conversation
- **Description**: Verbal description of a dispute situation (e.g., "a customer is threatening to sue over service outage")

If no communication is provided, prompt the user to supply one.

### Step 2: Gather Context

Ask the user for context before beginning the analysis:

1. **What type of communication is this?** (demand letter, subpoena, regulatory inquiry, complaint filed, cease & desist, notice of claim, informal threat)
2. **When was it received?** (critical for calculating response deadlines)
3. **Who is the sender?** (law firm, regulator, individual, company -- and is there an existing relationship?)
4. **What is the deadline?** (stated response deadline, statutory deadline, or court-imposed deadline)
5. **Do we have outside counsel?** (already engaged, need to engage, or handling in-house)
6. **Related agreements**: Is there an underlying contract governing this relationship? (if so, provide it)
7. **Known facts**: What do we know about the underlying facts? Any prior communications?
8. **Insurance**: Do we have insurance that might cover this? (D&O, E&O, cyber, general liability)
9. **Board notification**: Is this material enough to require board notification?

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly. **Always identify and prominently flag any response deadline.**

### Step 3: Load Knowledge

Read these files before starting the analysis:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/core/organization.md` — Entity structure, key facts
- `knowledge/playbooks/dispute-response.md` — Dispute handling process

**Load by dispute type:**
- `knowledge/reference/legal-knowledge/litigation-and-disputes.md` — Litigation strategy, defenses, procedures
- `knowledge/reference/checklists/litigation-hold-checklist.md` — If litigation is reasonably anticipated
- `knowledge/reference/legal-knowledge/compliance-and-licensing.md` — If regulatory inquiry
- `knowledge/reference/legal-knowledge/data-privacy.md` — If data breach or privacy-related
- `knowledge/reference/legal-knowledge/intellectual-property.md` — If IP dispute

**Load contextual knowledge:**
- Load relevant context file for the counterparty or sender (if exists)
- Load the underlying agreement (if one exists and is relevant)

### Step 4: Classify the Communication

Determine the type, urgency, and required response:

| Classification Element | Assessment |
|----------------------|-----------|
| **Communication Type** | Demand letter / Subpoena / Regulatory inquiry / Complaint / C&D / Notice of claim / Other |
| **Sender** | [name, role, represented by counsel?] |
| **Subject Matter** | [contract dispute / IP / regulatory / employment / tort / other] |
| **Urgency Level** | Critical (response due within days) / High (response due within weeks) / Standard (30+ days) |
| **Response Deadline** | [specific date and time, with source of deadline] |
| **Jurisdiction** | [where filed or sent from, governing law] |
| **Amount at Stake** | [quantified if possible, or qualitative assessment] |
| **Materiality** | [material to business / routine / uncertain] |

### Step 5: Determine Litigation Hold Requirement

Assess whether a litigation hold is needed:

| Factor | Assessment |
|--------|-----------|
| **Is litigation reasonably anticipated?** | [yes/no/uncertain] |
| **Has a complaint been filed?** | [yes/no] |
| **Has a preservation demand been made?** | [yes/no] |
| **Recommendation** | [implement hold / not required / precautionary hold recommended] |

If a litigation hold is required, walk through `knowledge/reference/checklists/litigation-hold-checklist.md`:
- Identify custodians (employees with relevant documents or communications)
- Identify data sources (email, Slack, cloud storage, databases, backups)
- Draft preservation notice
- Document the hold implementation

### Step 6: Assess Merits and Exposure

Analyze the dispute on the merits:

| Element | Analysis |
|---------|----------|
| **Their claims/demands** | [summary of what they assert] |
| **Legal basis** | [contract, statute, tort, regulatory, other] |
| **Strength of their position** | [strong/moderate/weak, with reasoning] |
| **Our defenses** | [available defenses, affirmative and procedural] |
| **Strength of our position** | [strong/moderate/weak, with reasoning] |
| **Factual disputes** | [key facts that are uncertain or contested] |
| **Financial exposure** | [best case / likely case / worst case] |
| **Non-financial exposure** | [reputational, regulatory, precedent-setting, operational] |
| **Insurance coverage** | [likely covered / excluded / uncertain, policy and limits] |

### Step 7: Develop Response Strategy

Determine the appropriate response approach:

| Strategy Option | Pros | Cons | Recommended? |
|----------------|------|------|-------------|
| **Respond substantively on merits** | [pros] | [cons] | [yes/no] |
| **Respond procedurally only** | [pros] | [cons] | [yes/no] |
| **Seek extension of time** | [pros] | [cons] | [yes/no] |
| **Engage in settlement discussions** | [pros] | [cons] | [yes/no] |
| **Refer to outside counsel** | [pros] | [cons] | [yes/no] |
| **No response (if appropriate)** | [pros] | [cons] | [yes/no] |

Determine tone: firm / measured / conciliatory / neutral

### Step 8: Draft Response

Prepare the appropriate response document based on the strategy:
- **Demand letter response**: Address each claim, assert defenses, state position
- **Subpoena response**: Identify scope, assert objections, propose reasonable compliance
- **Regulatory inquiry response**: Cooperate while preserving rights, address each question
- **Settlement proposal**: If authorized, draft terms for resolution

Mark all drafts as PRIVILEGED AND CONFIDENTIAL / ATTORNEY WORK PRODUCT.

### Step 9: Identify Escalation Needs

| Escalation | Required? | Rationale | Timing |
|-----------|----------|-----------|--------|
| **Outside counsel** | [yes/no] | [why, and what expertise is needed] | [when to engage] |
| **Executive notification** | [yes/no] | [who needs to know, and what they need to know] | [when to notify] |
| **Board notification** | [yes/no] | [materiality threshold met?] | [when to notify] |
| **Insurance carrier notification** | [yes/no] | [policy requires notice of claim?] | [deadline for notice] |
| **Regulatory notification** | [yes/no] | [does this trigger any regulatory reporting?] | [deadline] |

### Step 10: Post to Chat (If Connected)

If ~~chat is connected and the user requests it:
- Post a brief summary (classification, urgency, deadline, recommended next step) to the relevant channel
- **Do not post the full analysis or draft response** -- these are privileged
- Flag that the full analysis is available upon request

## Output Format

```
PRIVILEGED AND CONFIDENTIAL
ATTORNEY WORK PRODUCT

## Dispute Response Summary

**Communication**: [document name/description]
**Sender**: [name, organization, counsel]
**Received**: [date received]
**Type**: [demand letter / subpoena / regulatory inquiry / complaint / other]
**Subject**: [brief description]
**Response Deadline**: [DATE -- PROMINENTLY DISPLAYED]
**Amount at Stake**: [quantified or qualitative]

## Classification

[Communication type, urgency level, materiality assessment]

## Litigation Hold

**Recommendation**: [Required / Not required / Precautionary hold recommended]
[If required: custodians, data sources, preservation steps, draft notice]

## Merits Assessment

### Their Position
[Summary of claims, legal basis, strength assessment]

### Our Position
[Available defenses, strength assessment, key factual issues]

### Exposure Analysis
| Scenario | Financial | Non-Financial | Likelihood |
|----------|----------|---------------|-----------|
| Best case | [amount] | [impact] | [%] |
| Likely case | [amount] | [impact] | [%] |
| Worst case | [amount] | [impact] | [%] |

## Business Impact

[What this means for the business: operational impact, relationship impact, precedent impact, resource requirements]

## Response Strategy

**Recommended approach**: [substantive / procedural / extension / settlement / outside counsel / no response]
**Tone**: [firm / measured / conciliatory / neutral]
**Rationale**: [why this approach]

## Draft Response

[Full draft response document, formatted appropriately for the communication type]

## Escalation Recommendations

[Outside counsel, executive notification, board notification, insurance carrier, regulatory -- with rationale and timing for each]

## Follow-Up Action Items

| # | Action Item | Owner | Deadline | Priority |
|---|------------|-------|----------|----------|
| 1 | [action] | [who] | [when] | [critical/high/medium] |
| 2 | [action] | [who] | [when] | [critical/high/medium] |
```

## Notes

- **Response deadlines are critical.** Always identify and prominently flag any deadline for response. Missing a deadline can result in default judgment, waiver of rights, or regulatory penalties.
- Litigation holds must be implemented immediately when litigation is reasonably anticipated. Failure to preserve evidence can result in adverse inference instructions or sanctions.
- Regulatory inquiries may require different handling than private disputes; always classify first. Some regulatory communications require cooperation, while others allow for more guarded responses.
- If the communication is in a language other than English, note this and determine if a translated response is needed.
- If the dispute involves multiple jurisdictions, identify which jurisdiction's law governs and whether parallel proceedings are possible.
- Never waive privilege inadvertently -- all analysis and draft responses should be marked as privileged.
- If the dispute appears to be frivolous or abusive, note this but still provide a professional response strategy.

## After Completion

Suggest knowledge updates if relevant:
- **Decision log**: "Should I log this dispute and the response strategy in memory?"
- **Context update**: "Should I update the context file for [counterparty] with this dispute history?"
- **Legal knowledge gap**: "This dispute involved [topic] not well covered in our knowledge base -- should I add it?"
- **Lesson learned**: "This response approach was [effective/ineffective] -- should I note it for future reference?"
- **Clause improvement**: "This dispute arose from [clause issue] -- should I update standards to prevent this?"
