# NDA Triage Playbook

## When This Applies

When screening an incoming NDA — whether received from a counterparty or when determining whether our standard template is appropriate.

## Required Context

- **Always**: `core/principles.md`, `core/standards.md`
- **If counterparty context exists**: Load from `contexts/`

## NDA Standards

### Entity
- The signing entity should be the appropriate entity per your organizational structure (see `core/organization.md`)
- NDA should cover your organization and its **affiliates** (subsidiaries, parent entities, commonly controlled entities)

### Templates
- **Mutual NDA**: Both parties are "Discloser" and "Recipient"
- **One-way NDA**: Your organization is "Company" (sole discloser), counterparty is "Recipient"
- Templates located in `reference/templates/` (customize the path in `core/organization.md`)

## Screening Process

### 1. Agreement Structure

- Is it mutual or unilateral? Confirm this matches the stated intent.
- Is it a standalone NDA (not embedded in another agreement)?
- Are the parties correctly identified with proper legal names?
- **Your standard (mutual):** Both parties are "Discloser" and "Recipient." Your entity should be identified by its full legal name (see `core/organization.md`).
- **Your standard (one-way):** Your organization is "Company" (sole discloser), counterparty is "Recipient."

### 2. Affiliate Coverage

- The NDA should cover your organization and its affiliates so you don't need separate NDAs per entity
- Definition of "affiliates" should be broad enough for current and future subsidiaries
- Affiliates should be able to both disclose and receive information under the same agreement
- If counterparty has affiliate coverage, your organization should have equivalent (mutual treatment)
- **GREEN**: Expressly extends to affiliates of both parties, or defines "party" to include affiliates
- **YELLOW**: Silent on affiliates (ambiguous — may require separate NDAs per entity). Affiliates covered only for one side.
- **RED**: Explicitly excludes affiliates or restricts to named signing entity only

### 3. Definition of Confidential Information

- Your standard template uses "Proprietary Information" (or equivalent) covering financial, business, legal, and technical information
- Marking requirements should be reasonable — we don't require all information to be formally marked
- **Standard exclusions (mutual — all 4 required):**
  1. Already known to the receiving party prior to disclosure
  2. Publicly available (not through breach)
  3. Independently developed without use of the confidential info
  4. Rightfully received from a third party without restriction
- **Standard exclusions (one-way — 3 required):** The one-way template omits "independently developed." If counterparty's one-way NDA includes it, that's acceptable (GREEN).
- **YELLOW**: Overbroad definition without reasonable exclusions
- **RED**: Requires marking for ALL disclosures with no oral/visual carveout; includes non-confidential business terms

### 4. Obligations of Receiving Party

- Use solely for the stated Purpose
- Maintain confidentiality using reasonable precautions
- Limit disclosure to Representatives with need-to-know bound by comparable obligations
- No reverse engineering of disclosed materials
- One-way: Recipient must promptly notify of any unauthorized use/disclosure
- **YELLOW**: Standard of care less than "reasonable." Missing reverse engineering prohibition.
- **RED**: No use restriction, or obligation to share with unrestricted third parties

### 5. Standard Carveouts

- **Mutual NDA — all 4 required:**
  1. Already known / prior possession
  2. Publicly available (not through breach)
  3. Independently developed
  4. Third-party receipt (without restriction)
- **One-way NDA — 3 required** (independent development not in our standard one-way, but acceptable if present)
- Legal compulsion is handled separately (Section 6), not as an exclusion
- **YELLOW**: Missing one non-critical carveout
- **RED**: Missing two or more carveouts, or no carveouts at all

### 6. Compelled Disclosures & Permitted Disclosures

- Disclosure permitted if required by law, regulation, or court order
- Must give prompt written notice (where legally permitted) so the other party can seek protective order
- Whistleblower protections are expressly preserved in our template
- Disclosure to Representatives with need-to-know is permitted if bound by comparable obligations
- **YELLOW**: No notice requirement for compelled disclosures. Missing whistleblower safe harbor.
- **RED**: No compelled disclosure provision at all, or overly narrow permitted disclosures

### 7. Term and Duration

- **Mutual**: Agreement terminates on written notice (for future disclosures). Confidentiality survives **5 years** after termination. Trade secrets survive **indefinitely**.
- **One-way**: Obligations survive until Recipient can document info falls into an exception (potentially indefinite).
- **GREEN**: Survival of 3-5 years for mutual; indefinite for one-way
- **YELLOW**: Survival shorter than 3 years (mutual) or shorter than 5 years (one-way). Term longer than 5 years for a mutual NDA.
- **RED**: Perpetual obligations on BOTH parties in a mutual NDA with no trade secret exception. No termination mechanism.

### 8. Return and Destruction

- On termination, return or destroy all Proprietary Information and materials (all copies and derivatives)
- Our template does NOT include a retention exception for legal/compliance archival — if counterparty's NDA includes one, that's acceptable (GREEN, common market term)
- **YELLOW**: No certification of destruction available. Overly broad retention rights.
- **RED**: No return/destruction obligation at all

### 9. Remedies

- Injunctive relief available without bond for breach or threatened breach
- Prevailing party entitled to attorneys' fees
- **YELLOW**: Injunctive relief requires posting bond. No attorneys' fees provision. Indemnification clause for breach (acceptable but not in our standard).
- **RED**: Liquidated damages. Limitation of liability that would cap remedies for confidentiality breach. Waiver of injunctive relief.

### 10. Problematic Provisions

Flag any of these — they do NOT belong in an NDA:
- Non-solicitation clauses (**YELLOW** if limited to 12 months, **RED** if broad)
- Non-compete clauses (**RED**)
- Exclusivity or standstill provisions (**RED**)
- Broad residuals clause (**YELLOW** if narrowly scoped to unaided memory, **RED** if broad or grants IP license)
- IP assignment or license grants (**RED**)
- Audit rights (**YELLOW** if limited and reasonable, **RED** if broad/unlimited)
- Warranty of accuracy of disclosed information (**YELLOW**)
- Any obligation to proceed with a transaction (**RED** — our template expressly disclaims this)

### 11. Governing Law and Dispute Resolution

- **Domestic**: Your preferred governing law and courts with exclusive jurisdiction (see `core/standards.md`). Email notices effective within 24 hours.
- **International**: Arbitration in your preferred seat under applicable international arbitration rules (see `core/standards.md`).
- **Assignment**: One-way prohibits Recipient from assigning without your consent; your organization can freely assign. Mutual does not restrict assignment.
- **GREEN**: Your preferred jurisdiction (see `core/standards.md`), or other reasonable US jurisdiction
- **YELLOW**: Non-preferred US jurisdiction. Mandatory arbitration for domestic counterparty. Reasonable foreign jurisdiction for international counterparty.
- **RED**: Exclusive foreign jurisdiction for US counterparty. Governing law with no connection to either party. Prohibition on your organization assigning.

## Classification & Routing

- **GREEN**: All sections align with or better than our standard. Route for signature via standard delegation.
- **YELLOW**: Minor deviations in 1-3 sections. No RED items. Single counsel review pass likely sufficient.
- **RED**: Any RED-flagged item present. Requires full legal review, negotiation, or counterproposal using our standard template.

## Risk Scoring

When quantifying risk for specific items:
- Score = Impact (1-5) x Likelihood (1-5)
- 1-4: GREEN (Low risk)
- 5-9: YELLOW (Moderate risk)
- 10-15: YELLOW/ORANGE (Significant risk)
- 16-25: RED (High risk)
