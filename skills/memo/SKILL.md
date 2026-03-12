---
name: memo
description: "Write a privileged legal memo analyzing a question or topic — structured analysis with risk assessment and actionable recommendations. Use when the user asks a legal question, needs legal analysis, or wants a formal legal memorandum."
---

# Legal Memo

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Write a privileged legal memorandum analyzing a legal question or topic. Structure the analysis by issue, assess risk using Severity x Likelihood, and provide clear, actionable recommendations calibrated to the audience.

## Workflow

### Step 1: Accept the Question

Accept the legal question or topic in any of these formats:
- **Direct question**: Stated question or topic in the conversation
- **File path**: Background document (PDF, DOCX) that frames the question
- **URL**: Link to a document in ~~cloud storage that provides context
- **Pasted text**: Factual background or prior analysis pasted into the conversation

If the question is vague or too broad, ask the user to narrow the scope before proceeding.

### Step 2: Gather Context

Ask the user for context before beginning the analysis:

1. **Who is the audience?** (CEO, engineering, BD/partnerships, board, other lawyers, external counsel)
2. **What is the urgency?** (need-it-now, this week, no rush -- affects depth of analysis)
3. **What triggered this question?** (specific deal, regulatory change, incident, planning exercise, board request)
4. **Desired outcome**: What decision does this memo need to support? (go/no-go, risk acceptance, strategy choice, compliance determination)
5. **Known constraints**: Any positions already taken, commitments made, or facts that narrow the analysis?
6. **Scope boundaries**: Should the memo cover [specific jurisdiction only / all jurisdictions]? [Specific entity only / all entities]?

If the user provides partial context, proceed with what you have and note assumptions. If the user says to skip context gathering, proceed directly. Default audience is the CEO (lead with recommendation, concise, business-oriented).

### Step 3: Load Knowledge

Read these files before starting the memo:

**Always load:**
- `knowledge/core/principles.md` — How to think and prioritize
- `knowledge/playbooks/legal-memo.md` — Memo structure and standards

**Load by topic** (infer from the question):
- `knowledge/core/organization.md` — If the question involves organization-specific context (entities, structure, regulatory posture)
- `knowledge/reference/legal-knowledge/compliance-and-licensing.md` — Licensing, registration, regulatory
- `knowledge/reference/legal-knowledge/payments-and-money-transmission.md` — Payments, money transmission, MTL
- `knowledge/reference/legal-knowledge/data-privacy.md` — Privacy, data protection, GDPR, CCPA
- `knowledge/reference/legal-knowledge/international-trade.md` — Cross-border, sanctions, export controls
- `knowledge/reference/legal-knowledge/corporate-and-governance.md` — Corporate, governance, securities
- `knowledge/reference/legal-knowledge/litigation-and-disputes.md` — Litigation risk, disputes, enforcement
- `knowledge/reference/legal-knowledge/intellectual-property.md` — IP, patents, trade secrets, open source

**Load contextual knowledge:**
- If the question relates to a specific entity or deal, load the relevant context file
- If the question references a specific agreement, load it

### Step 4: Frame the Issues

Break the question into discrete, analyzable legal issues:

| Issue | Legal Framework | Key Question |
|-------|----------------|-------------|
| Issue 1 | [applicable law/regulation] | [precise sub-question] |
| Issue 2 | [applicable law/regulation] | [precise sub-question] |
| Issue 3 | [applicable law/regulation] | [precise sub-question] |

Confirm the issue framing with the user if the question is complex or ambiguous.

### Step 5: Analyze Issue by Issue

For each issue:
- State the applicable legal rule or framework
- Apply the rule to the relevant facts
- Identify areas of uncertainty or judgment
- Consider counterarguments or alternative interpretations
- Note jurisdictional variations where relevant
- Reference precedent from loaded knowledge where available

### Step 6: Assess Risk

Apply the Severity x Likelihood framework to each identified risk:

| Risk | Severity | Likelihood | Overall | Mitigation |
|------|----------|-----------|---------|-----------|
| [risk description] | Critical/High/Medium/Low | High/Medium/Low/Remote | [combined assessment] | [recommended mitigation] |

**Severity scale:**
- **Critical**: Existential risk, regulatory shutdown, material litigation
- **High**: Significant financial exposure, enforcement action, reputational harm
- **Medium**: Moderate financial impact, operational disruption, compliance gap
- **Low**: Minor exposure, easily remediated, theoretical risk

**Likelihood scale:**
- **High**: More likely than not, known enforcement pattern
- **Medium**: Plausible, some precedent or analogous situations
- **Low**: Possible but unlikely, limited precedent
- **Remote**: Theoretical, no known precedent

### Step 7: Formulate Recommendation

Provide a clear, actionable recommendation:
- **Decision recommendation**: Go / no-go / conditional go (with specific conditions)
- **Risk acceptance framing**: If recommending to proceed despite risk, state what risk the business is accepting
- **Alternative approaches**: If there are multiple paths, compare them
- **Mitigation steps**: Specific actions to reduce identified risks

### Step 8: Write the Memo

Calibrate tone and detail to the audience:
- **CEO / executives**: Lead with the recommendation, then brief analysis, focus on business impact
- **Engineering / product**: Include technical detail, practical implementation guidance
- **BD / partnerships**: Focus on deal impact, negotiation implications, relationship considerations
- **Other lawyers / outside counsel**: Full analytical depth, legal citations, counterargument analysis
- **Board**: Executive summary format, governance implications, fiduciary considerations

### Step 9: Save or Post (If Connected)

If ~~cloud storage is connected, offer to save the memo to the appropriate location.

If ~~chat is connected and the user requests it:
- Post the recommendation summary (not the full privileged memo) to the relevant channel
- Flag that the full memo is privileged and available upon request

## Output Format

```
PRIVILEGED AND CONFIDENTIAL
ATTORNEY WORK PRODUCT

**To**: [audience]
**From**: [author]
**Date**: [date]
**Re**: [subject line -- descriptive but concise]

## Executive Summary

[2-3 sentence summary: the question, the answer, and the key risk. For executive audiences, this may be all they read.]

## Issue

[Precise statement of the legal question(s) being analyzed]

## Background

[Relevant facts and context organized chronologically or by topic]

## Analysis

### Issue 1: [Name]
**Applicable framework**: [law, regulation, or standard]
**Analysis**: [rule, application, conclusion]
**Uncertainty**: [areas of judgment or ambiguity]

### Issue 2: [Name]
[Same structure]

[Repeat for each issue]

## Risk Assessment

| Risk | Severity | Likelihood | Overall | Mitigation |
|------|----------|-----------|---------|-----------|
| [risk 1] | [level] | [level] | [combined] | [action] |
| [risk 2] | [level] | [level] | [combined] | [action] |

## Recommendation

[Clear, actionable recommendation with specific conditions or caveats]

## Alternative Approaches

[If applicable: other paths considered and why they were not recommended]

## Next Steps

| Action Item | Owner | Deadline | Priority |
|------------|-------|----------|----------|
| [action 1] | [who] | [when] | [high/medium/low] |
| [action 2] | [who] | [when] | [high/medium/low] |
```

## Notes

- Always mark output as PRIVILEGED AND CONFIDENTIAL / ATTORNEY WORK PRODUCT
- The audience parameter changes the level of detail and technicality. Memos for the CEO should lead with the recommendation; memos for lawyers can be more analytical.
- If the user provides a specific deal or partner context, load the relevant context file to inform the analysis
- For time-sensitive questions (need-it-now urgency), provide a shorter preliminary analysis and note areas that would benefit from deeper research
- If the question requires expertise outside the loaded knowledge (e.g., foreign law, tax, specialized regulatory), flag this and recommend engaging subject matter experts or outside counsel
- If the memo identifies a need for outside counsel, note the specific expertise needed and any conflict considerations

## After Completion

Suggest knowledge updates if relevant:
- **Decision log**: "Should I log this decision/recommendation in memory?"
- **Legal knowledge gap**: "This analysis surfaced a topic not covered in legal knowledge -- should I add it?"
- **Lesson learned**: "This analysis revealed [insight] -- should I note it for future reference?"
- **New context**: "Should I update the context file for [entity/deal] with this analysis?"
