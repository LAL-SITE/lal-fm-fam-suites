---
name: lal-firm-adaptation
description: "Post-install adaptation engine. Use to teach installed LAL skills the firm's templates, style, naming, and preferences - scans firm files read-only and writes overlays that layer on the LAL base."
---

# LAL Firm Adaptation — Learn the Firm, Layer the Preferences

## When to use this skill (full trigger reference)

Legal Authority Lab post-install firm adaptation engine. Ships in Core Foundation. Run AFTER lal-installer, once the firm's document storage is connected. Triggers on: "adapt the skills to our firm," "learn our templates," "run the firm adaptation," "scan our matters," "make the skills match how we draft," "learn our style," "our parenting plans look different," "use our naming," "apply our formatting," or any request to teach the installed LAL skills a firm's own templates, style, naming, organization, or preferences. Read-only against firm files, de-identified overlays, re-runnable, and every overlay survives suite updates. Distinct from lal-installer (identity and profile) and from LAL's internal onboarding sweeps.

## The layering rule (read first — this governs everything)

**LAL libraries are the base. The firm's practices are an overlay. Overlays add
and prefer; they never delete, never overwrite, never shrink the base.**

- The firm's parenting plan template becomes a *firm-preferred model* offered
  first — the LAL tiered model plans and clause library stay fully available.
- The firm's caption/signature format becomes the *default format* — the LAL
  format standard remains as the fallback and the compliance reference.
- The firm's naming convention becomes the organizer's *active convention* —
  the LAL default stays documented beside it.
- On any conflict between a firm pattern and a legal-compliance rule (form
  requirements, mandatory language, court formatting), the compliance rule wins
  and the conflict is flagged to the attorney — never silently adopted.

## Where overlays live (changed — read carefully)

Installed LAL skills arrive through the firm's org-managed plugin marketplace
and are **read-only** — nothing can be written inside a skill folder on the
firm's side. Overlays therefore live in the **firm's own storage**, in the
overlay folder recorded in the Firm Profile (default: `LAL OVERLAYS/` under the
firm's admin or knowledge root; a firm working primarily in a Claude Project
may keep them as Project docs instead). This is BETTER for survival: suite
updates replace skills, but never touch the firm's storage — every overlay
survives every update automatically.

Every LAL skill that supports adaptation checks the Firm Profile for the
overlay folder and reads its own overlay (`<skill-name>.overlay.md`) at the
start of a run, when one exists.

## Phase 1 — Scan (read-only)

Using the storage configured by lal-file-connector, sample the firm's real work:

1. **Templates folder** — every template, form, and model document.
2. **Recent matters** — 5–10 matters across the firm's case types. From each:
   filed pleadings, agreements, parenting plans, letters, and the folder
   structure itself.
3. **Sent correspondence** — a sample per attorney for voice.

Hard rules: read-only — never move, rename, or edit a firm file. Confirm the
folders with the user before scanning. Report what was sampled.

## Phase 2 — Extract the firm's standards

From the sample, build the firm's practice profile:

- **Format spec:** caption block, fonts, margins, paragraph numbering style,
  heading conventions, signature blocks, certificate of service language,
  exhibit conventions, footer habits.
- **Naming and organization:** file naming patterns, folder taxonomy per matter,
  versioning habits, where drafts vs. finals live.
- **Drafting preferences:** clause and provision language the firm reuses
  (parenting plan provisions, MSA boilerplate, motion openings, prayer
  formulations), preferred document structures, length norms.
- **Voice:** correspondence tone per attorney, openings/closings, formality
  gradient, always/never phrases.
- **Workflow signals:** who signs what, review habits, stage vocabulary.

De-identification is mandatory: every extracted example is scrubbed of client
names, case numbers, addresses, and any party-identifying detail — patterns and
language only, with matter-level tokens where specifics appeared.

## Phase 3 — Write the overlays

Write results as **new files in the firm's overlay folder** — never anywhere
inside an installed skill:

1. **Master overlay** — `firm-practice-profile.md`: the complete extracted
   profile, versioned and dated.
2. **Per-skill overlays** — `<skill-name>.overlay.md`, one per installed skill
   the finding is relevant to (drafting skills get format + clause preferences;
   file organizer gets naming + taxonomy; correspondence gets voice; parenting
   plan drafter gets the firm's preferred provisions and models; MSA drafter
   gets their boilerplate; command center gets stage vocabulary). Each overlay
   states: what the firm prefers, the de-identified example, confidence
   (observed-consistently / observed-once / inferred), and the LAL base item it
   layers over.
3. **Overlay protocol line** — every overlay begins with the same header:
   "FIRM OVERLAY — preference layer. Apply these preferences first; the LAL
   base library remains available and authoritative for anything not covered
   here. Never delete the base."
4. **Register the folder** — record the overlay folder path in the Firm
   Profile so every skill can find it.

## Phase 4 — Report and confirm

Produce the **Adaptation Report**: what was scanned, what was learned, every
overlay written and where, confidence levels, and the confirmation list —
items marked inferred or observed-once that the attorney should confirm or
strike. Nothing observed-once becomes a firm default without confirmation.

## Re-running

Re-run quarterly or after the firm's templates change. Re-runs version the
overlays (v2, v3) and show a diff of what changed; they never silently rewrite.
Because overlays live in the firm's storage, suite updates never touch them.

## When an overlay is not enough

A preference fits an overlay. A change to what a skill actually DOES — its
steps, gates, or outputs — does not. Route those to `lal-customize`, which
creates a firm-prefixed derivative skill instead of altering the shipped one.

## What this skill does NOT do

- Never writes inside an installed skill folder (read-only by design)
- Never replaces, edits, or deletes any LAL base reference or clause library
- Never copies client PII into an overlay — patterns only, de-identified
- Never adopts a firm pattern that conflicts with a legal-compliance rule
  without an attorney flag
- Never edits the firm's own matter files — overlays are new files in the
  overlay folder only
