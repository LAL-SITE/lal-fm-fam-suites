# Core Foundation — Legal Authority Lab

**Suite:** Core Foundation  
**List price:** free with every purchase  
**Version:** 1.2.0  
**Publisher:** Legal Authority Lab — legalauthoritylab.com

Foundation layer every suite depends on: installer, file connector, start-case, command center, brand kit, correspondence, caselaw protocol, help, file organizer, judicial procedures, Florida ethics.

## Skills included

Eighteen skills. Every reference file a skill reads ships bundled inside that skill's own
`references/` folder — nothing is fetched at runtime except the public caselaw authority
library and the live judicial-procedure searches.

**Foundation**

- **`lal-installer`** — Buyer-side install. Reads the firm profile, substitutes the
  install-time token allow-list across every installed skill, births the command center,
  and verifies on one live matter. Re-runnable whenever the profile changes.
- **`lal-firm-adaptation`** — Post-install adaptation. Overlays a firm's own language and
  house conventions onto the shipped skills without editing substance.
- **`lal-file-connector`** — The storage abstraction for the whole product line. Detects and
  binds one provider at install — conversation uploads, a local folder, SharePoint, OneDrive,
  Google Drive, Dropbox or Box. Cloud storage is not required. No other skill names a provider.
- **`lal-start-case`** — First touch on a matter. Scans the file, infers from the documents
  present what has already happened, and births the command center with that state.
- **`lal-command-center`** — The single per-matter state file every suite reads before it
  works and writes to when it finishes: scope, position, deadlines, an append-only lifecycle
  ledger, and attorney flags.

**Practice layer**

- **`lal-correspondence`** — Four lanes — client, opposing counsel, bench, third party — over
  nine harvested content specifications, with per-entry provenance labelling and a hard stop
  on disengagement until the approving attorney supplies the Rule 4-1.16 language.
- **`lal-brand-kit`** — Brand and document standard for all non-filing output, populated from
  the intake form: voice archetype, always-say and never-say phrases, colours, type,
  signature and calls to action.
- **`lal-file-organizer`** — Whole-matter audit, rename and re-folder. The naming convention
  is configurable on four axes; a default ships and an existing house convention beats it.
- **`lal-judicial-procedures`** — Ambient. Fires on any judge, magistrate, hearing officer,
  division, circuit or county. A process, not a database — it never hard-codes what a judge
  requires, and it always searches live.
- **`lal-florida-ethics`** — Ambient. Seven-part written ethics assessment with an explicit
  risk level, attorney-approval gates, and a plainly stated boundary around the five domains
  it deliberately does not cover.
- **`lal-help`** — The front door. Routes to the right installed skill, generates a
  step-by-step how-to, or answers directly. Never tells anyone to go look it up.

**Ambient standing rules**

- **`lal-caselaw-protocol`** — Caselaw comes only from the authority library or material the
  attorney vouches for. Never model memory, never open-web search. Every citation carries a
  verification warning.
- **`lal-integrity-rules`** — Never invent a template or reference that cannot be found;
  check for an existing capability before declaring one unavailable.
- **`lal-filing-status-rules`** — Folder location is the evidence of status. A draft is a
  draft; its existence is never evidence of filing or service.
- **`lal-draft-versioning`** — Three independently versioned working tiers: attorney review,
  client review, final.
- **`lal-document-intake-rules`** — No feedback on a scanned document that has not been
  OCR-verified.
- **`lal-exemplar-library`** — When output is rejected or a template cannot be found, search
  the firm's own library for a real exemplar and retry with evidence rather than stopping.
- **`lal-adversarial-verification-rules`** — Data-bearing output (party data, dollar figures,
  dates, case numbers) headed to a filing, affidavit, discovery response, GAL report, or
  client deliverable gets an independent, blind second-pass re-derivation from source before
  it is presented as done — supplements, never replaces, the existing QC gates.

## Requirements

- **Core Foundation** (ships free with every purchase) must be installed first.
- Install-time firm identity is applied by the LAL install process, which substitutes
  the `{{TOKEN}}` placeholders: {{FIRM_NAME}}, {{ATTORNEY_NAME}}, {{BAR_NO}}, {{FIRM_ADDRESS}},
  {{FIRM_PHONE}}, {{FIRM_EMAIL}}, {{FIRM_WEBSITE}}, {{PM_SYSTEM}}, {{DMS}}, {{RESEARCH_PROVIDER}},
  {{UPLOAD_PORTAL}}, {{ROLE_DRAFTER}}, {{ROLE_REVIEWER}}, {{ROLE_APPROVER}}, {{ROLE_INTAKE}}.
- Matter-level tokens — {{CLIENT_NAME}}, {{CASE_NO}}, {{JUDGE}}, {{OPPOSING_COUNSEL}},
  {{COUNTY}}, {{CIRCUIT}}, {{DIVISION}}, {{DATE}}, {{AMOUNT}} — are filled by the attorney
  at draft time, never programmatically. Both classes use curly braces, so brace style
  does not indicate which is which: the installer substitutes only the install-time
  allow-list above and leaves everything else alone.
- `[CONFIRM LOCALLY: what, with whom]` markers are instructions to a human, wherever
  practice varies by circuit, county, division, judge or clerk. Nothing resolves them
  automatically.

## Install

1. Install through the firm's org-managed plugin marketplace — the private
   GitHub repository LAL provisions for your firm (see `BUYER-RUNBOOK.md` at
   the repository root).
2. Firm identity is pre-baked by LAL; run `lal-installer` to build the Firm Profile and verify.
3. Verify with a live matter before production use.

## Cross-suite behavior

Missing suites degrade gracefully: if a referenced suite is not installed, the skill
notes the limitation and continues with its own scope. It never errors and never
silently omits.
