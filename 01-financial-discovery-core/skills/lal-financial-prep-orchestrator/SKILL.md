---
name: lal-financial-prep-orchestrator
description: "Single-pass client financial prep. Use to build the FA draft AND the client request email for missing items in one session - orchestrates the FA builder, gap analysis, and brand kit."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA Cowork-native client-side financial prep workflow. Use this skill IMMEDIATELY whenever {{ROLE_DRAFTER}}, {{ROLE_REVIEWER}}, or {{ROLE_APPROVER}} needs to prepare a client's Financial Affidavit AND a client communication requesting items still missing — in a single Cowork pass. Triggers on: "client cowork financial prep," "FA prep," "build the FA," "build the FA and tell me what's missing," "prep the FA and ask the client for what we don't have," "do the financial prep for [client]," "draft the FA and the request letter," "what do we still need from the client," "FA + missing items email," or any variation. ORCHESTRATES lal-fa-builder + lal-brand-kit with a document-attribution audit and gap analysis so a single Cowork session produces the complete pre-call package — FA Long Form 12.902(c) DRAFT plus a brand-kit client request email. Run before any individual FA-related skill once intake and initial discovery are in.


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

# Feinstein & Mendez, PA Client Cowork Financial Prep

## Purpose

This is the integrated end-to-end workflow for preparing a client's Financial Affidavit in Cowork. It runs after intake forms have been completed and after the first batch of client-supplied financial documents has been organized, and it delivers two paired outputs in a single session: (1) a populated Long Form 12.902(c) Financial Affidavit DRAFT, and (2) a brand-kit-compliant client email requesting every item still missing.

The reason this is one skill instead of three separate skills is that the FA build and the request-for-missing-items email feed each other. You cannot draft a useful client email until you've actually tried to populate the FA and seen exactly what's blank or unverified — and you cannot finalize the FA until the client provides those items. Doing them as a single pass gives the supervising attorney a complete pre-call package: a draft FA marked DRAFT on every page with every gap footnoted, plus a ready-to-send email asking the client for precisely the items the FA is missing.

## Lane and Scope

This skill runs in Cowork. It is internal work product. Nothing produced by this skill is filed, sent to the client, or shared with opposing counsel without explicit attorney review and sign-off.

Default assignment: {{ROLE_DRAFTER}} (legal assistant) for routine matters where the discovery folder is already organized; {{ROLE_REVIEWER}} (lead paralegal) when the matter is mid-flight and requires judgment on what items are gaps versus deliberate omissions. Output goes to the attorney for review.

Scope OUT: do not run this skill if the FA has already been finalized and filed, or if the matter does not yet have at least one completed intake form. If documents have arrived but are not yet sorted in {{DMS}}, run `lal-disco-intake-prep` first.

## The Six Stages

This skill runs six stages in order. Do not skip stages. If a stage cannot be completed because of missing input, document the gap and continue — the email at Stage 5 is the mechanism for resolving those gaps.

### Stage 1 — Read and Anchor Case Context

Before touching any financial document, read enough of the matter file to know who the client is, who the opposing party is, where the case stands, and what the attorney has already pleaded.

At minimum, read:

- The lead call memo (or equivalent intake summary)
- The scope of representation summary
- Both client intake forms (the DOM Petitioner intake and the Equitable Distribution intake)
- The petition or response, if filed
- The retainer agreement, for scope confirmation

The goal of Stage 1 is to write a one-paragraph mental note before opening any financial PDF: who the client is, what their stated income source is, what they've pleaded, and what major issues are flagged. This anchors every downstream decision.

### Stage 2 — Document Attribution Audit (CRITICAL)

This is the most important stage and the one most likely to be done wrong. Every financial document in the matter folder must be attributed by the name actually on the document — not by the folder it sits in, not by the filename, and not by an assumption that "everything in this client's folder belongs to the client." Family law matters routinely contain both spouses' documents (joint returns, mandatory disclosure from the OP, statements collected from joint files), and misattributing a spouse's W-2 or 1099 to the client distorts the FA and creates downstream errors.

For each financial document in the discovery folder, open it and confirm whose name appears in the recipient or employee field. Do not infer. Do not lump.

Examples of what attribution looks like in practice:

- A W-2 with "THOMAS LEE LIMBAUGH" on it does not go on Lisa's FA, even if it sits in Lisa's matter folder.
- A 1099-R from DFAS in Thomas's name is Thomas's military retirement income — not Lisa's.
- A joint 1040 reflects both spouses' income; reading it requires breaking out the spouse-specific lines.
- An SSA-1099 names a single beneficiary — that benefit belongs to the named person only.
- Bank statements name the account holder(s); a joint "OR" account is shared, a sole-name account is not.

Build a short attribution map (in your head or on a scratch note) before populating any income or asset line. If the case profile in your project instructions says the client has no earned income but the folder contains a W-2, that conflict is the W-2 belonging to the spouse — not a sign that the case profile is wrong. Confirm by opening the document.

Saving even one wrong attribution into the FA can cause hours of rework later. Take the time.

### Stage 3 — Build the FA Long Form

Delegate to `lal-fa-builder` for the form structure, line-by-line population, deduction audits, and footnote register. Follow that skill's protocol exactly. Two governance notes specific to this orchestrating workflow:

**Form selection.** When the client has any income source that is not yet documented (a VA Disability Compensation amount with no award letter on file, undocumented self-employment, irregular gig income), default to the long form 12.902(c) regardless of what the documented income totals to. Income that is undocumented today often pushes annual gross above the $50,000 short-form threshold once captured, and rebuilding from short-form to long-form is wasted work. Footnote the conservative selection.

**Vehicle, account, and debt completeness.** When you build out Sections III and IV (Assets and Liabilities), cross-check the client's intake against the actual statements in the discovery folder. If a checking account appears in the bank statement batch but not on the intake form, list it on the FA with a flag — these are routinely the most consequential omissions. Same for an unlisted savings account, second checking, or money market.

**The output is always a Word document marked DRAFT — INTERNAL USE ONLY — SUBJECT TO ATTORNEY REVIEW — NOT FOR FILING on every page.**

### Stage 4 — Gap Identification

After Stage 3 produces the FA draft, walk the document end to end and capture every line that is incomplete, every value marked [TBD], and every footnote that begins with the FLAG or RED FLAG marker. The output of Stage 4 is a single internal punch list of items the client must provide before the FA can be filed.

Group the punch list into three buckets:

1. **Critical (RED FLAG)** — items without which the FA cannot be filed at all. Almost always this includes the income figure when an income source is undocumented. Example from the Limbaugh matter: VA Disability Award Letter — without it, gross monthly income is incomplete and Line 27 net income cannot be calculated.

2. **Time-sensitive** — items the attorney will want for the upcoming intake or strategy call. Common entries include: monthly expenses (the entire Section II), vehicle values when only some vehicles have known KBB figures, minimum monthly payments on each creditor account, and confirmation of any account that appears in the disco batch but not on the intake form.

3. **Follow-up** — items the attorney will want before MSA drafting but that are not critical for the FA itself. Trust documents (when a trust has been pleaded as separate property), life insurance policies, SBP elections, and post-decree retirement order source documents (DFAS RAS, OPM SF-50, TSP statement) typically land here.

The punch list should be written from the client's perspective — what does Lisa need to send us — not from the firm's perspective.

### Stage 5 — Draft the Client Email

Delegate to `lal-brand-kit` for the email structure, fonts (Arial throughout for Word), color rules (Pink/Orange/Lime/Teal four-color bar header and footer, Pink dividers, Teal field labels), three CTAs at close, and confidentiality notice.

The email translates Stage 4's punch list into a short, plain-English client communication. Voice rules from the brand kit apply: short paragraphs, plain English, no jargon, no corporate filler, no exclamation points in body copy.

Email structure for this skill specifically:

- Field block at top: DATE / TO / FROM / RE / MATTER (FROM should reflect the actual sending lane — {{ROLE_REVIEWER}} for routine pre-call paralegal communications, {{ROLE_DRAFTER}} for disco-only items, attorney for strategy items)
- Salutation
- Two or three short paragraphs explaining what was drafted, what the biggest gap is, and what timeline the client should expect
- A clearly labeled "TIME-SENSITIVE — please bring or send before [next call date]" section with numbered items and indented sub-bullets
- A clearly labeled "FOLLOW-UP — when you can in the next week or two" section
- A short, warm close (avoid "Best regards" / "Sincerely" — use "Warmly" or "Talk soon")
- Brand signature block
- Three CTAs (Schedule a free consult / Book a paid strategy session / Skip the consult — move forward) per brand kit Section 6
- Confidentiality notice in 8pt mid-gray italics

When the request mentions a specific document, give the client the easiest path to find it — for the VA Award Letter, point them to VA.gov → Get your VA benefit letters → Benefit Summary Letter, with the My HealtheVet portal as an alternate, and the VA phone number as a fallback. The email should be the path of least resistance for the client to comply.

### Stage 6 — Save and Hand Off

Save both outputs to the matter folder under `DRAFTS/`. If the `DRAFTS/` subfolder does not exist, create it.

File naming convention:

- FA: `[ClientLastName]_FA_LongForm_DRAFT_YYYY-MM-DD.docx`
- Email: `[ClientLastName]_FA_DocsRequest_Email_YYYY-MM-DD.docx`

Optionally also save PDF previews with the same filename and `.pdf` extension; these help the supervising attorney review on a phone or tablet.

Update the discovery tracker (`lal-disco-tracker`) with the items being requested in the email and the date the request is going out. The tracker becomes the running record of what is outstanding.

Hand-off rule: {{ROLE_DRAFTER}} or {{ROLE_REVIEWER}} completes this skill and routes BOTH outputs to the attorney via {{PM_SYSTEM}} for review. Nothing leaves the firm to the client without attorney sign-off.

## Pre-Filing Audit Checklist

Before declaring this skill complete, run this checklist against the FA draft. This is the same checklist required by the fa-builder skill, repeated here so it cannot be skipped.

1. Correct form selected (long vs. short) based on documented gross income, with conservative bias to long form when income is undocumented.
2. Every income source from intake addressed on the FA.
3. Total monthly gross income calculated and shown — even if marked "INCOMPLETE pending [X]".
4. All deductions itemized; FICA and Medicare present where applicable, audit performed for double-counting between deductions and expenses.
5. Net monthly income calculated.
6. All expense lines populated (zeros not blanks); blanks indicate forgetting, not absence.
7. Bank accounts, real property, vehicles, retirement accounts, and personal property all listed with current values or `[TBD]` flags.
8. Liabilities listed with balances and minimum monthly payments or `[TBD]` flags.
9. RED FLAG items documented in the footnote register.
10. Signature block and certification language present.
11. "DRAFT — INTERNAL USE ONLY — SUBJECT TO ATTORNEY REVIEW — NOT FOR FILING" header on every page.
12. Footnote register complete and numbered sequentially.

If any item fails, note the gap and do not mark the FA as complete. The same gap should appear on the client email.

## Output Requirements

Two Word documents per session, both saved to the matter folder under `DRAFTS/`:

1. The FA Long Form 12.902(c) DRAFT — a fully structured Florida Supreme Court approved long form, populated with what is known, footnoted with what is not, and marked DRAFT on every page.

2. The brand-kit-compliant client request email — Arial throughout, four-color bar header and footer, Pink dividers, Teal field labels, two-tier action list (TIME-SENSITIVE / FOLLOW-UP), warm close, three CTAs, confidentiality notice.

Optionally also save PDF previews of each. Optionally also generate a one-page Attorney Flag Summary (per the fa-builder skill's `Generate the FA Flag Summary` command) if the supervising attorney has asked for one.

## Triggering Notes

This skill is the orchestrator. When the user says any of the trigger phrases listed in the description above, run this skill — even if they only mentioned the FA, only mentioned the email, or only said "do the financial prep." The reason is that nine times out of ten the supervising attorney needs both outputs together for the next client touchpoint, and the gap analysis at Stage 4 is the bridge that makes them coherent.

If the user explicitly says "JUST build the FA, don't draft the email" or "JUST draft the email, don't touch the FA," respect that and route to the individual skill (`lal-fa-builder` or `lal-brand-kit`) rather than running this orchestrator.

## What This Skill Does NOT Do

- Does not file the FA. Filing requires attorney review and signature.
- Does not send the email. Sending requires attorney review.
- Does not assess legal questions about which income items are includable in alimony calculations, which assets are marital vs. non-marital, or how to characterize retirement assets — those are attorney decisions captured in footnotes, not resolved here.
- Does not produce alimony calculations, child support guidelines worksheets, or ED equalizer charts — those are downstream skills (`lal-alimony-assessment`, `lal-cs-worksheet`, `lal-ed-chart`).
- Does not handle opposing-party financial review — that workflow is `lal-op-disco-review`, run separately when the OP serves their FA.

## Reference Files

- `references/document-attribution-rule.md` — The full document attribution rule, with worked examples.
- `references/missing-items-template.md` — Reusable language for the most common missing-item asks (VA award letter, monthly expenses, undisclosed accounts, vehicle values, minimum monthly payments, trust documents, life insurance).

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

