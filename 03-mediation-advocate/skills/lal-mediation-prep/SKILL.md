---
name: lal-mediation-prep
description: "Advocate-side mediation preparation. Use when mediation is scheduled - readiness check, refreshed ED and support numbers, tiered proposals, confidential mediator summary. Run before session."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA advocate-side mediation preparation engine. Use IMMEDIATELY whenever a mediation is scheduled on a matter where Feinstein & Mendez, PA represents a party. Triggers on: "prep for mediation," "mediation prep," "mediation is set," "build the mediation package," "draft our proposal," "summary for the mediator," "mediation memo," "are we ready for mediation," "run the numbers for mediation," or any request to prepare a party's side for mediation. Produces the complete Mediation Prep Package: readiness check, refreshed ED chart and equalizer scenarios, support numbers, full command center update, tiered settlement proposal drafts, and the confidential summary for the mediator. Pulls live data from the discovery skills when their output exists; takes manual entries when it does not. Distinct from lal-mediation-advocate (the live in-session command center). Run BEFORE the session.


## Feinstein & Mendez, PA Firm-Wide Conventions (apply to every run of this skill)

These six conventions govern all Feinstein & Mendez, PA skills and override any narrower instruction
below that conflicts with them.

1. **Environment-flexible.** Complete the task in the environment you are already in
   — chat, Desktop, or Cowork. If a different environment would be materially better,
   say so in one line and keep working. Never block, never redirect, never hand off
   instead of doing the work.
2. **Identity over lanes.** Staff assignments in this skill are defaults, not gates.
   Anyone may run any skill. **Attorneys self-approve** — if the person running this
   skill is {{ROLE_APPROVER}}, they *are* the approving attorney.
3. **Just run it.** Prerequisite stages are soft checks, never hard gates. Pause only
   for a physically necessary input, and ask for that specific item by name.
4. **Read files first.** Search the entire matter file — including misnamed and
   misfoldered documents — before declaring anything missing.
5. **Transcripts preferred, never required.** A typed memo or rough notes always
   suffice as input.
6. **Write to the command center.** Every stage completion, deadline, lifecycle move,
   and attorney flag is written to the matter's command center before the run ends.

---

# Feinstein & Mendez, PA Mediation Prep — Advocate Side

## What this produces

One complete **Mediation Prep Package**, assembled in five steps, saved to DRAFTS,
nothing released without attorney approval:

1. Readiness check and posture snapshot
2. Refreshed ED chart + equalizer scenarios and support numbers
3. Full command center update
4. Tiered settlement proposal drafts (opening + fallback positions)
5. Confidential summary for the mediator

Run the steps in order. Each step states its data source and its fallback.

---

## Step 0 — Confirm the Session

Collect before anything else (ask only for what the file does not already show):

- Mediation date, time, format (in person / Zoom / hybrid), and mediator name
- Which party Feinstein & Mendez, PA represents (Petitioner / Respondent) and client's first name
- Court-ordered or voluntary; any CMO/order language governing the mediation
- Issues open for mediation: PEACE run-through — Parenting, Equitable distribution,
  Alimony, Child support, Everything else (fees, name restoration, exclusive use, etc.)

Log the mediation event and any order-driven deadlines to the command center now,
not at the end.

---

## Step 1 — Readiness Check and Posture Snapshot

Data source: the matter's command center, the disco tracker, and the Stage 7
discovery gap chart / readiness memo if they exist (lal-discovery-gap output).

- Summarize procedural posture: filed, served, answered, disclosure status both
  directions, pending motions, prior offers.
- Pull the discovery readiness conclusion. If the gap chart shows material gaps,
  flag: **"mediating with incomplete discovery — attorney decision required"** and
  list exactly what is missing and from whom.
- If no discovery-gap output exists in the file, run the readiness check manually:
  FA on file for both parties? Mandatory disclosure exchanged? Support numbers
  computable? State what is missing; do not block the prep.

Output: **Posture & Readiness section** of the prep memo.

---

## Step 2 — Numbers: ED Chart, Equalizer, Support

Data sources, in priority order:

1. **ED chart + equalizer** — latest Stage 8 / Stage 8-Bonus output (lal-ed-chart).
   If present: refresh values that have changed (new statements, paid-down balances,
   updated appraisals) and re-run the equalizer math. If absent: offer to run
   lal-ed-chart now if the FA cross-check data exists; otherwise take the asset
   and liability inventory by manual entry from the attorney or paralegal.
2. **Child support** — latest lal-cs-worksheet output; recompute if income figures
   changed. If absent, take guideline inputs manually and flag that the worksheet
   skill should be run for the filing-grade version.
3. **Income / alimony inputs** — lal-income-analysis output where income is disputed;
   otherwise FA net incomes. Alimony need/ability framing is attorney work product —
   present the numbers, flag the positions, never state a legal conclusion.

Build **scenario tiers** with the equalizer engine: at minimum, (A) client's preferred
outcome, (B) midpoint / probable court range as the attorney frames it, (C) walk-away
floor/ceiling. Every scenario shows the resulting equalization payment and monthly
support so the client can see each package as real dollars.

Output: **Numbers section** — ED chart snapshot, equalizer scenarios A/B/C, CS
guideline number, income findings. Excel for charts, per lal-output-standards.

---

## Step 3 — Full Command Center Update

Write to the command center (lal-command-center):

- Mediation event: date, mediator, format, order-driven deadlines
- Stage completion: "Mediation prep package built — v[N]"
- Current settlement posture: last offer each direction, date, response
- Open attorney flags from Steps 1–2 (discovery gaps, disputed income, appraisal age)
- Post-mediation follow-ups pre-staged: MSA drafting if settled (lal-msa-drafter),
  trial-track deadlines if impasse

This is a FULL update — the command center must let the attorney walk into the
session with zero file re-reading.

---

## Step 4 — Draft Proposals (Attorney Hard Stop)

Draft the client's proposal set as clean, service-ready documents:

- **Opening proposal** — full PEACE terms consistent with Scenario A
- **Fallback positions** — one document per tier the attorney authorizes, each a
  complete package (never trade a term without stating the paired concession)
- Parenting terms reference the parenting plan structure (lal-parenting-plan-drafter
  provisions) when timesharing is open
- Each proposal states its expiration and reservation-of-rights language
- Format: Word first for attorney markup; PDF version on approval for transmission

**HARD STOP: no proposal leaves the firm without explicit attorney approval.** {{ROLE_DRAFTER}}
drafts, {{ROLE_REVIEWER}} reviews, {{ROLE_APPROVER}} approves. If the attorney is running the skill,
their direction is the approval.

---

## Step 5 — Confidential Summary for the Mediator

Draft the **Confidential Mediation Summary** addressed to the mediator only:

- Header: matter style, mediation date, author attorney, and the legend
  **"CONFIDENTIAL MEDIATION COMMUNICATION — prepared exclusively for the mediator
  under sections 44.401–44.406, Florida Statutes; not filed, not served."**
- Case background: 1-page maximum narrative, facts only, no argument theater
- Issues in dispute, party positions on each, and movement history (offer log)
- ED snapshot and support numbers (from Step 2) at summary level
- What settlement needs to look like for the client — framed by the attorney
- Logistics: client emotional posture, safety concerns, interpreter needs, who
  attends, authority limits

Statutory references above are fixed statutory citations, not caselaw. Any caselaw
the attorney wants cited in the summary follows lal-caselaw-protocol — project
files only, verification warning attached.

**HARD STOP: the summary goes out only after attorney approval, and only to the
mediator — never filed, never served on opposing counsel.**

---

## Package Assembly and Delivery

Assemble the approved pieces into the Mediation Prep Package:

1. Prep memo (posture, readiness, numbers, strategy flags) — Word
2. ED chart + equalizer scenarios — Excel
3. Proposal set — Word drafts / PDF finals
4. Confidential mediator summary — Word draft / PDF final
5. Client prep sheet — what to expect, authority confirmed, logistics

Delivery per lal-file-connector: DRAFTS folder in the {{DMS}} matter folder,
`MM.DD.YY - LastName - Mediation Prep Package - v1` versioning, never overwritten.
Time logged in {{PM_SYSTEM}}, including Claude-assisted work.

Then hand off: the live session itself runs on **lal-mediation-advocate** — tell the user
that skill takes over on mediation day and the offer log seeded here carries in.

---

## Degradation Rules

- No lal-ed-chart output and no cross-check data → manual asset/liability entry;
  chart marked "manual entries — not discovery-verified."
- No lal-cs-worksheet → manual guideline inputs; flag for worksheet run before
  any agreement is signed.
- No command center → create it (first touch) rather than skipping Step 3.
- Discovery materially incomplete → prep continues, but the memo leads with the
  attorney flag; the decision to mediate anyway is the attorney's alone.

## What This Skill Does NOT Do

- Does not run the live session (lal-mediation-advocate) or act as neutral (mediator skills)
- Does not send anything to the mediator, client, or opposing counsel itself
- Does not state legal conclusions on alimony entitlement or ultimate outcomes
- Does not cite caselaw outside lal-caselaw-protocol
