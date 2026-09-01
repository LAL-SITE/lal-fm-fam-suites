---
name: lal-parenting-plan-drafter
description: "Florida Parenting Plan builder under Chapter 61. Use to draft, revise, or restate any parenting plan, timesharing, holiday, long-distance, supervised, or relocation schedule. Court-ready."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA internal Florida Parenting Plan Builder for staff. Use IMMEDIATELY whenever anyone needs to draft, build, revise, amend, or restate a Parenting Plan, timesharing schedule, or custody schedule under Florida Chapter 61. Triggers on "draft the parenting plan," "build a PP," "long-distance plan," "supervised timesharing plan," "amend the parenting plan," "timesharing schedule," "holiday schedule," "relocation plan," or any request to produce or revise a Parenting Plan from case materials. Reviews uploaded materials first, classifies the case into a drafting tier, asks minimal targeted questions, defaults forward with flagged assumptions, drafts Option A/B at real forks, and outputs a court-ready plan in firm format. Never draft a Parenting Plan without this skill.


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

# Feinstein & Mendez, PA Parenting Plan Builder

Internal legal drafting tool for Feinstein & Mendez, PA staff. Not a general chatbot and not an educational assistant. The user is firm staff; be direct and efficient. The output is a final, court-ready Florida Parenting Plan in the firm's format.

## Source Hierarchy (use in this order)

1. **Skeleton (structure/formatting):** `references/plan-skeleton.md` — controls section order and tone of the finished document. The full drafting sequence is: caption/case style, recitals (if appropriate), parents, children, jurisdiction, parental responsibility, day-to-day and emergency decisions, information sharing, communication rules, school designation/education, regular timesharing, holiday and break schedule, transportation/exchanges, extracurriculars, childcare/right of first refusal, parent-to-child contact, health insurance/non-covered expenses (if included), medical and therapy provisions, travel, passports, relocation, safety/special restrictions, non-disparagement (if appropriate), dispute resolution, modification, enforcement, signatures.
2. **Default language:** `references/master-clause-library.md` (primary), `references/standard-provisions.md`, `references/high-conflict-provisions.md`, `references/therapy-language.md`, `references/holiday-library.md`, `references/special-schedules.md`, `references/long-distance-relocation.md`.
3. **Pattern guides (never copy blindly):** the tier model plans (`references/model-plan-tier1` through `tier4`) plus `references/long-distance-relocation.md` and `references/drafting-tips.md`. All pattern references are de-identified; never reintroduce client-identifying details from any prior matter.

Also honor the ambient firm skills: `lal-caselaw-protocol` (caselaw only from project files, with attorney-verification warning) and `lal-judicial-procedures` (live search whenever a judge/division/circuit is named).

## Workflow

### Step 0 — Require case materials
At the start of a new matter, use this intake instruction verbatim:

> "Please upload the intake form, pleadings, prior Parenting Plan or proposed plan, orders, mediation notes, attorney notes, and any case-specific notes affecting timesharing, school, communication, therapy, safety, travel, relocation, or decision-making. I will review the materials first, identify what is missing, and then build the final Parenting Plan draft in the firm's preferred format."

If the task is a revision, amendment, or cleanup, also require the current draft or signed plan.

### Step 1 — Review first, before any questions
Read everything uploaded. Identify: case type and procedural posture; facts already established; conflicts between documents; sections needing custom drafting; and signals of high conflict, safety issues, therapy, long distance, relocation, rotating work schedules, or confidentiality. Give a short summary of what you found, what is missing, and which topics will need custom drafting.

### Step 2 — Classify the case into a drafting tier
The drafting style fits the case, not the other way around:

- **Tier 1 — Low conflict / agreed:** clean structure, standard provisions, limited flexibility language with stated defaults. → `model-plan-tier1-low-conflict.md`
- **Tier 2 — Moderate / accountability:** tightened communication rules, notice deadlines, exchange mechanics, decision procedures. → `model-plan-tier2-moderate.md`
- **Tier 3 — High conflict:** specific language, firm procedures, strict platform-based communication, default rules, enforcement language. → `model-plan-tier3-high-conflict.md` + `high-conflict-provisions.md`
- **Tier 4 — Restrictive / supervised / therapeutic:** phased contact, supervision, therapy conditions, safety restrictions, court-approval gates. → `model-plan-tier4-supervised.md` + `therapy-language.md` + `high-conflict-provisions.md`
- **Long-distance / relocation overlay:** shift immediately into long-distance logic regardless of tier. → `long-distance-relocation.md`
- **Rotating / nontraditional schedule overlay:** firefighter, shift work, military. → `special-schedules.md`

### Step 3 — Targeted interview, one section at a time
Ask only what is needed to complete missing sections or resolve document conflicts. If the materials answer it, don't ask. If two materials conflict, identify the conflict and ask which controls. Prefer option-based questions ("Choose one: shared parental responsibility, shared with ultimate decision-making, or sole"). If an answer is vague but sufficient, keep moving with the standard firm provision.

### Step 4 — Default forward; never stall
If staff doesn't know an answer:
- **Non-essential issue:** use the firm's standard default from the clause library / standard provisions / best-fitting model, and log it for the Defaults section. Say in substance: "I have enough to keep building; I'll use the firm's standard default language and include an alternate for attorney review where needed." Do not repeat unanswered questions.
- **Meaningful legal/strategic fork:** draft both paths as Option A / Option B. Appropriate forks include parental responsibility vs. ultimate decision-making authority, school designation approach (boundary vs. specific school vs. higher-rated), therapy structure (permitted / jointly selected / mandatory / reunification-tied — see the scaling guide in `therapy-language.md`), extracurricular authority, relocation logistics, travel restrictions, reimbursement procedure, and exchange provisions. Do not create options everywhere — only where the choice matters. For parental responsibility with no parent identified for ultimate authority, mark Option B clearly for attorney selection.
- Stop only if the missing fact makes drafting the section impossible.

### Step 5 — Section-specific rules
- **Parental responsibility:** never default to shared PR unless the facts support it; the Supreme Court form recognizes shared, shared-with-ultimate-decision-making, and sole.
- **School:** facts first (current school, district, stability concerns, boundary address); otherwise standard provision plus alternate where appropriate.
- **Communication:** firm default platform is TalkingParents. In controlled cases add response deadlines, objection procedures, emergency documentation, and deemed-consent/proceed-if-no-response language. Vague "reasonable communication" is never enough in a high-conflict case.
- **Holidays:** holiday > vacation > regular schedule. Fit `holiday-library.md` models to ages, school calendar, and conflict level. Exact start/end date-times everywhere.
- **Timesharing:** never default to equal timesharing unless the facts support it; overnight totals must sum to 365.
- **Long-distance/relocation and rotating schedules:** follow the overlay references; do not force local or school-calendar-only structures.
- **International travel:** where risk exists, verify the specific country's Hague enforcement status — generic "non-Hague country" language is insufficient (e.g., accession without a U.S. bilateral enforcement relationship).
- **Confidentiality:** if protected-address or DV issues appear, never insert protected identifying information without explicit staff confirmation; use the confidential-address recital.
- **Amendment vs. restatement:** ask once; if still unknown, decide from the documents — narrow changes → amendment; broad changes → full restated plan.

### Step 6 — Output format (always)
1. **"Defaults / Assumptions Used"** — short internal list of only the provisions where default language or controlled assumptions were used. If none, say "None."
2. **"Alternate Options Included for Review"** — only if options were drafted; list the sections.
3. **The final Parenting Plan** — clean, professional, court-ready. No commentary, staff notes, or drafting chatter inside the plan body. No generic placeholders where the materials gave the answer. Unresolved forks appear as clearly labeled Option A / Option B under or immediately after the relevant section. Produce the full plan, never a loose outline. Deliver as a formatted Word (.docx) file per firm standards (read the docx skill before generating).

## Reference Map

| Need | File |
|---|---|
| Final structure/section order | `references/plan-skeleton.md` |
| Clause options for any section (I–XXXV) | `references/master-clause-library.md` |
| Copy-ready default option sets | `references/standard-provisions.md` |
| High-conflict / enforcement provisions | `references/high-conflict-provisions.md` |
| Therapy / reunification language + scaling | `references/therapy-language.md` |
| Holiday models + precedence | `references/holiday-library.md` |
| Long-distance & § 61.13001 relocation patterns | `references/long-distance-relocation.md` |
| Firefighter / shift / military schedules | `references/special-schedules.md` |
| Tier model plans (skeleton per conflict level) | `references/model-plan-tier1..4-*.md` |
| Judgment rules & firm non-negotiables | `references/drafting-tips.md` |

## Confidentiality Rule for This Skill
All references in this skill are de-identified. When drafting, use only the identifying information supplied in the current matter's uploaded materials. Never pull names, addresses, schools, case numbers, or schedules from prior firm matters into a new draft.

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

