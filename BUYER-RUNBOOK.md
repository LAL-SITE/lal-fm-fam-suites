# LAL Suite Install — Buyer Runbook

**Audience:** the buying firm's Claude admin (Team or Enterprise plan) and the
attorney running setup. **Time budget: under 30 minutes.** No zip files, no
per-skill uploads, no command line.

---

## What you received from Legal Authority Lab

A **private GitHub repository** containing Core Foundation plus the suites your
firm purchased, with your firm's identity already baked in (firm name,
attorneys, bar numbers, systems). LAL has granted your firm's GitHub account
read access to it.

## Part 1 — Admin: connect the marketplace (one time, ~10 min)

Prerequisites (both in **Admin settings → Capabilities**):

- **Code execution / Skills** — enabled
- **Cowork / Plugins** — enabled

Steps:

1. Go to **Admin settings → Plugins** (on some plans this appears under
   Cowork or Capabilities → Plugins).
2. Choose **Add marketplace** and connect the private GitHub repository LAL
   provisioned for your firm (you'll authenticate with the GitHub account LAL
   granted access to).
3. Once the marketplace syncs, you will see one plugin per purchased suite
   (e.g. *lal-core-foundation*, *lal-financial-discovery-core*).
4. For each plugin, set the org preference:
   - **lal-core-foundation → Required** (everything depends on it)
   - each purchased suite → **Installed by default** (or Required)
5. Done. Every seat in your org now has the skills, bundled reference files
   included. New hires get them automatically.

> If a plugin shows an error after sync, don't troubleshoot zips or files —
> screenshot the error and send it to LAL support. The repo is the single
> source of truth; LAL fixes it there and your marketplace re-syncs.

## Part 2 — Attorney or admin: run the installer (~15 min)

In a new Claude conversation (chat or Cowork):

1. Say: **"Run the LAL installer."**
2. The `lal-installer` skill will:
   - verify the purchased plugins are present,
   - build your **Firm Profile** (or read the one LAL onboarding created) —
     it lives in *your* storage, not inside the skills,
   - initialize the matter **command center**,
   - run one real matter through a primary skill end-to-end as verification,
   - hand you an **Install Report** with any gaps.
3. Download the **reference library** (see Ongoing below) into your document
   storage before or right after the installer runs — the installer records
   its location in the Firm Profile.
4. Optional but recommended once your document storage is connected:
   **"Run the firm adaptation"** — reads your templates and recent matters
   (read-only) and teaches the skills your formats, naming, and clause
   preferences via overlay files in your storage.

## Ongoing

- **Updates:** LAL pushes new versions to your repo; your marketplace
  re-syncs and every seat updates. Nothing to reinstall.
- **Changing a skill:** never edit a shipped skill. Say **"customize the
  [name] skill"** — `lal-customize` creates *your firm's* version under your
  prefix (e.g. `bj-lal-drafting-core`) so LAL updates never overwrite your
  changes.
- **New attorney / new systems:** re-run the installer; if a baked value
  changed (firm name, attorney roster), also tell LAL so the repo gets
  updated.
- **Reference library:** your purchase includes read access to the private
  `lal-reference-library` GitHub repository (~780 MB: the neutralized master
  guide, ~1,700 cleaned example documents, and the cleaned templates/forms
  library). Download it once (green **Code** button → **Download ZIP**, or
  clone with GitHub Desktop) into your firm's document storage — e.g. a
  `LAL REFERENCE LIBRARY` folder — and `lal-installer` will register its
  location in your Firm Profile so every skill can pull exemplars and
  templates from it. Re-download or pull when LAL announces corpus updates.
- **Caselaw** is separate from the reference library: it always flows through
  the authorized caselaw repository with verification warnings; the skills
  never cite from memory or the open internet.

## Troubleshooting quick table

| Symptom | Fix |
|---|---|
| Plugins not visible to staff | Admin: plugin preference not set to Installed by default/Required |
| Marketplace won't add | Confirm the GitHub account has access to the private repo; repo must stay **private** |
| A skill won't upload as an org skill | Don't upload skills one-by-one — use the marketplace path above |
| Skill fires but doesn't know the firm | Run `lal-installer` — the Firm Profile is missing or incomplete |
| Output format looks generic | Run `lal-firm-adaptation` after connecting storage |
