# Legal Authority Lab — Core Foundation Suite

**Version 1.0.0** · Florida family law · Ships free with every Legal Authority Lab suite

Core Foundation is the shared operating layer every other Legal Authority Lab suite is built on. It handles file access, matter state, house style, correspondence, authority discipline, help, file organization, judicial procedure, and legal ethics. Purchased suites — Discovery, Drafting, Mediation, GAL and the rest — assume Core is installed and write to it.

---

## Install

This suite installs through the firm's **org-managed plugin marketplace** — the
private GitHub repository Legal Authority Lab provisions for your firm.

1. Your Claude admin: **Admin settings → Cowork/Plugins → Add marketplace**,
   pointing at your firm's private LAL repository on GitHub.
2. Set the purchased plugins to **Installed by default** (or **Required**).
3. Every seat in the org receives the skills, references included. No zip
   uploads, no per-skill installs.

See `BUYER-RUNBOOK.md` at the repository root for the full walkthrough.
Firm identity is pre-baked into this repository by LAL; anything remaining is
handled at runtime by `lal-installer` and the Firm Profile.

---

## What's included

Ten skills. Every reference file each skill reads ships inside that skill's own `references/` folder — nothing is fetched from a server at runtime, with one deliberate exception noted below.

| Skill | What it does |
|---|---|
| `lal-file-connector` | Storage-agnostic file access. Detects and binds one provider at install: conversation uploads, a local folder, SharePoint, OneDrive, Google Drive, Dropbox, or Box. **Cloud storage is not required.** Every other skill reaches files through this one, so no other skill names a provider. |
| `lal-start-case` | First-touch scan of a matter file. Infers which stages are already complete from the documents present, then births the command center. A matter joined mid-stream does not lose its history. |
| `lal-command-center` | The live matter record: scope, position, deadlines, an append-only lifecycle ledger, and attorney flags. Every suite writes here. Deadlines record *how* a date was computed, not just the date. |
| `lal-brand-kit` | Your firm's voice and document standards, populated from the intake form. Choose a voice archetype, supply your always-say and never-say phrases, colours, fonts, signature, and calls to action. Governs non-filing output only. |
| `lal-correspondence` | Four lanes — client, opposing counsel, bench, third party — over nine harvested content specifications. Selects the lane and document type, applies the format standard, and enforces the approval gates. |
| `lal-caselaw-protocol` | Ambient. Caselaw comes from one place and never from model memory or an open-web search. Every citation carries a mandatory attorney-verification warning. |
| `lal-help` | The front door. Routes to the right skill, generates a how-to guide, or answers directly. It never tells you to go look something up. |
| `lal-file-organizer` | Whole-matter audit, rename, and re-folder. The naming convention is configurable — a default ships, and your existing house convention beats it. |
| `lal-judicial-procedures` | Ambient on any judge, magistrate, hearing officer, division, circuit, or county. It is a process, not a database: it never hard-codes what a judge requires. |
| `lal-florida-ethics` | Ambient on ethics-adjacent language. Seven-part assessment, attorney-approval gates, and an explicit, deliberate statement of what it does not cover. |

Plus a shared **conventions block**, bundled into every skill's `references/conventions.md`: environment-flexible, identity over lanes, just-run-it, read-files-first, transcripts-preferred, and command-center writes.

---

## Live network dependencies — stated plainly

Almost everything in Core runs offline. Two things do not, and you should know which:

1. **`lal-judicial-procedures` runs live web searches, always.** Judges reassign, retire, and change their procedures constantly, so a cached answer is a wrong answer. It searches official Florida sources — `flcourts.gov`, circuit court sites, `floridabar.org`, `leg.state.fl.us`. Its bundled reference files are starting points to verify, never data to rely on. It also flags any video-hearing detail for judicial-assistant confirmation within 48 hours regardless of where the detail came from.

2. **`lal-caselaw-protocol` reads one public repository** — the Legal Authority Lab Florida family law authority library. This is the single authorized exception to the suite's otherwise-hermetic design, and it is deliberately **not** configurable. Every deployment reads the same library so that an unverified citation cannot enter one firm's work and go uncaught everywhere else.

Nothing else in Core reaches the network.

---

## The caselaw rule

Read this before anyone uses the product.

Caselaw comes only from the authority library, or from material a licensed attorney supplies and personally vouches for. **Never from model memory. Never from an open-web search.** Every citation the suite produces carries an attorney-verification warning, and that warning is not decorative — verifying authority is a duty that cannot be delegated to software.

The reason is on the record. Three fabricated paternity authorities once propagated across three separate internal files at a firm before anyone caught them. The protocol exists so that cannot recur.

Statutes, rules, forms, and secondary materials are **not** restricted in the same way — the rule is specific to caselaw.

---

## Tokens

Two classes, two behaviours, both written in curly braces.

**Install-time** — the installer substitutes these once per firm:

```
{{FIRM_NAME}}  {{ATTORNEY_NAME}}  {{BAR_NO}}  {{FIRM_ADDRESS}}  {{FIRM_PHONE}}
{{FIRM_EMAIL}}  {{PM_SYSTEM}}  {{DMS}}  {{RESEARCH_PROVIDER}}  {{UPLOAD_PORTAL}}
{{PAYMENT_PROCESSOR}}  {{ESIGN_TOOL}}  {{CLIENT_UPLOAD_TOOL}}  {{VIDEO_TOOL}}
{{ROLE_DRAFTER}}  {{ROLE_REVIEWER}}  {{ROLE_APPROVER}}  {{ROLE_INTAKE}}
```

Plus brand tokens documented in `skills/lal-brand-kit/references/intake-fields.md`.

**Draft-time** — an attorney fills these per matter:

```
{{CLIENT_NAME}}  {{CASE_NO}}  {{JUDGE}}  {{OPPOSING_COUNSEL}}  {{COUNTY}}
{{CIRCUIT}}  {{DIVISION}}  {{DATE}}  {{AMOUNT}}  {{THIRD_PARTY_NAME}}
```

**Roles are tokens, not job titles.** Your firm's structure is not the structure of the firm this content was harvested from, so the suite never says "the paralegal does X" — it says `{{ROLE_DRAFTER}}`. Map the four role tokens to your own people at install; one person may hold several roles, and an approving attorney self-approves.

**`[CONFIRM LOCALLY: what, with whom]`** is the third marker. It appears wherever practice varies by circuit, county, division, judge, or clerk. Each one names what to confirm and who to confirm it with, so it reads as an instruction rather than a hole. `lal-judicial-procedures` uses it heavily and correctly.

---

## What Core does not do

An honest boundary is a feature. `lal-florida-ethics` recognizes these areas, states that Core carries no workflow for them, and stops to the approving attorney rather than improvising:

- trust accounting and IOTA
- conflicts-of-interest screening (Core can confirm a check was run and documented; it will not run, simulate, or infer one)
- withdrawal and termination ethics
- limited-scope representation ethics — the *procedure* is covered elsewhere, the *ethics* is not, and the presence of one does not imply the other
- attorney advertising compliance

`skills/lal-florida-ethics/references/coverage-and-limits.md` carries the full statement.

**No letterhead format master ships.** Correspondence carries the layout specification in prose and you apply your own letterhead. A shipped master would be another firm's visual identity wearing your name.

**`lal-correspondence` labels provenance.** Some sub-types were harvested from real matters; others come from untested templates. The skill tells you which before it drafts, because a template that has never been sent is not the same thing as a letter that has.

**Disengagement has an attorney-supply gate.** The Rule 4-1.16 compliance language is deliberately empty and the skill hard-stops rather than sending without it. Supply it once, in writing, reviewed by an attorney — it is the one gate the suite's self-approval convention cannot clear.

---

## Suite interoperation

Core degrades, it does not error. Where a skill would use a suite you have not purchased, it says so and continues:

> if the Discovery suite is installed, log the deficiency to the tracker; if not, note it in the memo

A missing suite never causes a failure and never causes a silent omission.

---

## One open item flagged for resolution

**Packager token gate.** This suite writes draft-time tokens in curly braces per a deliberate ruling aligning with the neutralized master corpus. The packaging skill's token gate still specifies bracket-style draft-time tokens and will flag this suite as non-compliant until that gate is amended.

Note the consequence of that ruling, which is already handled here but matters for any other suite: because both token classes use curly braces, brace style no longer indicates which is which. The installer must substitute against an explicit allow-list of install-time tokens and leave everything else alone. Pattern-matching on `{{ }}` would write one firm-level value into `{{CLIENT_NAME}}` across every matter the firm ever opens.

*(Resolved: the authority repository name is `florida-family-law-research-suite`, confirmed and applied throughout.)*

---

## Support

Legal Authority Lab. Updates ship as new versions in this repository; see the changelog for whether a reinstall is required.

Core Foundation is licensed, not sold. See `LICENSE` — in particular Section 5, which is where professional responsibility lives.
