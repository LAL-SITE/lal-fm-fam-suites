---
name: lal-cert-of-compliance
description: "Drafts the Certificate of Compliance for Rule 12.285 mandatory disclosure. Use when disclosure has been served and the cert is needed for filing. Attorney reviews and signs before filing."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA Certificate of Compliance drafter for Florida Rule 12.285 mandatory disclosure. Use this skill immediately whenever {{ROLE_DRAFTER}} needs to draft a Certificate of Compliance confirming that mandatory disclosure has been served. Triggers on: "draft the cert of compliance," "certificate of compliance," "cert of compliance," "mandatory disclosure is complete," "we served disclosure — draft the cert," "client disclosure is done," "draft the 12.285 certificate," "we need to file the cert," "disclosure is served — generate the cert," or any request to prepare the Certificate of Compliance for filing after mandatory disclosure has been produced. {{ROLE_DRAFTER}} drafts using the tracker and served documents as reference. Output goes to {{ROLE_APPROVER}} to review and sign before filing. Never filed without attorney approval. Always assign to {{ROLE_DRAFTER}} for drafting — attorney for signing.


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

# Feinstein & Mendez, PA Certificate of Compliance — Rule 12.285
## Staff Lane: {{ROLE_DRAFTER}} drafts | {{ROLE_APPROVER}} signs | Files via {{PM_SYSTEM}}
## Triggers After: Client mandatory disclosure is served and tracker confirms complete

This skill drafts the Certificate of Compliance confirming that the client
has served mandatory automatic disclosure pursuant to Florida Family Law
Rule of Procedure 12.285. {{ROLE_DRAFTER}} runs this skill after the disco tracker
confirms all required items have been served. Output is a court-ready draft
that goes directly to {{ROLE_APPROVER}} for review and signature before filing.

---

## BEFORE DRAFTING — CONFIRM PREREQUISITES

{{ROLE_DRAFTER}} must confirm ALL of the following before this skill runs:

**From the Disco Tracker (Section 2 — Mandatory Disclosure Status):**

| Requirement | Must Confirm |
|---|---|
| Financial Affidavit | Served — correct form (long or short), signed, notarized |
| Tax Returns | Federal and state — past 3 years, all attachments — served |
| W-2s / 1099s / K-1s | All applicable income documents served |
| Pay Stubs | 6 months preceding compliance — all served |
| Bank Statements | All accounts — 12 months (+ canceled checks/registers) — all served |
| Investment / Retirement Statements | Past 12 months (retirement: most recent + 12 months) — all served |
| Real Property Documents | Deeds, mortgage statement, tax bill — all applicable served |
| Life Insurance | Cash value policy statements — all applicable served |
| Vehicle Titles | All applicable served |
| Loan Documents | All outstanding obligations served |
| Credit Card Statements | 24 months — all served |
| Business Documents | If any ownership or interest — returns, financials, agreement served |
| Virtual Currency | 12 months + current holdings list — all applicable served |
| Loan Applications / Credit Reports | Prior 24 months — all served |

If ANY required item is marked Missing or Partial in the tracker,
**do not draft the Certificate**. Flag to {{ROLE_REVIEWER}} — the cert cannot be
filed until disclosure is complete or the item is noted as N/A with
a valid reason.

If an item is genuinely not applicable (N/A), it must be listed in the
cert as not applicable with the reason stated.

---

## STEP 1 — GATHER DRAFTING INFORMATION

Confirm the following from the tracker and case file before drafting:

- Client full legal name (as it appears on pleadings)
- Client's role: Petitioner or Respondent
- Case name (v. format as on pleadings)
- Case number
- Court (County and Circuit)
- Division (if known)
- Date each category of documents was served
- Method of service (Florida e-filing portal / email / hand delivery)
- If served by email — opposing counsel's email address
- Attorney signing the certificate: Martha L. Mendez, Esq. or Martha L. Mendez, Esq.

---

## STEP 2 — DRAFT THE CERTIFICATE

Produce the Certificate of Compliance in Florida family law format.
Use exact case caption format. No deviations from the template below.

```
IN THE CIRCUIT COURT OF THE [CIRCUIT] JUDICIAL CIRCUIT,
IN AND FOR [COUNTY] COUNTY, FLORIDA

IN RE: THE [MARRIAGE / PARENTAGE] OF:

[CLIENT FULL NAME],
        Petitioner,                    Case No.: [CASE NUMBER]

and

[OPPOSING PARTY FULL NAME],
        Respondent.
_________________________________/


        CERTIFICATE OF COMPLIANCE WITH MANDATORY DISCLOSURE

        [CLIENT FULL NAME], [Petitioner / Respondent], by and through

undersigned counsel, hereby certifies that [he / she] has complied with the

mandatory disclosure requirements of Florida Family Law Rule of Procedure

12.285 by serving the following documents upon opposing counsel on the

date(s) indicated below:

        1.      Financial Affidavit ([Long Form / Short Form]), pursuant to

Rule 12.285(b)(1), served on [DATE].

        2.      Federal and state income tax returns for [YEAR], pursuant to

Rule 12.285(b)(2), served on [DATE].

        3.      W-2 forms for [YEAR][, and all 1099 and K-1 forms for [YEAR]],

pursuant to Rule 12.285(b)(2), served on [DATE].

        4.      Pay stubs for the three (3) months preceding service of the

initial pleading, pursuant to Rule 12.285(b)(3), served on [DATE].

        5.      All bank and financial institution statements for all accounts

for the three (3) months preceding service of the initial pleading, pursuant

to Rule 12.285(b)(4), served on [DATE].

        6.      Most recent statements for all investment, brokerage, and

retirement accounts, pursuant to Rule 12.285(b)(5), served on [DATE].

[INCLUDE IF APPLICABLE — REAL PROPERTY:]
        7.      Deeds for all real property, most recent mortgage statement,

and most recent real estate tax bill, pursuant to Rule 12.285(b)(6), served

on [DATE].

[INCLUDE IF APPLICABLE — LIFE INSURANCE:]
        8.      Most recent statements for all life insurance policies with

cash surrender value, pursuant to Rule 12.285(b)(7), served on [DATE].

[INCLUDE IF APPLICABLE — VEHICLES:]
        9.      Titles for all motor vehicles, pursuant to Rule 12.285(b)(8),

served on [DATE].

[INCLUDE IF APPLICABLE — LOANS:]
        10.     Loan documents for all outstanding loan obligations, pursuant

to Rule 12.285(b)(9), served on [DATE].

[INCLUDE IF APPLICABLE — CREDIT CARDS:]
        11.     Credit card statements for all credit card accounts for the

three (3) months preceding service of the initial pleading, pursuant to

Rule 12.285(b)(10), served on [DATE].

[INCLUDE IF APPLICABLE — BUSINESS INTERESTS:]
        12.     Business tax returns for the three (3) most recent years,

current financial statements (profit and loss and balance sheet), and

business entity agreement, pursuant to Rule 12.285(b)(11), served on [DATE].

[FOR ANY ITEM NOT APPLICABLE — ADD PARAGRAPH:]
        [#].    [DESCRIPTION OF ITEM] is not applicable to [Petitioner /

Respondent] because [SPECIFIC REASON — e.g., "Petitioner is not self-employed

and has no ownership interest in any business entity"].


                                Respectfully submitted,

                                Feinstein & Mendez, PA
                                [ADDRESS LINE 1]
                                [ADDRESS LINE 2]
                                Telephone: [PHONE]
                                Email: [ATTORNEY EMAIL]

                                By: _______________________________
                                    [ATTORNEY FULL NAME], Esquire
                                    Florida Bar No.: [BAR NUMBER]
                                    Attorney for [Petitioner / Respondent]


                        CERTIFICATE OF SERVICE

        I HEREBY CERTIFY that on [DATE], a true and correct copy of the

foregoing Certificate of Compliance with Mandatory Disclosure was served

upon [OPPOSING COUNSEL NAME], Esquire, counsel for [Petitioner /

Respondent], [OPPOSING PARTY NAME], via the Florida Courts E-Filing Portal

[/ via electronic mail to [OPPOSING COUNSEL EMAIL]].


                                    _______________________________
                                    [ATTORNEY FULL NAME], Esquire
```

---

## STEP 3 — {{ROLE_DRAFTER}}'S CHECKLIST BEFORE SENDING TO ATTORNEY

Before {{ROLE_DRAFTER}} sends the draft to {{ROLE_APPROVER}}, she confirms:

- [ ] Case caption matches the operative pleading exactly — party names, case number, court, circuit, division
- [ ] Client role (Petitioner / Respondent) is correct throughout — no reversals
- [ ] Every item served is listed with the correct date
- [ ] Every inapplicable item has a paragraph with the specific reason stated
- [ ] No items are listed as served if {{ROLE_DRAFTER}} cannot confirm service from the tracker
- [ ] Correct pronouns used for the client throughout
- [ ] Correct attorney name in signature block — {{ROLE_APPROVER}}, not both
- [ ] Correct attorney email and bar number in signature block
- [ ] Certificate of Service reflects the actual service method and date
- [ ] Draft saved to {{PM_SYSTEM}} DRAFTS folder before sending for review

---

## STEP 4 — SEND TO ATTORNEY FOR REVIEW

{{ROLE_DRAFTER}} sends the draft to {{ROLE_APPROVER}} via {{PM_SYSTEM}} with the following note:

```
TO: [{{ROLE_APPROVER}}]
FROM: {{ROLE_DRAFTER}}
RE: [Matter Name] — Certificate of Compliance — Ready for Review

Draft Certificate of Compliance attached. Disco tracker confirms all
required items have been served. Please review, sign, and return for
filing via the Florida e-portal.

Items noted as N/A: [List any N/A items and the reason stated in the cert]
Service dates confirmed from tracker: [Yes]
{{PM_SYSTEM}} time logged: [Yes]
```

---

## GUARDRAILS

{{ROLE_DRAFTER}} does not file the Certificate. Filing is attorney function only.
The signed cert goes from {{ROLE_APPROVER}} directly to the e-portal.

{{ROLE_DRAFTER}} does not draft the Certificate if any required item is still missing
or partial in the tracker unless {{ROLE_APPROVER}} has specifically authorized
her to proceed and note the item as N/A with a reason.

{{ROLE_DRAFTER}} does not guess at service dates. Every date in the cert must be
confirmed from the tracker or from the served document itself.

{{ROLE_DRAFTER}} does not use this skill to certify opposing party compliance.
This cert covers client production only. Opposing party compliance issues
go to lal-advanced-discovery for deficiency letter or motion to compel.

All drafting time is logged in {{PM_SYSTEM}} before {{ROLE_DRAFTER}} closes the session.

---

## STAFF LANE SUMMARY

| Who | Does What |
|---|---|
| {{ROLE_DRAFTER}} | Confirms tracker is complete, gathers drafting info, produces draft cert, runs self-checklist, saves to {{PM_SYSTEM}} DRAFTS, sends to attorney with note |
| {{ROLE_REVIEWER}} | Reviews {{ROLE_DRAFTER}}'s work before it goes to attorney if {{ROLE_REVIEWER}} is in the lane |
| {{ROLE_APPROVER}} | Reviews draft, signs, files via Florida e-portal |

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

