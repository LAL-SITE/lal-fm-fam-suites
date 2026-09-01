---
name: lal-customize
description: "Fork-on-customize engine. Use when a firm wants to change, extend, or override how a shipped LAL skill behaves - never edits the shipped skill; creates a firm-prefixed derivative skill instead."
---

# LAL Customize — Fork, Never Edit

## When to use this skill (full trigger reference)

Use whenever anyone at the firm asks to change what a shipped LAL skill does: "change how the skill works," "our version should also...", "edit the skill," "the skill should skip that step," "add a step to the drafting skill," "make our own version of this skill," "override the QC gate order," "customize the correspondence skill," or any request that goes beyond a preference (preferences are overlays — route those to lal-firm-adaptation). Also fires when a suite update lands and the firm has derivative skills that need review against the update.

## The rule

Shipped LAL skills are read-only and are replaced wholesale by suite updates.
**A firm never edits a shipped skill. A customization becomes a NEW skill,
named with the firm's prefix** — e.g. the firm "BJ" customizing `lal-drafting-core`
produces **`bj-lal-drafting-core`** (lowercase, hyphenated; the firm's short
code comes from the Firm Profile `meta.firm_short`).

This guarantees: (1) LAL suite updates never clobber the firm's work; (2) the
firm's version and the LAL base can be compared at any time; (3) LAL support
can always reason about what the base does.

## Decision ladder — smallest change wins

1. **It's a preference** (format, naming, preferred clause, voice, default
   model): NOT a fork. Route to `lal-firm-adaptation` — it belongs in the
   skill's overlay file in the firm's storage.
2. **It's a behavior change** (different steps, added/removed gates, different
   outputs, different routing): fork per the process below.
3. **It's a missing capability** (something no LAL skill does): a brand-new
   firm skill, prefixed the same way (`bj-<purpose>`), built with the same
   structure conventions.

## The fork process

1. **Read the base.** Load the shipped skill's SKILL.md and references.
2. **Draft the derivative.** Create `<firm_short>-lal-<base-name>/SKILL.md`:
   - frontmatter `name` = the derivative name; `description` ≤200 characters,
     written so it wins routing for this firm's phrasing of the task;
   - body opens with a **Fork header**: base skill name, base plugin version
     forked from, date, and a one-line reason;
   - then the full adapted instructions (copy the base body and change what
     the firm wants changed — never a diff that requires reading the base);
   - copy any base reference files the derivative still needs into its own
     `references/` (the derivative must be self-contained).
3. **De-conflict routing.** The derivative's trigger section states: "This
   firm's version of <base>. Prefer this skill over <base> for this firm's
   work." If the base skill would still auto-fire ambiently, note in the
   derivative which base steps are superseded.
4. **Deliver it** — two accepted routes, in order of preference:
   - **Firm repo route (org-wide):** package the derivative folder into the
     firm's private marketplace repo under the `90-firm-custom` plugin
     (create the plugin folder with its `.claude-plugin/plugin.json` on first
     use). The firm pushes with GitHub Desktop or sends it to LAL to commit;
     the org marketplace re-syncs and every seat gets it.
   - **Org-skill route (quick):** zip the derivative skill folder as a
     `.skill` file and give it to the firm's Claude admin to upload under
     Organization settings → Capabilities → Skills. Fine for one skill;
     migrate it into the repo at the next update.
5. **Log it.** Record the fork in the Firm Profile (`install.open_items` or a
   `customizations:` list): derivative name, base name, base version, route
   used. The command center gets a note on the matter that prompted it.

## Attorney approval

A fork that changes a compliance gate, QC screen, ethics rule, or anything the
base marks as a hard stop requires the approving attorney's sign-off before
delivery. Identity-over-lanes still applies: an attorney running this skill
self-approves.

## When a suite update lands

Suite updates replace base skills, never derivatives. After any update, run
this skill in review mode: for each derivative in the Firm Profile's
customizations list, compare its recorded base version against the updated
base's version and changelog, and flag derivatives whose base changed
materially. The firm decides: keep the fork as-is, refresh it from the new
base, or retire it.

## What this skill does NOT do

- Never edits a shipped LAL skill, its references, or its plugin
- Never deletes the base skill or asks the admin to disable it (the firm may
  choose to; the fork must work either way)
- Never copies client PII into a derivative — same de-identification rule as
  overlays
- Never forks lal-caselaw-protocol, lal-florida-ethics, lal-prefiling-qc, or
  the ambient integrity rules in a way that weakens them — additions yes,
  removals require LAL and attorney sign-off both
