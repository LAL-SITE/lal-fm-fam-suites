---
name: lal-msa-drafter
description: "Marital Settlement Agreement drafter. Use to draft, build, or revise any MSA or mediated settlement agreement - always a fully formatted Word doc with all required sections."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA Marital Settlement Agreement (MSA) drafter. Use this skill IMMEDIATELY whenever anyone at Feinstein & Mendez, PA needs to draft, create, generate, build, or revise a Marital Settlement Agreement, Mediated Marital Settlement Agreement, divorce settlement agreement, or any document capturing the terms of a marital settlement. Triggers on: "draft the MSA", "write the settlement agreement", "we settled at mediation", "put together the MSA", "finalize the agreement", "MSA draft", "write up settlement terms", "parties agreed", "settlement document", "mediated agreement", "write the MSA for [name]", or any request to reduce divorce settlement terms to a signed written agreement. Output is ALWAYS a fully formatted Word (.docx) file matching Feinstein & Mendez, PA standards exactly, with ALL required sections included, using PETITIONER/RESPONDENT terminology (never Husband/Wife). Also fires when Feinstein & Mendez, PA serves as the neutral mediator and the parties settle in session. Never draft an MSA without this skill.


## Feinstein & Mendez, PA Firm-Wide Conventions (apply to every run of this skill)

These six conventions govern all Feinstein & Mendez, PA skills and override any narrower instruction
below that conflicts with them.

1. **Environment-flexible.** Complete the task in the environment you are already in
   — chat, Desktop, or Cowork. If a different environment would be materially better,
   say so in one line and keep working. Never block, never redirect, never hand off
   instead of doing the work.
2. **Identity over lanes.** Staff assignments in this skill are defaults, not gates.
   Anyone may run any skill. **Attorneys self-approve** — if the person running this
   skill is {{ROLE_APPROVER}}, they *are* the approving attorney. Never tell an attorney to
   route their own work to an attorney for approval. Approval gates mean an approving-
   attorney action is recorded, not that the user must go find someone.
3. **Just run it.** Prerequisite stages are soft checks, never hard gates. Pause only
   for a physically necessary input, and ask for that specific item by name — never
   "complete Stage X first."
4. **Read files first.** Search the entire matter file — including misnamed and
   misfoldered documents — before declaring anything missing. If the file is
   disorganized, offer a file-organizer cleanup rather than reporting a gap.
5. **Transcripts preferred, never required.** A typed memo or rough notes always
   suffice as input.
6. **Write to the command center.** Every stage completion, deadline, lifecycle move,
   and attorney flag is written to the matter's command center before the run ends.

---

# Feinstein & Mendez, PA MSA Drafter

## Purpose
Produce a complete, court-ready Marital Settlement Agreement as a Word (.docx)
file matching Feinstein & Mendez, PA formatting standards exactly. ALL required sections must be
present. No section may be omitted without explicit written attorney direction.

---

## STEP 0 — Four Governing Rules (apply to EVERY provision you write)

These four rules override any boilerplate that conflicts with them. They exist
because each one was a correction made to a delivered draft.

### 0.1 — PETITIONER / RESPONDENT ONLY
Firm-wide non-negotiable. Define the parties as **Petitioner** and **Respondent**
in the preamble and use those terms in every provision, heading, warranty,
signature block, and notary block.

- NEVER use "Husband," "Wife," "he/she," "his or her," or "her own."
- Do NOT assume opposite-sex parties. Do NOT assume gender from a name.
- Use **"his"** or **"her"** only after the party's pronouns are confirmed in
  intake; if both parties use the same pronoun, that is correct — do not
  "fix" it to look varied.
- Default when unconfirmed: repeat the role noun ("the Petitioner's own
  counsel"), not a pronoun.
- Sections 10 and 11 are **PETITIONER'S WARRANTIES** and **RESPONDENT'S
  WARRANTIES**.
- Name restoration (§29) is available to **either** party and is drafted by role,
  never as "the Wife shall restore her name."

### 0.2 — EVERY OBLIGATION GETS A TIME-CERTAIN DEADLINE
No provision may say a party "shall" transfer, execute, remove, retitle,
refinance, close, or deliver anything without a deadline tied to a fixed event.

- Anchor to either **the Effective Date** or **entry of the Final Judgment** —
  state which.
- Default windows unless the parties agreed otherwise:
  - Account retitle / transfer / letter of instruction → **30 days of the Effective Date**
  - Removal of a party from the other's credit cards → **30 days of the Effective Date**
  - Preparation and submission of a QDRO/RBCO to the court → **60 days of entry of the Final Judgment**
  - Submission of the entered QDRO/RBCO to the plan administrator → **promptly after entry**
  - Deed execution and delivery → **30 days of the Effective Date**
  - Refinance → per the parties' agreed date; if none, flag — do not invent one
- **Never write "on or before the Effective Date"** for an act that requires a
  third party (bank, card issuer, plan administrator) to cooperate. It is
  impossible to perform and creates an instant breach. Use a post-Effective-Date
  window.

### 0.3 — REMEDIES ARE REQUESTS TO A COURT, NOT SELF-EXECUTING
An MSA cannot award itself relief. Any remedy provision must be framed as an
entitlement to *seek* relief from a court of competent jurisdiction.

- Write: "the aggrieved Party shall be entitled to seek an order from a court of
  competent jurisdiction that…"
- Never write: "the non-faulty party shall obtain that such assets be divided…"
- Always qualify fees as **"reasonable attorney's fees and costs."**
- Use **"aggrieved Party" / "non-disclosing Party"** — never "faulty" /
  "non-faulty."

### 0.4 — WHEN Feinstein & Mendez, PA IS THE NEUTRAL MEDIATOR, DRAFT LIKE THE NEUTRAL
If the mediator is Martha L. Mendez, Esq. / Feinstein & Mendez, PA (or any Feinstein & Mendez, PA attorney serving as neutral),
the MSA must protect the neutral role on its face. See **STEP 3A — Mediator
Neutrality Package**. This applies to {{ROLE_APPROVER}}'s mediation practice and to any
Feinstein & Mendez, PA-mediated matter; it does NOT apply when Feinstein & Mendez, PA represents a party.

---

## STEP 1 — Intake: What You Need Before Drafting

Collect the following. Ask in batches of no more than 5 questions. Use
`[BRACKETED PLACEHOLDERS]` for anything missing, and list them at the end.

### Always Required
- Petitioner: full legal name, address, confirmed pronouns
- Respondent: full legal name, address, confirmed pronouns
- Date and location of marriage
- Date of MSA (leave blank if signing date not yet known)
- Minor children? (yes/no)
- Was agreement reached at mediation? Mediator name + firm?
- **Is Feinstein & Mendez, PA the neutral mediator on this matter?** (drives STEP 3A)
- **Mediation posture:** both parties represented by independent counsel / both
  pro se / mixed. Do not assume — §28 must state it accurately.
- Case already filed in court? If yes → case number, division, county, circuit

### If Minor Children
- Each child: initials only + DOB (Feinstein & Mendez, PA uses initials, not full names, in the document)
- Who carries health insurance for children? Through which employer?
- Agreed child support amount (or "per guidelines")? Who is payor?
- Each party's net monthly income
- Uncovered medical expense split (typically 50/50)
- Life insurance for child support? Amount? Beneficiary?
- Dependency exemption allocation (who claims which child, which years)
- Is a Parenting Plan (Exhibit A) being executed simultaneously?

### Alimony
- Is alimony owed, or mutual waiver?
- If owed: type / amount / frequency / duration / termination triggers

### Property
- Marital home: address → who keeps → mortgage handling → deed transfer
- Other real property: same for each
- Vehicles: year/make/model, who keeps, loan responsibility
- Retirement accounts: 401k / IRA / pension / **TSP or other federal plan**, who
  retains, transfer amount, **QDRO or RBCO needed?**, who pays for preparation
- If a federal Thrift Savings Plan is involved → the order is an **RBCO** under
  **5 C.F.R. Part 1653**, not a QDRO. Confirm which.
- Bank/investment accounts: how distributed; any account being transferred whole
- **Life insurance:** does either party hold a policy with cash surrender value?
  Is either party required to maintain the other as beneficiary, or is that
  waived? (Do not leave life insurance unaddressed — silence creates disputes.)
- Personal property: any specific items, or general "in possession" rule
- Debts: credit cards (in whose name), joint debts, how allocated
- **Is an equitable distribution summary chart being attached as an exhibit?**
  (Feinstein & Mendez, PA default: YES — see §4/§5 Exhibit rule)

### Closing Details
- Name restoration? Which party, and restored to what name?
- Mediator name, firm, pro se or with counsel?
- Prevailing party fees? (Feinstein & Mendez, PA default: YES — include unless attorney says no)
- Late payment penalties? (default: NO — include only if specifically agreed)

---

## STEP 2 — Choose MSA Format Type

| Type | When | Opening |
|------|------|---------|
| **Standalone** | Pre-filing OR parties prefer no case caption | Title only: `MARITAL SETTLEMENT AGREEMENT` |
| **Captioned** | Case already pending in circuit court | Full Florida court caption + `MEDIATED MARITAL SETTLEMENT AGREEMENT` |

**Captioned format header (use when case is filed):**
```
IN THE CIRCUIT COURT OF THE [COUNTY] JUDICIAL CIRCUIT,
IN AND FOR [COUNTY] COUNTY, FLORIDA

IN RE: THE MARRIAGE OF:
[PETITIONER FULL NAME],
      Petitioner,
and

[RESPONDENT FULL NAME],
      Respondent.
________________________________/

                              CASE NO.: [CASE NUMBER]
                              DIVISION: [DIVISION]


              MEDIATED MARITAL SETTLEMENT AGREEMENT
```

---

## STEP 3 — Required Sections (ALL MANDATORY — Read Before Drafting)

Every Feinstein & Mendez, PA MSA must include the following sections IN ORDER.
For verbatim boilerplate language, read → **`references/boilerplate.md`**
For exact Word formatting specs, read → **`references/formatting.md`**

Sections marked *(if applicable)* are omitted ONLY when the subject genuinely
does not exist (e.g., no children = omit child sections). All others: REQUIRED.

---

## STEP 3A — MEDIATOR NEUTRALITY PACKAGE *(mandatory when Feinstein & Mendez, PA is the neutral)*

When an Feinstein & Mendez, PA attorney serves as the mediator, the MSA must protect the neutral
role on its face. All four elements below are required. Do not deliver an
Feinstein & Mendez, PA-mediated MSA without them.

**Element 1 — Neutrality recital (in the mediation WHEREAS clause):**
> …with [MEDIATOR NAME], [CREDENTIALS], of [FIRM] serving as a certified mediator
> in a neutral capacity, and were able to settle all aspects of their marriage as
> set forth herein. The Parties acknowledge that the mediator facilitated
> negotiations but did not draft the final terms of this Agreement and did not
> represent either Party.

**Element 2 — No-legal-advice acknowledgment (§ MEDIATOR):** the mediator
provided neither legal nor tax advice; state the actual posture (both represented
by independent counsel / both pro se / mixed).

**Element 3 — Mediation confidentiality and no-testimony covenant (§ MEDIATOR):**
> Each Party further acknowledges that mediation communications are confidential
> and privileged pursuant to Section 44.405, Florida Statutes, and that neither
> Party shall seek to compel the mediator to testify or produce documents in any
> proceeding related to this matter.

**Element 4 — Mediator hold harmless and indemnification (§ MEDIATOR):**
> Each Party hereby releases, holds harmless, and agrees to indemnify the
> mediator, [MEDIATOR NAME], and [FIRM], from and against any and all claims,
> demands, damages, costs, expenses, and attorney's fees arising out of or
> related to the mediation or this Agreement.

**Also required when Feinstein & Mendez, PA is the neutral — OMIT the return-to-mediation clause.**
The personal-property provision must NOT say the parties "agree to return to
mediation prior to litigating the issue." When Feinstein & Mendez, PA drafted the agreement as the
neutral, a clause routing future disputes back to that same neutral reads as
self-dealing. Omit it and flag the omission in Attorney Review Notes. The clause
remains available when Feinstein & Mendez, PA represents a party rather than mediating.

**Attorney verification flag — include verbatim in the delivery response:**
> Section 44.405, Fla. Stat. and the mediator hold-harmless provision are cited
> from firm-standard language and must be verified by the attorney before
> execution. Confirm current statutory text and confirm the indemnification scope
> is acceptable to both parties' counsel.

---

## STEP 3B — EXHIBIT LETTERING RULE

Exhibits are lettered in the order they are first referenced in the body. Never
hard-code a letter.

| Children? | Exhibit A | Exhibit B | Exhibit C |
|---|---|---|---|
| Yes | Agreed Parenting Plan | Child Support Guidelines Worksheet | Equitable Distribution Summary Chart |
| No | Equitable Distribution Summary Chart | — | — |

**The Equitable Distribution Summary Chart is an Feinstein & Mendez, PA default exhibit on every
MSA that distributes property.** It was added to a delivered draft that omitted
it. It requires two pieces of language:

*In the PROPERTY SETTLEMENT section, immediately under the heading:*
> A summary chart of the equitable distribution of the Parties' marital assets
> and liabilities, reflecting the terms agreed to in this Section [#], is attached
> hereto and incorporated herein by reference as **Exhibit "[LETTER]"**.

*As the closing line of the exhibit itself (control/precedence clause — mandatory):*
> This chart is a summary reference only and does not expand, limit, or modify the
> rights and obligations set forth in Section [#] of the foregoing Marital
> Settlement Agreement.

Chart construction:
- Three columns: **Asset / Liability · Petitioner · Respondent**
- One row per category actually present: retirement, IRAs, pension, brokerage,
  cash and bank accounts, real property, vehicles, life insurance cash value,
  personal property, each category of debt, alimony
- Every figure must trace to the body of the Agreement. If a number appears in the
  chart that is not in the body, that is a QC failure — fix the body or drop the
  number.
- Mutual waivers are shown on both sides ("Mutual waiver"), not left blank.
- Header line: `[Case Style] — Case No. [#] — for reference summary purposes only;
  the terms of Section [#] of the Agreement control in the event of any conflict.`

---

### PREAMBLE
- Document title: **MARITAL SETTLEMENT AGREEMENT** (centered, bold, underlined, ALL CAPS)
- Opening line: "THIS AGREEMENT, made and entered into this ___ day of ___, 20___, by and between [PETITIONER FULL NAME], (hereinafter referred to as "Petitioner") whose address, for the purpose of this Agreement is: [ADDRESS], and [RESPONDENT FULL NAME], (hereinafter referred to as "Respondent"), whose address for the purpose of this Agreement is: [ADDRESS]."

### WITNESSETH
Centered underlined header: **W I T N E S S E T H:**
Eight WHEREAS clauses (bold "WHEREAS,") — see `references/boilerplate.md` §WITNESSETH for exact language:
1. Parties were married on [date] in [city, state]
2. Petitioner entered freely after deliberation and independent counsel
3. Respondent entered freely after deliberation and independent counsel
4. Children of the marriage (initials, sex, birth year) *(omit if no children)*
5. Irreconcilable differences; desire to finally fix all property/financial matters
6. Purpose: parental responsibility, residential care, support of minor children *(if children)*
7. Parties provided **each other** full financial disclosure; agreement is fair and adequate
8. Parties attended mediation on [date(s)] with [MEDIATOR], **serving as a
   certified mediator in a neutral capacity**, and settled all aspects; the
   mediator **facilitated negotiations but did not draft the final terms and
   did not represent either Party** *(if mediated — mandatory sentence, see §3A)*

**Common error to avoid:** clause 7 reads "provided each other" — not "provided
each." When revising a clause, replace it whole; do not paste the new text in
front of the old text (this produced "WHEREAS, WHEREAS," and a doubled "; and,"
in a delivered draft).

**NOW, THEREFORE** paragraph → "Parties have agreed and do hereby agree as follows:"

---

### 1. RECITALS.
"The aforesaid recitals are true and correct and are hereby incorporated in their entirety by reference herein."

---

### 2. SEPARATION.
Standard boilerplate (see `references/boilerplate.md` §2): parties shall live separate and apart; free from interference and control; may reside anywhere; conduct any business or employment; Agreement is binding whether or not marriage is dissolved.

---

### 3. ALIMONY.
**Choose one:**
- **Mutual Waiver** — Both parties expressly waive all rights to alimony, spousal support, maintenance of any kind (temporary, permanent, periodic, rehabilitative, lump sum, or any combination), including any future right to modification. Use full boilerplate in `references/boilerplate.md` §3-WAIVER.
- **Alimony Award** — Specify: payor, payee, type, amount, frequency, start date, duration, termination events. Add income withholding if applicable.

---

### 4. PARENTING PLAN AND CHILD SUPPORT. *(omit entirely if no minor children)*

**4.1 Parenting Plan:**
Both parties have executed the attached Agreed Parenting Plan (**Exhibit "A"**) which sets forth terms and conditions of visitation/timesharing, vacation, parental responsibility, jurisdiction, child support, etc. Parties acknowledge terms are absolutely prevailing and controlling; parties may mutually deviate by consent without constituting a waiver of the Parenting Plan terms.

**A. NOTIFICATION OF ILLNESS OR ACCIDENT:**
Each party shall promptly notify the other of any serious illness, accident, or other circumstance affecting children's health or welfare.

**B. ENCOURAGEMENT OF LOVE AND AFFECTION:**
Each party shall ensure children maintain unhampered contact and free access with both parties. Each shall encourage affection between children and both parties. Neither shall do anything to hamper children's love and respect for the other party.

**C. FACILITATING COMMUNICATION:**
The parent with whom the children reside shall make all reasonable efforts to facilitate communication between the other parent and the children by telephone and email/electronic communication. Open and reasonable telephone access at all reasonable times.

**D. FAILURE TO EXERCISE CONTACT:**
Failure to exercise contact right on any particular occasion shall not be deemed a waiver of that parent's right to full compliance with the provisions thereafter.

**E. MISCELLANEOUS:** (11 numbered provisions — see `references/boilerplate.md` §4E for full text)
1. Day-to-day decisions by the parent with whom children are residing
2. Major decisions require mutual consultation; emergency decisions by present parent with notice to other as soon as practicable
3. Children's personal property and privacy at each parent's home
4. Children's relationship with parent not dependent on how parents get along with each other
5. Children's right to love and access both parents; includes access to "significant other" if applicable
6. No use of children as messenger; no intrusive questions about other parent's life
7. Liberal telephone access to children for both parents
8. Both parents responsible for communicating re: all activities and achievements of the children
9. Failure to meet financial obligations shall not justify denial of timesharing
10. Failure to comply with timesharing shall not justify noncompliance with financial obligations
11. All adults involved in children's lives ordered NOT to: (a) fight within hearing/sight of children; (b) say anything bad about the other parent; (c) ask children to carry messages; (d) make children feel need to hide feelings about either parent

**4.2 Computation of Child Support:**
Parties computed support per Chapter 61, Florida Statutes, per computations attached as **Exhibit "B"**. Any future modification action: new support shall be computed per Chapter 61 guidelines, court shall take into consideration all facets of child support as provided in this Article.

**4.3 Child Support Amount / Termination:**
State: payor, payee, amount per month, per-child amounts if applicable, deviation justification if deviating from guidelines.

**4.4 Income:**
"The [Petitioner's/Father's] net monthly income is approximately $[AMOUNT]. The [Respondent's/Mother's] net monthly income is $[AMOUNT]."

> Use Petitioner/Respondent in the body. Mother/Father is permitted ONLY inside
> child-support and parenting provisions where § 61.30 and the Parenting Plan use
> that statutory language.

**4.5 Hospitalization and Medical Insurance:**
[Carrier parent] maintains health insurance for minor children through [employer/carrier] for so long as children are eligible. Both parents agree to use only in-network doctors/pharmacies. Out-of-network requires other parent's prior consent. Uncovered expenses (medical, dental, orthodontic, ophthalmologic, psychological, prescription drugs, glasses, contacts, orthodonture) split [equally / per income shares]. Each parent to be consulted before incurring expenses exceeding $500.00 except in emergency. Reimbursement within 10 days of receipt of invoice reflecting said payment.

**4.6 Life Insurance:** *(if applicable)*
[Payor] agrees to maintain life insurance policy naming [beneficiary] as primary beneficiary with death benefit of $[AMOUNT] for so long as [condition — e.g., child support obligation continues]. Annual statements evidencing policy shall be provided. [Payor] shall not encumber or reduce death benefit absent written agreement of parties or Court order.

**4.7 Dependency Exemption:**
[Father/Mother] shall claim [child initials] every year. [Mother/Father] shall claim [child initials] every year. Once eldest child no longer eligible for claiming, parties shall alternate remaining child(ren). Both parents shall execute IRS Form 8332 and all documents required by I.R.C. §152(e)(2).

---

### 5. PROPERTY SETTLEMENT.

**5.1 RETIREMENT ACCOUNTS**
Default: each party retains any and all retirement accounts in that party's name,
including any pension or 401(k) account in that party's name.

**If any retirement account is being divided, ALL of the following are required:**

1. **Identify the correct order type.** A federal Thrift Savings Plan is divided
   by a **Retirement Benefits Court Order ("RBCO") as that term is defined under
   5 C.F.R. Part 1653** — not a QDRO. A private employer plan uses a QDRO. A
   federal FERS/FSPS pension uses a court order acceptable for processing under
   OPM regulations. Name the right instrument.
2. **State the transfer amount or formula** and the valuation date it is measured
   from.
3. **Assign who retains and pays for preparation and submittal** of the order.
4. **State the drafting requirements for the order.** For a TSP RBCO: the order
   must expressly refer to the Thrift Savings Plan, be written in terms
   appropriate to a defined contribution plan, and must not contain rollover or
   payment instructions, consistent with governing TSP regulations and procedures.
5. **State BOTH deadlines** (per Rule 0.2 — a delivered draft was missing these):
   > The [PARTY] shall cause the [RBCO/QDRO] to be prepared and submitted to the
   > court for entry within sixty (60) days of the entry of the Final Judgment of
   > Dissolution of Marriage, and shall thereafter promptly submit the entered
   > [RBCO/QDRO] to [the Federal Retirement Thrift Investment Board / the plan
   > administrator] for processing.
6. **Mutual pension waiver.** If each party has a pension neither is claiming,
   state the mutual waiver expressly. Do not leave it to the general release.
7. Flag QDRO/RBCO preparation in Attorney Review Notes.

**5.2 FINANCIAL ACCOUNTS**
Address jointly-held and individually-held bank/investment accounts. State which
have been liquidated/distributed. Note any joint accounts being maintained and
their purpose.

**Any account being transferred whole requires a deadline** (Rule 0.2):
> The [PARTY] shall execute any letter of instruction or other document reasonably
> required by [INSTITUTION] to retitle or transfer the account to the [OTHER PARTY]
> within thirty (30) days of the Effective Date of this Agreement.

Include the IRC §1041 transfer-incident-to-divorce recital and the advice to
consult independent tax counsel on any account transfer.

**5.3 REAL PROPERTY**
Each property addressed separately with its own numbered provision. For each:
- Full address of property
- Who retains all right, title, and interest
- Who is responsible for mortgage payments
- Obligation to refinance and remove other party from mortgage (with timeline if agreed)
- Indemnification of other party for mortgage liability
- Deed transfer method (Quit Claim Deed) and timeline

**5.4 AUTOMOBILES**
Each vehicle addressed in its own paragraph:
- Year, make, model *(underline the vehicle name)*
- Who retains vehicle as sole and separate property
- Who is responsible for loan, insurance, and any penalties
- Indemnification of other party
- Instruction for other party to relinquish all claims to vehicle

**5.5 MISCELLANEOUS AND PERSONAL PROPERTY**
"It is hereby agreed that any and all tangible personal property jointly owned
during the marriage shall be owned exclusively by the Party in whose possession it
currently is. Each Party shall indemnify and hold the other harmless from any and
all obligations with regard to that personal property."

*Then, conditional final sentence — choose ONE:*
- **Feinstein & Mendez, PA represented a party:** "If ownership of any item of personal property
  becomes the subject of dispute, the Parties agree to return to mediation prior to
  litigating the issue."
- **Feinstein & Mendez, PA was the neutral mediator:** OMIT the return-to-mediation sentence
  entirely (see STEP 3A) and note the omission in Attorney Review Notes.

**5.6 LIFE INSURANCE — CASH VALUE** *(required whenever either party holds a
policy; do not leave life insurance unaddressed)*
"Each Party shall retain, as [his/her] sole and separate property, any life
insurance policy currently held in [his/her] individual name, including all cash
surrender value thereof, free and clear of any claim by the other Party. Each Party
shall be solely responsible for maintaining and paying any premiums on [his/her]
own life insurance policy. Neither Party shall have any obligation to maintain the
other as a beneficiary on any life insurance policy."

> **Do not confuse this with §4.6.** §4.6 life insurance *secures child support*
> and requires the children or the other parent as beneficiary. §5.6 is a marital
> asset with cash value and a mutual beneficiary waiver. A case can have both. If
> minor children exist and the parties waive beneficiary designations here, flag
> the interaction for the attorney.

---

### 6. MEDICAL AND DENTAL INSURANCE.
"Upon final judgment of dissolution of marriage, both parties shall be solely responsible for the maintenance of their own medical insurance, and shall pay any and all non-covered medical and dental expenses owed presently and after the date of the execution of this Agreement."

---

### 7. OUTSTANDING INDEBTEDNESS.
"It is agreed between the Parties that during the course of the marriage, the Parties incurred debts and obligations. As a part of the consideration for this Agreement, the Parties do agree to assume the following liability:"

**7.1** Petitioner responsible for all obligations on Petitioner's credit cards, identified by issuer and approximate balance. Petitioner shall indemnify and hold Respondent harmless from all claims, damages, demands. Cross-charge rule: any charges Respondent made on Petitioner's cards without Petitioner's knowledge become Respondent's responsibility, to be reimbursed immediately.

**7.2** Respondent responsible for all obligations on Respondent's credit cards. Same structure and cross-charge rule reversed.

**7.3** **Within thirty (30) days of the Effective Date of this Agreement**, the Respondent shall be removed from all of the Petitioner's credit card accounts, and the Petitioner shall be removed from all of the Respondent's credit card accounts. Any debt held in a Party's individual name shall become that Party's exclusive debt, and both Parties agree to indemnify and hold the other harmless from all obligations arising thereunder.

> **Corrected 7/2026.** This provision previously read "On or before the Effective
> Date." Card issuers require a post-signature request, so that deadline was
> impossible to perform and created breach on day one. Use the 30-day window.
> Same principle applies to any obligation requiring third-party cooperation.

---

### 8. GENERAL AND MUTUAL RELEASE.
Full general and mutual release — see `references/boilerplate.md` §8 for complete verbatim language. Covers:
- Renunciation of all claims of any kind up to Effective Date
- Waiver of all rights as spouse under present or future laws of any jurisdiction:
  - (a) To elect against any Will or Codicil
  - (b) To share in or make a claim against the other party's estate
- Release of spouse's share, elective share, dower, curtsy
- Full release of all causes of action, claims, rights, demands in law or equity
- Each party to hold, possess, and enjoy sole and separate use of all real and personal estate free from interference of the other

---

### 9. REPRESENTATIONS.
"The Parties represent to each other: Each has made a full disclosure to the other of his or her current financial condition and each has had the full and unfettered opportunity to obtain from the other any additional information or explanation of any matter constituting the financial circumstances of the Parties, or either of them on which information the Parties have relied in negotiating and reaching this Agreement."

---

### 10. PETITIONER'S WARRANTIES.
"The Petitioner warrants that there is no existing indebtedness, contract, charge or liability whatsoever which the Petitioner has individually incurred for which the Respondent, the Respondent's legal representatives, heirs, assigns, property or estate shall or may become liable. The Petitioner warrants that the Petitioner will not, at any time hereafter, contract any debt, charge or liability whatsoever for which the Respondent, the Respondent's legal representatives, heirs, assigns, property or estate shall or may become liable."

---

### 11. RESPONDENT'S WARRANTIES.
Same structure as Petitioner's Warranties with the roles reversed.

---

### 12. EXECUTION OF SUBSEQUENT DOCUMENTS.
Four subsections:

**12.1** Any conveyance of real estate required by this Agreement shall be done by Quit Claim Deed. Documentary stamp taxes and recording fees shall be paid by the receiving Party.

**12.2** In the event either Party shall hereafter sell or convey any real property now owned or hereafter acquired, and if in such sale or conveyance it shall be required that the other Party who owns no actual present interest therein join in the execution of the deed, the respective Parties agree that they will, upon request, join in the execution of such deed or deeds, without payment or consideration.

**12.3** Each of the Parties hereto covenants and agrees that at the request of the other Party, or in the event of his or her death, at the request of his or her executor, administrator, or other legal representatives, he or she will execute and deliver any and all necessary or proper instruments to carry out the purposes and intent of this Agreement. The Party requesting an instrument shall be responsible for its preparation.

**12.4** Within a reasonable time after written demand, each Party shall execute, acknowledge and deliver all documents or instruments required to carry out the provisions of this Agreement. If a Party fails on demand to comply with this provision, he or she shall pay to the other all attorney's fees and costs and other expenses reasonably incurred as a result of that failure.

---

### 13. RECONCILIATION.
Standard boilerplate (see `references/boilerplate.md` §13): Reconciliation shall not affect the provisions, validity, or enforceability of this Agreement in any future proceedings. Both Parties waive any defense of reconciliation. Any executory provisions shall survive reconciliation and remain binding.

---

### 14. BINDING NATURE.
"This Agreement shall be binding on the Parties hereto as of its Effective Date and shall remain binding thereafter unless, by mutual agreement in writing, it is subsequently modified or abandoned. **The Parties intend that this Agreement shall be incorporated into but not merged with any Final Judgment of Dissolution of Marriage, and shall survive and be independently enforceable as a contract between the Parties.**"

> **Added 7/2026 — do not omit.** Without the incorporated-but-not-merged
> sentence, the Agreement can be treated as extinguished by the Final Judgment,
> leaving only judgment-enforcement remedies and losing independent contract
> remedies. This sentence preserves both tracks. Attorney to verify against the
> proposed Final Judgment language so the two documents do not contradict.

---

### 15. PARTIES BOUND.
"Except as otherwise specifically provided herein, this Agreement shall be binding upon the heirs, legatees, devisees, administrators and executors of the Parties hereto, and in the event of the death of either of the Parties to this Agreement while it is in force and effect, the estate of said deceased Party shall be responsible for the performance of the obligations and conditions of this Agreement."

---

### 16. AMENDMENT OR MODIFICATION.
"The Parties agree that no modification or waiver of any of the terms of this Agreement shall be valid unless in writing and executed with the same formalities as this Agreement or except by a court of competent jurisdiction pursuant to the laws of Florida and the terms of this Agreement. The provisions of this Agreement which are designated as non-modifiable are intended to remain so, notwithstanding this provision. The failure of either Party to insist in one or more instances upon the strict performance of any of the terms or provisions of this Agreement on the part of the other Party to be performed shall not be construed as a waiver or relinquishment for the future of any such term or provision, and the same shall continue in full force and effect."

---

### 17. ENTIRE AGREEMENT.
"This Agreement contains the entire agreement of the Parties. There are no representations, promises or undertakings other than those expressly set forth herein."

---

### 18. INTERPRETATION.
"The article headings of this Agreement are for the convenience of reference only and shall not affect the interpretation of any provision hereof."

---

### 19. LAW.
"This Agreement shall be interpreted and governed by the laws of the State of Florida."

---

### 20. INDEMNIFY AND HOLD HARMLESS.
Full indemnification provision (see `references/boilerplate.md` §20): includes all demands, claims, damages; taxable and non-taxable costs; professional fees and attorney's fees from commencement of any litigation until appeals are final; applies to declaration of rights, reformation, damages for default, misrepresentation, indemnification, contribution, subrogation, or other legal or equitable remedy.

---

### 21. SEVERABILITY.
"If any particular provision, or part thereof, of this Agreement is deemed or declared to be invalid, void or unenforceable by any court of competent jurisdiction, the other provisions, or parts thereof, of this Agreement shall continue in full force and effect and shall be valid and enforceable according to their terms. In such event, the Parties agree to negotiate in good faith a replacement provision that most closely reflects the original intent of the invalid provision."

> **Replaced 7/2026.** The prior second sentence ("the Court which declares any
> provision void… shall make such awards in its discretion is fair and equitable
> to compensate either or both Parties…") was both ungrammatical and an attempt to
> direct a court's discretion. Use the good-faith renegotiation sentence above.
> Do not restore the old language.

---

### 22. EFFECTIVE DATE OF AGREEMENT.
"The effective date of this Agreement shall be the last date on which either Party signs it."

---

### 23. PERFORMANCE.
"From and after the date of the execution of this Agreement, neither Party will take any action that would prohibit, inhibit, or diminish in any way, the ability of any Party nor any entity related to that Party to perform the obligations of this Agreement. Further, it is the intent of this Agreement that neither Party will take any action that will cause any damage to the other or to any entity related to that Party."

---

### 24. UNDISCLOSED ASSETS.
"Should either Party discover assets in the future that were not discovered or disclosed by the other Party in [his/her] financial affidavit and before the execution of this Agreement, among other remedies afforded by Florida law, the aggrieved Party shall be entitled to seek an order from a court of competent jurisdiction that such undisclosed assets be divided between the Parties in equal shares, and the non-disclosing Party shall be responsible for the aggrieved Party's reasonable attorney's fees and costs incurred as a result of such non-disclosure."

> **Rewritten 7/2026** per Rule 0.3. Three changes: (1) "shall be entitled to seek
> an order from a court of competent jurisdiction" replaces the self-executing
> "shall obtain that such assets be divided"; (2) "aggrieved Party" /
> "non-disclosing Party" replaces "non-faulty" / "faulty"; (3) fees are qualified
> as "reasonable." Write the clause once, cleanly — a delivered draft contained
> both the old and new text spliced together mid-sentence.

---

### 25. BANKRUPTCY.
"The bankruptcy or the filing of any petition in bankruptcy under any of the provisions of the existing or any future bankruptcy law by either party shall not operate to discharge either party from satisfying any debt or obligation set forth in this Agreement. Both parties represent and warrant that they are not planning to file for bankruptcy and that they will satisfy the debts and obligations respectively assigned to each of them herein on a timely basis. The Petitioner hereby indemnifies, saves, and holds the Respondent harmless for any debts and obligations that the Petitioner is responsible for satisfying herein; and the Respondent hereby indemnifies, saves, and holds the Petitioner harmless for any debts and obligations assigned to the Respondent herein."

---

### 26. ATTORNEY'S FEES.
Two-part provision:

**Part 1 — Own Fees:**
"Each of the parties hereby acknowledges and agrees that she or he shall be responsible for the payment of her or his own attorney's fees with regard to the preparation of this Marital Settlement Agreement and any proceeding which may be instituted resulting in the dissolution of marriage of the parties."

**Part 2 — Prevailing Party:** (include unless attorney directs otherwise)
"To the extent either party seeks to compel enforcement (including contempt) and/or compliance with this Marital Settlement Agreement or to the extent a dispute arises concerning this Marital Settlement Agreement, including but not limited to the validity and/or interpretation hereof, the prevailing party shall be entitled to their reasonable attorney's fees and costs in any such proceedings, including appellate court proceedings, and further including attorney's fees, costs and suit monies incurred when litigating both entitlement and amount of such prevailing party fees."

---

### 27. TAX ADVICE.
"Each party acknowledges that he or she has had the opportunity to retain his or her own Certified Public Accountant, tax attorney, or tax advisor, with reference to the tax implications of this Agreement. Each party acknowledges that he or she has not relied upon any tax advice that may or may not have been given by his or her respective attorneys, if any, who have represented him or her in the negotiations of this Agreement, and the dissolution of marriage proceedings. Each party acknowledges that he or she has been advised to seek independent tax advice by retaining a Certified Public Accountant, tax attorney, or tax advisor with reference to the tax implications involved in this Agreement. The signatures of each party to this Agreement acknowledge that each has read this particular paragraph and he or she has had the opportunity to seek independent tax advice."

---

### 28. MEDIATOR. *(include for ALL mediated MSAs — four required parts)*

**Part 1 — No legal or tax advice:**
"Each Party hereby acknowledges that the mediator, [MEDIATOR NAME], [CREDENTIALS], of [FIRM], did not provide either side with legal advice nor tax advice."

**Part 2 — Actual mediation posture (state the true one — do not default):**
- *Both represented:* "Mediation was conducted with each Party represented by and appearing with independent counsel of [his/her] own choosing. Each Party had the opportunity to hire, and did hire, [his/her] own attorney."
- *Both pro se:* "Mediation was conducted without attorneys, with each Party appearing pro se. Each Party had the opportunity to hire [his/her] own attorney and elected not to do so."
- *Mixed:* state which party appeared with counsel and which appeared pro se. Flag for attorney.

**Part 3 — Mediation confidentiality and no-testimony covenant:**
"Each Party further acknowledges that mediation communications are confidential and privileged pursuant to Section 44.405, Florida Statutes, and that neither Party shall seek to compel the mediator to testify or produce documents in any proceeding related to this matter."

**Part 4 — Mediator hold harmless and indemnification:**
"Each Party hereby releases, holds harmless, and agrees to indemnify the mediator, [MEDIATOR NAME], and [FIRM], from and against any and all claims, demands, damages, costs, expenses, and attorney's fees arising out of or related to the mediation or this Agreement."

> **Parts 3 and 4 added 7/2026.** The prior version had only Parts 1–2, leaving the
> neutral exposed to being subpoenaed as a fact witness and to claims arising from
> the mediation. Both parts are mandatory on every Feinstein & Mendez, PA-mediated MSA. Every
> statutory citation carries the standard attorney-verification warning — the
> attorney confirms § 44.405 text before execution. Caselaw and statutory
> authority come from firm reference files only, never AI memory or web search.

---

### 29. NAME RESTORATION. *(include ONLY if a party is restoring a former name)*
"The [Petitioner/Respondent] shall restore [his/her] name. The [Petitioner/Respondent], [CURRENT LEGAL NAME], shall restore [his/her] name to: [RESTORED NAME]."

> Drafted by role, not by gender. Either party may restore a former name. Do not
> assume the Respondent, and do not assume a wife.

---

### SIGNATURE BLOCK

```
      IN WITNESS WHEREOF, the Parties have hereunto set their hands and seals
as of this day and year first above written.

Signed, sealed and delivered in the presence of:


___________________________________       ___________________________________
[PETITIONER FULL NAME],                   [RESPONDENT FULL NAME],
PETITIONER                                RESPONDENT
```

---

### NOTARY ACKNOWLEDGMENT — PETITIONER

```
STATE OF FLORIDA
COUNTY OF [COUNTY]

      The foregoing instrument was acknowledged before me this _____ day of
______________, 20___, by [PETITIONER FULL NAME], Petitioner, who is
personally known to me or who has produced a driver's license as identification.

      WITNESS my hand and official seal this _____ day of ______________, 20___.


                                     ___________________________________
                                     Notary Public – State of Florida

My Commission Expires: ____________________  Commission # ______________
```

---

### NOTARY ACKNOWLEDGMENT — RESPONDENT

```
STATE OF FLORIDA
COUNTY OF [COUNTY]

      The foregoing instrument was acknowledged before me this _____ day of
______________, 20___, by [RESPONDENT FULL NAME], Respondent, who is
personally known to me or who has produced a driver's license as identification.

      WITNESS my hand and official seal this _____ day of ______________, 20___.


                                     ___________________________________
                                     Notary Public – State of Florida

My Commission Expires: ____________________  Commission # ______________
```

---

## STEP 4 — Generate the Word (.docx) File

**Read `/mnt/skills/public/docx/SKILL.md` BEFORE writing any code.**

Then read `references/formatting.md` for the complete Feinstein & Mendez, PA MSA style spec.

### Critical docx-js Settings for MSA
```javascript
// Font: Times New Roman 12pt (override docx-js default of Calibri/Arial)
styles: {
  default: {
    document: { run: { font: "Times New Roman", size: 24 } } // 24 half-points = 12pt
  }
}

// Page: US Letter, 1-inch margins
properties: {
  page: {
    size: { width: 12240, height: 15840 },      // US Letter
    margin: { top: 1440, right: 1440, bottom: 1440, left: 1440 } // 1 inch
  }
}

// Double spacing for all body paragraphs
spacing: { line: 480, lineRule: "auto" }         // 480 twips = double space

// Full justification (both sides)
alignment: AlignmentType.BOTH

// Footer: "Page X of Y" centered
footer: new Footer({
  children: [
    new Paragraph({
      alignment: AlignmentType.CENTER,
      children: [
        new TextRun("Page "),
        new TextRun({ children: [PageNumber.CURRENT] }),
        new TextRun(" of "),
        new TextRun({ children: [PageNumber.TOTAL_PAGES] }),
      ]
    })
  ]
})
```

### Heading Hierarchy in the MSA
| Level | Example | Style |
|-------|---------|-------|
| Document title | MARITAL SETTLEMENT AGREEMENT | Centered, bold, underlined, ALL CAPS |
| WITNESSETH | W I T N E S S E T H: | Centered, underlined, letter-spaced |
| Section (1. 2. 3.) | `1.      RECITALS.` | Left-aligned, bold, underlined, tab between number and title |
| Subsection (4.1) | `      4.1    Parenting Plan:` | Indented 0.5", underlined only |
| Sub-subsection (A. B.) | `            A.      NOTIFICATION...` | Indented 1", ALL CAPS, underlined |
| Numbered sub-items (1. 2.) | `                  1.    When the children...` | Indented 1.5" |
| Lettered sub-items (a. b.) | `                        a.    Fight within...` | Indented 2" |

### Equitable Distribution Summary Chart — table build spec
The chart is a real Word table on its own page after the notary blocks.

```javascript
// Page break, then exhibit heading
new Paragraph({ children: [new PageBreak()] }),
new Paragraph({ alignment: AlignmentType.CENTER, children: [
  new TextRun({ text: 'EXHIBIT "A"', bold: true, underline: {} })]}),
new Paragraph({ alignment: AlignmentType.CENTER, children: [
  new TextRun({ text: "EQUITABLE DISTRIBUTION SUMMARY CHART", bold: true })]}),

// 3-column table, US Letter with 1" margins => 9360 DXA usable
new Table({
  columnWidths: [3120, 3120, 3120],          // must sum to table width
  width: { size: 9360, type: WidthType.DXA },
  rows: [ /* header row + one row per category */ ]
})
// Every cell: width: { size: 3120, type: WidthType.DXA }
// Header row shading: { type: ShadingType.CLEAR, fill: "D9D9D9" }  // never SOLID
// Table body may be single-spaced 11pt; the Agreement body stays TNR 12pt double
```
Column headers: `Asset / Liability` · `Petitioner ([Last Name])` · `Respondent
([Last Name])`. Close the exhibit with the control/precedence paragraph from
STEP 3B — it is not optional.

### Output Steps
1. Generate the `.docx` using Node.js + `docx` npm package
2. **Validate the generated file against the settings above** — no validation script ships with
   this skill, so confirm by inspection: default run font is Times New Roman 12pt, page is US
   Letter with 1-inch margins, body paragraphs are double-spaced and fully justified, the footer
   shows a centered "Page X of Y", and — if the Equitable Distribution exhibit is included — its
   three column widths sum to 9360 DXA. Fix any mismatch before continuing.
3. Copy to: `/mnt/user-data/outputs/[LastName]_MSA_DRAFT.docx`
4. **Run STEP 5 QC before delivering to user**
5. Use `present_files` tool to deliver to user
6. End response with: **"This draft requires attorney review before execution."**

### FILE SAVE INSTRUCTIONS
- Filename: `[LastName]_MSA_DRAFT_v[N].docx` — increment the version, never overwrite
- Destination: {{DMS}} → matter folder `Last, First - [Matter Type] (####-####)`
  → **`Notes/`** (GAL matters: `GAL Notes/`). Mediation matters use the Mediation
  template folder.
- {{ROLE_APPROVER}} downloads the output and saves it to {{DMS}} manually.
- Assigned to: drafted by {{ROLE_DRAFTER}} or {{ROLE_REVIEWER}} → reviewed by {{ROLE_APPROVER}} → approved by {{ROLE_APPROVER}}.
  When Feinstein & Mendez, PA is the neutral mediator, {{ROLE_APPROVER}} reviews and releases directly.
- Time is tracked in {{PM_SYSTEM}}, including Claude-assisted drafting time.

---

## STEP 5 — Quality Control (Run BEFORE Delivering the File)

Before presenting the .docx to the user, run every check below. Fix any failure
before delivery. Document all findings in the QC Report that accompanies the file.

### A. Section Completeness Check
Go through the master section list and confirm every required section is present:

| # | Section | Present? | Notes |
|---|---------|----------|-------|
| — | Preamble (parties, addresses, date) | | |
| — | WITNESSETH / WHEREAS clauses | | |
| — | NOW, THEREFORE paragraph | | |
| 1 | RECITALS | | |
| 2 | SEPARATION | | |
| 3 | ALIMONY (award OR waiver — not blank) | | |
| 4 | PARENTING PLAN AND CHILD SUPPORT | *(if children)* | |
| 4.1 | Parenting Plan / Exhibit A reference | *(if children)* | |
| 4.A–D | Notification / Encouragement / Communication / Failure | *(if children)* | |
| 4.E | Miscellaneous — all 11 numbered provisions | *(if children)* | |
| 4.2 | Computation of Child Support / Exhibit B | *(if children)* | |
| 4.3 | Child Support amount and payor | *(if children)* | |
| 4.4 | Income (both parties stated) | *(if children)* | |
| 4.5 | Hospitalization and Medical Insurance | *(if children)* | |
| 4.6 | Life Insurance | *(if applicable)* | |
| 4.7 | Dependency Exemption | *(if children)* | |
| 5 | PROPERTY SETTLEMENT | | |
| 5.1 | Retirement Accounts | | |
| 5.2 | Financial Accounts | | |
| 5.3 | Real Property (each property addressed) | | |
| 5.4 | Automobiles (each vehicle addressed) | | |
| 5.5 | Miscellaneous and Personal Property | | |
| 5.6 | Life Insurance — cash value / beneficiary waiver | *(if any policy)* | |
| 6 | MEDICAL AND DENTAL INSURANCE | | |
| 7 | OUTSTANDING INDEBTEDNESS (7.1–7.3) | | |
| 8 | GENERAL AND MUTUAL RELEASE | | |
| 9 | REPRESENTATIONS | | |
| 10 | PETITIONER'S WARRANTIES | | |
| 11 | RESPONDENT'S WARRANTIES | | |
| 12 | EXECUTION OF SUBSEQUENT DOCUMENTS (12.1–12.4) | | |
| 13 | RECONCILIATION | | |
| 14 | BINDING NATURE | | |
| 15 | PARTIES BOUND | | |
| 16 | AMENDMENT OR MODIFICATION | | |
| 17 | ENTIRE AGREEMENT | | |
| 18 | INTERPRETATION | | |
| 19 | LAW | | |
| 20 | INDEMNIFY AND HOLD HARMLESS | | |
| 21 | SEVERABILITY | | |
| 22 | EFFECTIVE DATE OF AGREEMENT | | |
| 23 | PERFORMANCE | | |
| 24 | UNDISCLOSED ASSETS | | |
| 25 | BANKRUPTCY | | |
| 26 | ATTORNEY'S FEES (both parts) | | |
| 27 | TAX ADVICE | | |
| 28 | MEDIATOR — all four parts (advice / posture / § 44.405 / hold harmless) | *(if mediated)* | |
| 29 | NAME RESTORATION | *(if applicable)* | |
| — | IN WITNESS WHEREOF + signature lines | | |
| — | Notary block — PETITIONER | | |
| — | Notary block — RESPONDENT | | |
| — | Exhibit — Equitable Distribution Summary Chart + control clause | *(if property distributed)* | |

**Fail condition:** Any required section is missing → add it before delivery.

---

### B. Internal Consistency Check
Verify the following match throughout the entire document:

- [ ] **Party names** — Petitioner's and Respondent's full names spelled identically every time they appear
- [ ] **Role terminology** — zero instances of "Husband," "Wife," or "his or her" anywhere in the document (Mother/Father permitted only in child-support and parenting provisions)
- [ ] **Pronouns** — match confirmed pronouns for each party; both parties may share the same pronoun
- [ ] **Children's initials** — same initials used consistently; no full names in body text
- [ ] **Exhibit references** — every reference to Exhibit "A" and Exhibit "B" uses bold + underline; the same letter is used every time for the same exhibit
- [ ] **Dollar amounts** — all dollar figures match intake data; written-out amounts match numerals (e.g., "Five Hundred Dollars ($500.00)")
- [ ] **Income figures** — §4.4 income amounts match any CS guidelines computation
- [ ] **Child support amount** — §4.3 amount matches the Exhibit "B" computation
- [ ] **Real property addresses** — same address spelled consistently in §5.3 and anywhere else referenced
- [ ] **Vehicle descriptions** — same year/make/model in §5.4 and anywhere else referenced
- [ ] **Date of marriage** — same date in Preamble and in WHEREAS §1
- [ ] **County** — same county in both notary blocks; matches case county if captioned
- [ ] **Mediator name** — same name and credentials in WHEREAS mediation clause and in §28
- [ ] **ED chart tie-out** — every dollar figure, account, vehicle, and debt in the
      Equitable Distribution Summary Chart appears in the body with the identical
      figure; nothing appears in the chart that is absent from the body
- [ ] **Exhibit letters** — assigned per STEP 3B in order of first reference; no
      hard-coded letter; the same letter used for the same exhibit everywhere
- [ ] **No splice artifacts** — no doubled "WHEREAS, WHEREAS," no doubled "; and,",
      no sentence containing both an old and a revised phrasing (search for repeated
      openers and for "Florida law, Should")
- [ ] **Name restoration** — §29 names the correct party by role, current legal name, and restored name

**Fail condition:** Any inconsistency → correct before delivery.

---

### C. Formatting Check
Visually verify the generated .docx matches Feinstein & Mendez, PA standards:

- [ ] Font is Times New Roman 12pt throughout (not Arial, Calibri, or mixed)
- [ ] Body text is double-spaced
- [ ] Body text is fully justified (both sides)
- [ ] First line of each body paragraph is indented ~0.5 inch
- [ ] Every page has "Page X of Y" centered in the footer
- [ ] Document title is centered, bold, underlined, ALL CAPS
- [ ] WITNESSETH is centered, underlined, letter-spaced
- [ ] Section headings (1. 2. 3.) are bold, underlined, left-aligned with tab
- [ ] Subsection headings (4.1, 5.1 etc.) are underlined only (not bold)
- [ ] Sub-subsection headings (A. B. C.) are underlined, ALL CAPS
- [ ] WHEREAS is bold wherever it appears
- [ ] IN WITNESS WHEREOF is bold
- [ ] Exhibit references are bold AND underlined
- [ ] Vehicle names are underlined in §5.4
- [ ] Signature blocks have correct name/role labels below each line
- [ ] Both notary blocks are present and correctly formatted
- [ ] No visible table borders in signature area
- [ ] Paper size is US Letter, margins are 1 inch on all sides

**Fail condition:** Any formatting deviation → fix before delivery.

---

### D. Legal Completeness Check
Flag the following for attorney attention if present:

- [ ] **Alimony blank** — §3 has neither award language nor waiver → STOP, get direction
- [ ] **QDRO needed** — any retirement account being divided requires a separate QDRO order → flag in Attorney Review Notes
- [ ] **Deviation from CS guidelines** — §4.3 deviates from Exhibit "B" computation → confirm deviation language and justification are stated in the MSA
- [ ] **Real property deed** — §5.3 or §12.1 references deed transfer → note doc stamp tax and timeline
- [ ] **Income withholding** — if child support or alimony is ordered, confirm whether an Income Withholding Order is also being prepared
- [ ] **Passport/travel restriction** — if either party has international travel concerns re: children, confirm whether §4 or Parenting Plan addresses it
- [ ] **Undisclosed assets clause (§24)** — confirm it is present; if attorney directed removal, document reason
- [ ] **Mediator appeared pro se vs. with counsel** — §28 must accurately reflect the mediation configuration
- [ ] **Deadline audit (Rule 0.2)** — search the document for every "shall" that
      creates an obligation. Each one must have a time-certain deadline anchored to
      the Effective Date or entry of the Final Judgment. **Fail condition:** any
      bare obligation with no deadline.
- [ ] **No impossible deadlines** — nothing requiring third-party cooperation
      (bank, card issuer, plan administrator, county recorder) is due "on or before
      the Effective Date"
- [ ] **Self-executing remedy audit (Rule 0.3)** — no provision purports to award
      relief, divide property, or direct a court's discretion without framing it as
      an entitlement to seek an order; all fee entitlements say "reasonable"
- [ ] **QDRO vs. RBCO** — the correct instrument is named for each plan type (TSP →
      RBCO under 5 C.F.R. Part 1653; private plan → QDRO; FERS/FSPS pension → OPM
      order), and both deadlines (60 days to court, promptly to administrator) are stated
- [ ] **Mutual pension waiver** — if each party has a pension neither is claiming, it is expressly waived, not left to the general release
- [ ] **Incorporated but not merged** — §14 contains the survival sentence, and it does not contradict the proposed Final Judgment
- [ ] **Life insurance** — addressed as a marital asset (§5.6) and, if children exist, checked against any §4.6 support-security requirement
- [ ] **Mediator Neutrality Package (STEP 3A)** — if Feinstein & Mendez, PA was the neutral: all four
      elements present, return-to-mediation clause omitted, and the attorney
      verification flag included in the delivery response
- [ ] **Statutory citations** — every statute or C.F.R. cite carries the attorney
      verification warning; citations sourced from firm reference files only, never
      AI memory and never web search
- [ ] **Equitable distribution chart** — attached, correctly lettered, every figure
      traces to the body, and the control/precedence clause is the closing line

---

### E. Placeholder Audit
Search the entire document for any remaining `[BRACKET]` placeholders:

- [ ] Run a find for `[` in the document — every remaining bracket must be listed in MISSING FACTS
- [ ] Confirm no placeholder was accidentally left inside a boilerplate provision
- [ ] Confirm all blanks in signature/notary blocks are intentional (for handwriting at execution)

---

### QC REPORT (attach to delivery)

After completing all checks, include the following in your response:

```
QC REPORT — [CASE NAME] MSA DRAFT
Date: [DATE]
Prepared by: [STAFF NAME / AI]

SECTION COMPLETENESS: PASS / FAIL (list any missing sections)
INTERNAL CONSISTENCY: PASS / FAIL (list any discrepancies found)
FORMATTING: PASS / FAIL (list any deviations corrected)
LEGAL FLAGS: (list any items flagged for attorney attention)
OPEN PLACEHOLDERS: (list every [BRACKET] still in the document)

CLEARED FOR ATTORNEY REVIEW: YES / NO
```

**The MSA draft is not delivered until all PASS/FAIL items have been resolved
or documented. If any section is missing or any consistency check fails, fix
the document first, then re-run QC before presenting the file.**

---

## STEP 6 — Required Response After Delivery

### EXHIBITS NEEDED
Letter per STEP 3B — order of first reference in the body.
- [ ] **Agreed Parenting Plan** *(if children)* — draft separately or attach if already executed
- [ ] **Child Support Guidelines Worksheet** *(if children)* — attach the § 61.30 computation
- [ ] **Equitable Distribution Summary Chart** — Feinstein & Mendez, PA default on every MSA that
      distributes property; must carry the control/precedence closing clause
- [ ] *(List any other referenced exhibits)*

### MISSING FACTS / OPEN ITEMS
List every `[BRACKETED PLACEHOLDER]` in the draft that still needs to be filled in.

### ATTORNEY REVIEW NOTES
- Any deviations from standard Feinstein & Mendez, PA boilerplate
- Any sections omitted with reason documented
- QDRO flag if any retirement account is being divided
- Real property: flag deed transfer tax implications
- Flag any deviation from Chapter 61 child support guidelines (§4.3)
- Flag if parties appeared with counsel vs. pro se at mediation
- If Feinstein & Mendez, PA was the neutral: state that the Mediator Neutrality Package is included
  and that the return-to-mediation clause was omitted for that reason
- List every deadline created by the Agreement in a calendar table (obligation /
  responsible party / trigger event / due date) so {{ROLE_REVIEWER}} can docket them
- Flag every statutory and C.F.R. citation for attorney verification

---

## Non-Negotiable Rules

1. ALL 29 sections must appear unless the topic genuinely does not exist
2. No invented facts — use [BRACKETS] for anything not confirmed by file or staff
3. Children's names in document body: **initials only** (e.g., H.N.K., not full name)
4. Section 3 ALIMONY is mandatory — either award language or full mutual waiver
5. Each piece of real property gets its own numbered sub-provision under 5.3
6. Each vehicle gets its own paragraph under 5.4
7. Both notary acknowledgment blocks required — one per party — never omit
8. Mediator acknowledgment (§28) required for every mediated MSA
9. **Output is always a .docx file** — inline text alone is never acceptable
10. Prevailing party language (§26 Part 2) is included by default
11. **Petitioner/Respondent only** — never Husband/Wife; never assume gender or
    pronouns; Mother/Father only inside child-support and parenting provisions
12. **Every obligation carries a time-certain deadline** anchored to the Effective
    Date or entry of the Final Judgment (Rule 0.2)
13. **No self-executing remedies** — relief is always framed as an entitlement to
    seek an order from a court of competent jurisdiction (Rule 0.3)
14. **Equitable distribution summary chart** attached as an exhibit on every MSA
    that distributes property, with the control/precedence clause
15. **Mediator Neutrality Package** (all four elements) on every Feinstein & Mendez, PA-mediated MSA,
    and the return-to-mediation clause omitted when Feinstein & Mendez, PA was the neutral
16. **§14 incorporated-but-not-merged** survival sentence is never omitted
17. Every statutory citation carries the attorney verification warning; authority
    comes from firm reference files only — never AI memory, never web search
18. **Real case material is never carried between matters.** Party names, case
    numbers, balances, account numbers, and institution names from one matter never
    appear in a template, a skill file, or another matter's draft.

---

## Reference Files

| File | Contents |
|------|----------|
| `references/boilerplate.md` | Verbatim standard language for all sections |
| `references/formatting.md` | Complete Feinstein & Mendez, PA Word formatting spec |

---

## AMBIENT STANDARD — Feinstein & Mendez, PA PLEADING FORMAT & DRAFT-STATE RULES

`lal-pleading-standard` governs every court-bound document this skill produces.
Two rules, from the first keystroke:

1. **Format correctly immediately** — portrait, Times New Roman 12 black, single
   spacing 0pt before/after, left aligned, 1" margins, Feinstein & Mendez, PA caption (court centered ·
   case/division right · parties left · rule line ending in `/` · title centered
   bold ALL CAPS), numbering I. → 1. → a. → i. continuous. No bullets, no dividers.
   There is no rough-format stage that gets fixed later.
2. **Drafts show their work, highlighted** — attorney notes 🟨, outstanding facts 🟨,
   alternative provisions 🟩 drafted in full. When unclear what the pleading should
   contain, present highlighted ALTERNATIVES — never assume and draft one version
   as if decided. Never strip flags at draft stage; only `lal-finalize-draft`
   strips, after the attorney resolves them.

---

## MANDATORY HANDOFF — PRE-FILING QC GATE

Any document this skill produces that will be **filed with a court, served on a
party, or sent outside the firm** goes to `lal-prefiling-qc` before it reaches
an attorney. This handoff is not optional and is not skippable for urgency.

```
THIS SKILL  →  lal-prefiling-qc  →  ATTORNEY SIGN-OFF  →  FILE / SERVE / SEND
```

- Do not present a draft as "ready for {{ROLE_APPROVER}}" or "ready to file" until the gate has run.
- A **BLOCKED** verdict returns the draft here for correction. Fix and re-run the gate.
- A **CONDITIONAL** verdict goes to the attorney with the findings attached.
- Never resolve a flagged item by deleting the language to make the gate pass.

- After the gate clears, hand the document to `lal-finalize-draft` to produce the
  filing-ready Word file and PDF. That skill enforces portrait, Times New Roman 12,
  all black, single spacing, the Feinstein & Mendez, PA caption layout, strips every internal artifact,
  and checks `lal-judicial-procedures` for the assigned judge before output.

**Approval behavior:** if the person in the session is an Feinstein & Mendez, PA attorney ({{ROLE_APPROVER}} or
{{ROLE_APPROVER}}), her instruction IS the sign-off — do not ask her to approve what she just
directed. If staff, every attorney-gated item routes to {{ROLE_APPROVER}} and waits.

---

## OUTPUT DELIVERY — FIRM STANDARD (v2, {{DMS}}-native)

All output from this skill is delivered through `lal-file-connector` (Operation 4).

**Destination:** `Notes/` in the {{DMS}} matter folder
`Last, First - [Matter Type] (####-####)`. There is no `CLAUDE OUTPUT` folder and
no {{DMS}} path. (`GAL Notes/` on GAL matters.)

**Filename:** `MM.DD.YY - LastName - DocTitle - v1.ext` — versioned, never overwritten.

**Delivery depends on where this skill is running:**

- **Claude.ai (chat / Projects)** — Claude cannot write to {{DMS}}. Present the file
  as a **download** and print the destination block: matter folder → `Notes/`, filename,
  version. Never write "saved to {{DMS}}."
- **Cowork (desktop)** — write to the folder designated for the session (ask once at
  first delivery, reuse thereafter), confirm the **actual path written**, and state
  where the file belongs in {{DMS}}.

Nothing is filed or sent without attorney sign-off. Time is tracked in {{PM_SYSTEM}},
including Claude-assisted work.

