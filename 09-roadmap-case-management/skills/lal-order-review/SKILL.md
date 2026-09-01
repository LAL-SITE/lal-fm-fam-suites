---
name: lal-order-review
description: "Court order review engine. Use when any order, judgment, or ruling arrives - extracts rulings, obligations, and deadlines, computes response and appeal windows, updates the command center."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA court order review engine. Use IMMEDIATELY whenever a court order, final judgment, or ruling arrives or appears in a matter folder. Triggers on: "an order came in," "the judge ruled," "review this order," "order entered," "we got the final judgment," "what does the order require," "what are our deadlines under the order," "docket the order," or any new document in the ORDERS folder. Reads the order, extracts every ruling, obligation, deadline, and compliance item, calculates response and appeal windows, updates the command center and pleading log as a mandatory step, and routes follow-up work to the right skill. Also handles notices: every notice issued or received is logged to the command center the same way. Review is not complete until the command center is updated. Always assign to {{ROLE_DRAFTER}}; deadline calculations and legal-effect reads go to {{ROLE_APPROVER}} for confirmation.


## Feinstein & Mendez, PA Firm-Wide Conventions (apply to every run of this skill)

These six conventions govern all Feinstein & Mendez, PA skills and override any narrower instruction
below that conflicts with them.

1. **Environment-flexible.** Complete the task where you are; suggest a better
   environment in one line if warranted, and keep working.
2. **Identity over lanes.** Staff assignments are defaults. Attorneys self-approve.
3. **Just run it.** Soft checks, never hard gates.
4. **Read files first.** Search the whole matter file before declaring anything missing.
5. **Transcripts preferred, never required.**
6. **Write to the command center** before the run ends.

---

# Feinstein & Mendez, PA Order Review

## Scope

Runs on every court-issued document: orders, final judgments, orders to show
cause, case management orders, agreed orders after entry, and (in its logging
function) every notice issued or received. Governed by lal-filing-status-rules:
a document reviewed here must actually be in ORDERS (or NOTICES) or confirmed
entered — never a proposed order still in DRAFTS.

## Step 1 — Read and verify

OCR-verify per lal-document-intake-rules. Confirm: signing judge, entry date
(stamp/e-filing date, not the hearing date), matter, and that the copy is the
entered version (signature + date present), not a proposed version.

## Step 2 — Extract, ruling by ruling

Build the Order Digest — one row per operative provision:

| # | Provision (verbatim cite) | Who is obligated | What is required | Deadline / trigger | Affects (PEACE category) |

Capture: every ordered act, every deadline (compute actual dates from entry or
service as the order specifies), payment obligations with amounts and start
dates, timesharing changes, purge conditions, fee awards, reserved issues, and
anything the court retained jurisdiction over.

**Deadline math is drafted, not decided:** show the computation (trigger date +
period + weekend/holiday rule) and flag every computed date for attorney
confirmation. Rehearing and appeal windows are ALWAYS flagged to the attorney
with the computed date — never silently assumed waived.

## Step 3 — Mandatory command center update (review is not done without this)

Write to the command center before the run ends:

1. **Pleading log entry** — the order/judgment as an entered docket event:
   date entered, title, judge, direction (court), evidence (ORDERS folder /
   stamped copy).
2. **Deadlines** — every computed deadline with its trigger and confirmation
   status.
3. **Obligations** — recurring obligations (support start, exchanges, payments)
   as tracked items.
4. **Lifecycle move** — if the order changes posture (temp relief entered,
   judgment entered, case closed, jurisdiction reserved), record it.
5. **Attorney flags** — appeal/rehearing window, ambiguities, conflicts with
   prior orders, scrivener's errors.

The same rule applies to notices: every notice issued or received gets a
pleading log entry (date, title, direction, hearing date if set) and its
deadlines — a notice of hearing that never reaches the command center is a
missed hearing waiting to happen.

## Step 4 — Route follow-ups

- Compliance items on our client → client letter via lal-correspondence
  (attorney approval before sending)
- Enforcement posture if the other party violates → lal-contempt-movant
- Judgment entered → lal-case-closing candidacy check
- Modification/appeal considerations → memo to {{ROLE_APPROVER}}/{{ROLE_APPROVER}} via lal-case-memo
- Roadmap shift → lal-case-roadmap update

## Output

Order Review Memo (Word, per lal-output-standards): digest table, deadline
computations with flags, command center entries written (listed), and routed
follow-ups. Save to NOTES via lal-file-connector; log time in {{PM_SYSTEM}}.

## What This Skill Does NOT Do

- Does not draft orders (drafting skills) or decide legal effect (attorney)
- Does not treat a proposed order in DRAFTS as entered
- Does not calendar a deadline as confirmed without attorney sign-off
