---
name: lal-disco-qc
description: "Discovery output QC. Run after every discovery stage and before output moves up the review lane - checks memos, charts, and analyses; flags substantive issues for attorney review."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA discovery output quality control skill for {{ROLE_DRAFTER}}. Use this skill immediately after every discovery stage is complete and before any output moves up the staff lane. Triggers on: "QC this stage," "check my output," "review the memo," "is this ready for {{ROLE_REVIEWER}}," "QC the FA review," "check the crosscheck chart," "QC the income analysis," "review the gap chart," "check the ED chart," "is this stage done," "ready to send to {{ROLE_REVIEWER}}," or any request to review, check, or validate discovery stage output before it moves to {{ROLE_REVIEWER}} or {{ROLE_APPROVER}}. Also triggers automatically after any stage skill produces output — {{ROLE_DRAFTER}} should not advance to the next stage or send output up the lane without running this skill first. {{ROLE_DRAFTER}} fixes errors she can resolve herself. Substantive issues that require legal judgment generate a flagged memo that goes directly to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}. Always assign to {{ROLE_DRAFTER}}.


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

# Feinstein & Mendez, PA Discovery Output Quality Control
## Staff Lane: {{ROLE_DRAFTER}} | Runs After: Every Discovery Stage
## Gates Before: Output moves to {{ROLE_REVIEWER}} or {{ROLE_APPROVER}}

This skill is {{ROLE_DRAFTER}}'s mandatory QC gate. Every discovery stage output —
Stage 2 through Stage 8 — gets checked here before it moves up the lane.
{{ROLE_DRAFTER}} either fixes it herself or generates a flagged memo for {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}.
Nothing advances without clearing this gate.

---

## HOW THIS SKILL WORKS

When {{ROLE_DRAFTER}} triggers this skill, she pastes or references the stage output
to be reviewed and identifies which stage it is. Claude runs the applicable
QC checklist for that stage, categorizes every issue found, and tells {{ROLE_DRAFTER}}
exactly what to do with each one.

**Two outcome categories:**

**{{ROLE_DRAFTER}} Fixes** — Naming errors, math errors, missing party details, wrong
dates, formatting problems, 12.285 category mismatches, incomplete fields,
unclear language. {{ROLE_DRAFTER}} corrects and reruns the stage output before sending up.

**Flagged Memo to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}** — Substantive inconsistencies between the
FA and documents, income figures that don't reconcile, undisclosed accounts,
asset or liability discrepancies that affect case value, anything requiring
legal judgment or attorney strategy input. {{ROLE_DRAFTER}} cannot resolve these — they
go up immediately.

---

## STEP 1 — IDENTIFY THE STAGE

{{ROLE_DRAFTER}} confirms which stage output is being reviewed:

- Stage 2 — Case Summary Memo
- Stage 3 — FA Preliminary Review Memo (Client or OP)
- Stage 4 — FA Cross-Check Chart and Memo (Client or OP)
- Stage 5 — Income Analysis Memo (Client or OP)
- Stage 7 — Discovery Gap Chart and Readiness Memo
- Stage 8 — ED Chart and/or Equalizer
- Final Output — Any compiled output going to attorney for case strategy

If the stage is unclear, ask {{ROLE_DRAFTER}} before running the checklist.

---

## STEP 2 — RUN THE STAGE QC CHECKLIST

### ALL STAGES — Universal Checks (run on every stage)

| Check | What to Verify |
|---|---|
| Party names | First names used consistently — no last-name-only references, no pronouns without prior identification, no reversed party names |
| Case name | Consistent throughout — matches matter name in {{PM_SYSTEM}} |
| Dates | All dates present where required, no placeholder text left in output |
| Math | All figures that can be cross-checked are cross-checked — totals, averages, monthly-to-annual conversions |
| Internal consistency | Figures cited in narrative match figures in charts — no mismatches between sections |
| Attorney review flag | Output carries the standard internal work product disclaimer — not for filing, not for client distribution without attorney approval |
| Completeness | No sections left blank, no "[TBD]" or "[INSERT]" placeholders remaining |
| {{PM_SYSTEM}} time | {{ROLE_DRAFTER}} has logged time for this stage in {{PM_SYSTEM}} before QC runs |

---

### STAGE 2 — Case Summary Memo

| Check | What to Verify |
|---|---|
| Case type confirmed | Dissolution / Paternity / Modification — correct and stated |
| County and circuit | Present and correct |
| Both parties identified | Full names, roles, Petitioner/Respondent confirmed |
| Financial issues flagged | All issues visible in pleadings captured — alimony, ED, child support, dissipation, business interests |
| Issues in dispute | Clearly listed — not vague |
| Mandatory disclosure status | Rule 12.285 timeline noted — when served, when due |
| No legal conclusions | Memo describes facts and issues only — no legal recommendations |

---

### STAGE 3 — FA Preliminary Review (Client or OP)

| Check | What to Verify |
|---|---|
| Correct form identified | Long form or short form — confirmed and stated |
| Party identified | Client or OP — confirmed at top of memo |
| Math audited | Monthly totals, annual totals, net income calculations — all checked |
| Internal inconsistencies flagged | Claimed income vs. expense totals, lifestyle vs. stated income, unusual figures |
| Missing sections flagged | Any FA section left blank or marked N/A without explanation |
| 12.285 checklist cross-referenced | What the FA covers vs. what Rule 12.285 requires — gaps noted |
| No documents compared yet | Stage 3 is FA-only — if document comparison crept in, flag it |

**{{ROLE_DRAFTER}} Fixes:** Math errors, blank field flags, formatting issues, naming errors.
**Flagged to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}:** Income figures that appear implausible, lifestyle-income mismatch, sections left blank that should have entries, any pattern suggesting incomplete or inaccurate disclosure.

---

### STAGE 4 — FA Cross-Check Chart (Client or OP)

| Check | What to Verify |
|---|---|
| Every uploaded document accounted for | Each document {{ROLE_DRAFTER}} uploaded appears in the chart — no document reviewed without a chart entry |
| FA figures vs. document figures | Each row correctly states what the FA claims and what the document shows |
| Status column accurate | Present / Partial / Missing — correctly assigned to each row |
| Discrepancies described precisely | Not "income differs" but "FA states $5,200/mo gross; W-2 shows $67,000 annual ($5,583/mo) — $383/mo variance" |
| Missing mandatory disclosure flagged | Rule 12.285 categories with no document produced — listed and flagged |
| Rolling batch notation | If chart was built across multiple batches, all batches reflected |
| No legal conclusions in chart | Chart states facts and discrepancies only — strategy belongs to attorney |

**{{ROLE_DRAFTER}} Fixes:** Missing chart rows, incorrect status assignments, incomplete descriptions, naming errors.
**Flagged to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}:** Income that does not reconcile across documents, accounts appearing in bank records not disclosed on FA, deposit patterns inconsistent with stated income, asset values that differ materially between FA and documents.

---

### STAGE 5 — Income Analysis (Client or OP)

| Check | What to Verify |
|---|---|
| Income sources all identified | Every income source in the record captured — W-2, 1099, K-1, rental, business, other |
| Averaging methodology stated | How the income figure was calculated — which years, which method, why |
| Year-over-year variance noted | Significant changes across years flagged with the dollar amount |
| Gross vs. net distinguished | Analysis clearly separates gross income from net — no blending |
| Self-employment add-backs identified | Depreciation, personal expenses run through business, non-recurring deductions — all flagged if applicable |
| Rental income net calculation shown | Gross rental income, allowable expenses, net figure — each step shown |
| No child support or alimony calculation | Income analysis does not calculate guideline amounts — that is attorney function |
| Documents supporting each figure cited | Every income figure traceable to a specific document |

**{{ROLE_DRAFTER}} Fixes:** Missing citations, calculation errors, incomplete year coverage, formatting.
**Flagged to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}:** Income figures that cannot be reconciled across sources, unexplained deposit patterns, significant year-over-year variance without explanation, business income that appears understated, rental income with no supporting documentation.

---

### STAGE 7 — Discovery Gap Chart and Readiness Memo

| Check | What to Verify |
|---|---|
| Both parties covered | Gap chart has a row for every 12.285 category for both client and OP |
| Status accurate per party | Produced / Partial / Missing — correctly assigned for each party on each category |
| Cross-party conflicts noted | Items where the two FAs contradict each other — specifically identified |
| Undisclosed accounts flagged | Accounts visible in bank records or tax returns not on either FA |
| Mediation readiness assessment present | Clear statement of what must be resolved before mediation |
| Advanced discovery recommendations present | Specific items — not vague — that need interrogatories, RFPs, or subpoenas |
| Stage 4 and 5 completion confirmed | Gap chart does not run until both parties' Stage 4 is complete |

**{{ROLE_DRAFTER}} Fixes:** Missing rows, incorrect status, formatting, naming errors.
**Flagged to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}:** Undisclosed accounts or assets, cross-party FA conflicts that affect case value, income discrepancies that change support or alimony exposure, patterns suggesting intentional non-disclosure.

---

### STAGE 8 — ED Chart and Equalizer

| Check | What to Verify |
|---|---|
| Every identified asset has a row | Nothing from Stage 7 or the FAs missing from the chart |
| Every identified liability has a row | All debts from both FAs and documents captured |
| Values sourced | Each value tied to a document — no unsourced figures |
| Disputed values flagged | Items where parties disagree on value clearly marked as disputed |
| Marital vs. non-marital column blank or attorney-flagged | {{ROLE_DRAFTER}} does not classify — attorney does; column left for attorney input |
| Equalizer math checked | If equalizer was run — total assets, total liabilities, net equity, equalization payment all verified |
| Scenario modeling labeled | Each scenario clearly labeled — not mixed together |
| No settlement recommendations | Chart presents data — attorney makes the call |

**{{ROLE_DRAFTER}} Fixes:** Missing rows, math errors, unsourced values, formatting, naming.
**Flagged to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}}:** Assets with no supporting documentation, liabilities that appear on one FA but not the other, business interests with no valuation support, equalization numbers that shift significantly across scenarios without explanation.

---

## STEP 3 — DELIVER THE QC RESULT

After running the checklist, deliver one of two outcomes:

---

### OUTCOME A — {{ROLE_DRAFTER}} FIXES

List every issue found in plain language. Tell {{ROLE_DRAFTER}} exactly what to fix
and where. Keep it direct — one line per issue.

```
QC RESULT — [Stage Name] — [Party if applicable] — [Date]
Matter: [Case Name]

STATUS: NEEDS CORRECTION — {{ROLE_DRAFTER}} to fix before sending up

CORRECTIONS REQUIRED:
1. [Specific issue — exactly what is wrong and what the correct version is]
2. [Next issue]
3. [Continue for all {{ROLE_DRAFTER}}-level fixes]

After corrections are made, rerun this QC check before sending to {{ROLE_REVIEWER}}.
Log correction time in {{PM_SYSTEM}}.
```

---

### OUTCOME B — FLAGGED MEMO TO {{ROLE_REVIEWER}} AND {{ROLE_APPROVER}}

Generate a flagged memo {{ROLE_DRAFTER}} sends directly to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}} in {{PM_SYSTEM}}.
The memo attaches or references the stage output with the issues highlighted.

```
DISCOVERY QC FLAG MEMO
TO:     {{ROLE_REVIEWER}} / {{ROLE_APPROVER}}
FROM:   {{ROLE_DRAFTER}}
DATE:   [Date]
RE:     [Case Name] — [Stage Name] QC Flag — Attorney Review Required
MATTER: [{{PM_SYSTEM}} Matter Name]

This memo flags issues identified during QC review of [Stage Name] output
for [Case Name] that require attorney review before this stage can advance.

FLAGGED ISSUES:

Issue 1 — [Category: Income / Asset / Liability / Disclosure]
What the output shows: [Exactly what the stage output states]
Why it is flagged: [Specific inconsistency, discrepancy, or concern]
Documents involved: [Which documents are in conflict]
What attorney review should address: [Specific question for {{ROLE_APPROVER}}]

Issue 2 — [Repeat structure for each flagged issue]

STAGE OUTPUT STATUS: On hold pending attorney review.
{{ROLE_DRAFTER}} will not advance to the next stage until {{ROLE_REVIEWER}} or {{ROLE_APPROVER}} clears this flag.

Time logged in {{PM_SYSTEM}}: [Yes / No — {{ROLE_DRAFTER}} confirms before sending]
```

---

### OUTCOME C — QC PASS

If no issues are found, confirm clearly so {{ROLE_DRAFTER}} can advance.

```
QC RESULT — [Stage Name] — [Party if applicable] — [Date]
Matter: [Case Name]

STATUS: PASS — Ready to advance

No issues found. Output is consistent, complete, and accurate against
the documents in the record. {{ROLE_DRAFTER}} may send to {{ROLE_REVIEWER}} and advance to the
next stage.

Log completion in {{PM_SYSTEM}} before closing this session.
```

---

## GUARDRAILS

{{ROLE_DRAFTER}} does not advance to the next stage until this skill produces either
a PASS or a confirmed CORRECTIONS COMPLETE result. A stage that has not
cleared QC does not move up the lane regardless of time pressure.

{{ROLE_DRAFTER}} does not resolve flagged items herself. If an issue requires legal
judgment it goes to {{ROLE_REVIEWER}} and {{ROLE_APPROVER}} immediately — {{ROLE_DRAFTER}} does not interpret,
speculate, or attempt to explain the discrepancy in the output.

{{ROLE_DRAFTER}} does not send flagged output to the client or opposing counsel under
any circumstances. Flagged output is internal work product on hold.

All time — including QC time — is logged in {{PM_SYSTEM}} before {{ROLE_DRAFTER}} closes
the session. QC is billable work. It does not get skipped to save time.

If the same type of error appears repeatedly across stages on the same
matter, {{ROLE_DRAFTER}} notes the pattern in the flag memo so {{ROLE_REVIEWER}} and {{ROLE_APPROVER}} can
assess whether it reflects a systemic documentation issue.

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

