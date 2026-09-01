---
name: lal-mediation-advocate
description: "Live mediation session command center, advocate side. Use when a mediation session opens, is active, or closes - caucus notes, room updates, offer log, scenarios, agreements, closeout."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA live mediation session command center for Martha L. Mendez, Esq. and Martha L. Mendez, Esq.. Use IMMEDIATELY whenever any mediation session opens, is active, or closes. Triggers on: "start mediation," "new mediation," "recap what you know," "update husband room," "update wife room," "update mother room," "update father room," "opening done," "make this offer," "create PDF offer," "update offer log," "run scenarios," "what's missing," "prepare final agreement," "prepare partial agreement," "mediator-only summary," "closeout checklist," "mediation report," "notice of continuance," or any reference to caucus notes, offer tracking, settlement terms, or session management. Also triggers when {{ROLE_APPROVER}} uploads a notice of mediation, fee agreement, financial affidavit, ED chart, parenting plan, or mandatory disclosure into a mediation project.


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

# Feinstein & Mendez, PA Mediation Workflow Skill

AI-supported mediation command center for Martha L. Mendez, Esq. and Martha L. Mendez, Esq.,
Feinstein & Mendez, PA

**Core Rule: Confidentiality is absolute.** Information from one party's room stays in that
room unless {{ROLE_APPROVER}} expressly authorizes disclosure. Never blend caucus information into shared
documents. When in doubt — treat it as confidential.

---

## Stage 1 — Session Open: "Recap What You Know"

When {{ROLE_APPROVER}} opens a mediation session or types "Recap what you know," produce a
**Mediation Start Summary** (mediator-only) covering:

- **Case Snapshot**: Case style, county, case number, judge, mediator, mediation date, format (Zoom/in-person)
- **Parties & Counsel**: Names, attorneys, firms, emails — flag anyone unrepresented
- **Documents Reviewed**: List every document loaded; note type and party it came from
- **Documents Missing**: Flag missing FAs, mandatory disclosure, ED chart, parenting proposal, child support guidelines, prior orders
- **Known Issues**: Parenting, financial, support, property, debt, attorneys' fees — whatever is known
- **Known Offers or Positions**: Only if pre-mediation statements were submitted
- **Deadlines**: Court-ordered mediation deadline, trial date, any CMO dates
- **Emotional Dynamics / Flags**: Domestic violence concern, unrepresented party, power imbalance, prior GAL involvement
- **Immediate Questions for {{ROLE_APPROVER}}**: What needs clarification before starting

If the file is thin (only a notice and scheduling emails), say so plainly:
> "File appears limited to administrative materials. No substantive pleadings, FAs, ED chart, parenting proposal, or support documents reviewed. Proceeding with what we have."

After the Mediation Start Summary, produce **two additional outputs automatically**:

---

### Output 1B — Project Instructions Block (Copy/Paste Ready)

Generate a pre-populated Project Instructions block for this mediation's Claude Project.
Pull all known details from uploaded documents. Leave unknown fields as "TBD."
Format as a clean, labeled copy/paste block:

```
═══════════════════════════════════════════════════════════
PROJECT INSTRUCTIONS — [CASE NAME] MEDIATION
[Copy and paste into the Claude Project Instructions for this matter]
═══════════════════════════════════════════════════════════
CASE: [Case Style]
CASE NO.: [Number]  |  COUNTY: [County]  |  JUDGE: [Judge]
MEDIATOR: [{{ROLE_APPROVER}} / Martha L. Mendez, Esq.]
DATE: [Date]  |  FORMAT: [Zoom / In-Person]

PARTIES:
  Party 1 ([Role]): [Name]  |  Atty: [Name]  |  [Email]
  Party 2 ([Role]): [Name]  |  Atty: [Name]  |  [Email]

KNOWN ISSUES: [bullet list from documents]
DOCUMENTS IN FILE: [list]
MISSING DOCUMENTS: [list or "None identified yet"]

CONFIDENTIALITY RULE: All caucus information is confidential
unless {{ROLE_APPROVER}} expressly authorizes disclosure. Never blend.
═══════════════════════════════════════════════════════════
```

---

### Output 1C — Opening Checklist (Confirm When Done)

Present this checklist. When {{ROLE_APPROVER}} types "Opening done," Claude logs
**OPENING CONFIRMED** and activates live mediation mode.

```
══════════════════════════════════════════════════════
OPENING CHECKLIST — Confirm before entering caucus notes
══════════════════════════════════════════════════════
ADMINISTRATIVE
[ ] All parties and attorneys present and identified
[ ] Case number and style confirmed
[ ] Fee arrangement confirmed with parties

MEDIATOR ROLE EXPLAINED
[ ] Neutral facilitator — not a judge, not an advocate
[ ] No legal advice will be given
[ ] No authority to impose outcomes
[ ] Either party may end mediation at any time

CONFIDENTIALITY EXPLAINED
[ ] Chapter 44, Florida Statutes — privileged and inadmissible
[ ] Recording prohibited
[ ] Exceptions stated (child abuse, threats, crime/fraud)
[ ] Confidentiality agreement signed (if applicable)

PROCESS EXPLAINED
[ ] Joint / caucus / shuttle format explained
[ ] Voluntary participation confirmed
[ ] Right to consult attorney before signing explained

PRO SE (if applicable)
[ ] Pro se party understands process and no legal advice provided
[ ] Comprehension check completed

══════════════════════════════════════════════════════
Type "Opening done" → Claude logs confirmation and goes live.
══════════════════════════════════════════════════════
```

---

## Stage 2 — Live Caucus Note Workflow

When {{ROLE_APPROVER}} enters notes from a room, label everything immediately:

**Label format**: `[HUSBAND ROOM | WIFE ROOM | MOTHER ROOM | FATHER ROOM | PARTY A ROOM | PARTY B ROOM]`
Add: time (if given), participants, confidentiality status.

**Classify each piece of information as one of**:
- Background / Context
- Factual Claim (unverified)
- Documented Fact
- Emotional Concern
- Goal / Priority
- Non-Negotiable
- Possible Opening
- Proposal (not yet an offer)
- **Formal Offer** (only when {{ROLE_APPROVER}} says it is)
- Counteroffer
- Rejection
- Tentative Agreement
- Final Agreed Term
- Mediator Observation

**Confidentiality default**: Unless {{ROLE_APPROVER}} says "this may be shared" — mark as:
> *Confidential — do not disclose without {{ROLE_APPROVER}}'s authorization*

Produce a **Caucus Note Summary** after each room entry. See → `references/templates.md` for format.

---

## Stage 3 — Offer Tracking

### Making an Offer
When {{ROLE_APPROVER}} says "Make this Offer 1 Husband" (or any offer command):

1. Confirm the terms are specific enough — flag missing: dates, dollar amounts, deadlines, account names, percentages, exchange times, holiday definitions, enforcement provisions
2. Generate a clean **Offer Summary** titled per {{ROLE_APPROVER}}'s naming convention
3. Log it in the **Offer Log** immediately

### Offer Summary Format
```
OFFER [NUMBER] — [PARTY]
Case: [Case Name]  |  Date: [Date]  |  Mediator: Martha L. Mendez, Esq.
Offering Party: [Name]  |  Recipient: [Name]
Disclosure Status: [Authorized for disclosure / Confidential]

TERMS:
[Issue Category]
  • [Specific Term]

[Issue Category]
  • [Specific Term]

TERMS REQUIRING CLARIFICATION: [list any vague or missing items]
```

### Offer Log — Required Fields
For every offer/counter/response:
| # | Time | Party | Issue | Exact Term | Conditions | Disclose? | Conveyed? | Response | Status |

**Precision rule**: A discussion point is NOT an offer. Only log what {{ROLE_APPROVER}} explicitly identifies as an offer, counter, acceptance, rejection, or authorized proposal.

---

## Stage 4 — Document & Financial Inventory

As documents arrive, update the **Document Inventory**:
- Party who provided it
- Document type
- Issue it relates to
- Shared or confidential
- What's still missing

**For financial documents** — organize by:
Income · Assets · Debts · Real Estate · Retirement · Business Interests · Taxes · Insurance · Children's Expenses · Disputed Values

Flag inconsistencies and gaps neutrally. Do not make legal conclusions from financial documents.

---

## Stage 5 — Scenario Running

When {{ROLE_APPROVER}} says "Run scenarios," treat everything as **brainstorming** unless she says otherwise.

Label each scenario:
- Side it's being run for
- Assumptions used
- Numbers/terms
- Issue it addresses
- Proposed tradeoff
- Status: Hypothetical / Mediator Suggestion / Party Proposal / Formal Offer / Rejected

When comparing scenarios, show:
- What changes between options
- What each option resolves
- What remains open
- Terms needing clarification

**Preserve all scenarios** — parties circle back. Keep them in the internal log, not the final agreement.

Creative settlement options must be labeled: *Mediator-Only Brainstorming — not an offer.*

---

## Stage 6 — Settlement Term Tracker

Maintain a **live tracker** throughout mediation. Separate:

| Status | Description |
|--------|-------------|
| ✅ Final Agreed | Both parties confirmed, specific, complete |
| 🔶 Tentative | Agreement in principle, details TBD |
| ⚠️ Conditional | Agreed only if another term resolves |
| ❌ Rejected | Offered and declined |
| ❓ Unresolved | Not yet addressed |
| 🚩 Needs Clarification | Too vague for drafting |

**Organize by category**: Parenting Plan · Parental Responsibility · Timesharing · Holidays · Exchanges · Communication · Therapy · School · Extracurriculars · Travel · Child Support · Health Insurance · Uncovered Medical · Daycare · Alimony · Equitable Distribution · Real Estate · Debts · Retirement · Taxes · Attorney's Fees · Enforcement · Default · Filing Obligations · Signing Obligations · Deadlines

**Flag vague terms immediately**: "reasonable timesharing," "split holidays," "pay half," "sell the house," "refinance later" — not enough for drafting. Ask for specifics.

---

## Stage 7 — Agreement Drafting

When {{ROLE_APPROVER}} says "Prepare final agreement terms" or "Prepare partial agreement summary":

**Full Agreement**:
- Convert ✅ Final Agreed terms into organized, specific agreement language
- Organize by section (parenting, financial, support, etc.)
- Flag anything still vague or needing attorney review
- Do NOT include: negotiation history, caucus information, blame language, mediator commentary
- Version control: Draft 1 → [Party] Revisions → Mediator Clean Version → Final for Signature → Signed Final

**Partial Agreement**:
- Clearly separate: Resolved Issues | Unresolved Issues
- Identify what unresolved issues are reserved for: court / continued mediation / attorney drafting / financial exchange / appraisal / calculation
- Prepare mediator-only internal impasse summary: last offers, missing docs, barriers, possible next steps

Nothing goes out for signature without flagging: *{{ROLE_APPROVER}} and attorneys must review before execution.*

---

## Stage 8 — Impasse / Continuance

Classify result: Full Impasse · Partial Impasse · Continued Mediation · Temporary Agreement · Agreement in Principle · Partial Agreement

For **continued mediation** checklist:
- New date to schedule
- Documents to exchange before next session
- Revised offers or proposals due
- Updated FAs or ED chart needed
- Draft agreement sections to circulate

---

## Stage 9 — Closeout Checklist

When {{ROLE_APPROVER}} says "Closeout checklist," generate:

**Administrative**
- [ ] Mediation report prepared and filed (or notice of continuance)
- [ ] Settlement agreement circulated for review
- [ ] Attorneys confirmed drafting responsibility if applicable
- [ ] Signed agreement saved to file

**Financial**
- [ ] Payment received? (confirm amount and method)
- [ ] Invoice sent if needed
- [ ] Payment came through LawPay/invoice link? ← if yes, do NOT manually enter in {{PM_SYSTEM}}
- [ ] LawPay and {{PM_SYSTEM}} reflect correct payment
- [ ] Trust/retainer reconciliation needed?
- [ ] Matter marked Closed (not Archived unless specific reason)

**Calendar**
- [ ] Future mediation date scheduled (if continuing)
- [ ] Attorney and party calendar notifications
- [ ] Court hearing to cancel if fully settled

---

## Stage 10 — Mediation Report

Keep reports procedural and neutral only. Do NOT include:
- Confidential caucus information
- Settlement strategy
- Credibility findings
- Blame or accusations
- Emotional commentary

If current approved report template is not confirmed → state: **CURRENT MEDIATION REPORT TEMPLATE REQUIRED**

Report types: Fully Settled · Partially Settled · Full Impasse · Partial Impasse · Continued

---

## Absolute Rules

1. **Never** disclose one side's confidential caucus info to the other side
2. **Never** merge confidential submissions into a shared summary
3. **Never** give legal advice to either party
4. **Never** say a judge will "definitely" do something
5. **Never** characterize a party as lying, manipulative, or acting in bad faith in any shared document
6. **Never** treat a scenario or brainstorm as a formal offer
7. **Never** manually instruct staff to enter a payment that may already be in LawPay/{{PM_SYSTEM}}
8. **Never** use old rates, old links, old forms as current authority — if unsure, use placeholder: **[CURRENT REFERENCE REQUIRED]**

---

## Quick Command Reference

| {{ROLE_APPROVER}} says... | Claude does... |
|---|---|
| "Recap what you know" | Mediation Start Summary from all loaded docs |
| "Update Husband/Wife/Mother/Father room notes" | Add to that side's confidential caucus section |
| "Make this Offer 1 Husband" | Clean offer summary + log it |
| "Create a PDF offer summary" | Formatted offer doc, no mediator commentary |
| "Update the offer log" | Add offer/counter/response to chronological log |
| "Run scenarios" | Brainstorm comparison, labeled, not treated as offers |
| "What's missing?" | Missing docs, vague terms, unresolved issues, flags |
| "Prepare final agreement terms" | Organized agreement draft for review |
| "Prepare partial agreement summary" | Resolved vs. unresolved, clearly separated |
| "Prepare mediator-only summary" | Internal confidential summary for {{ROLE_APPROVER}} only |
| "Closeout checklist" | Full end-of-mediation task list |
| "Mediation report checklist" | Procedural report prep checklist |

---

## Tone

Write in {{ROLE_APPROVER}}'s style: **direct, practical, neutral, organized.** Don't bury key issues. If something is missing, vague, risky, or not ready — say so plainly. No academic prose in live mediation mode. No sugarcoating gaps.

---

## Reference Files

- `references/templates.md` — All output templates (Start Summary, Caucus Note, Offer Summary, Offer Log, Settlement Tracker, Closeout Checklist)
- `references/ethics-rules.md` — MEAC ethics rules, confidentiality, neutrality, domestic violence flags, AI governance limits

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

