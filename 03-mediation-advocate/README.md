# Mediation & Settlement — Advocate — Legal Authority Lab

**Suite:** Mediation & Settlement — Advocate  
**List price:** $4,000  
**Version:** 1.0.1  
**Publisher:** Legal Authority Lab — legalauthoritylab.com

Advocate-side mediation: prep engine (ED chart, scenarios, proposals, mediator summary), live session command center, MSA drafting, parenting plan.

## Skills included

- `lal-mediation-prep`
- `lal-mediation-advocate`
- `lal-msa-drafter`
- `lal-parenting-plan-drafter`

## Requirements

- **Core Foundation** (ships free with every purchase) must be installed first.
- Install-time firm identity is applied by the LAL install process, which substitutes
  the `{{TOKEN}}` placeholders: {{FIRM_NAME}}, {{ATTORNEY_NAME}}, {{BAR_NO}}, {{FIRM_ADDRESS}},
  {{FIRM_PHONE}}, {{FIRM_EMAIL}}, {{FIRM_WEBSITE}}, {{PM_SYSTEM}}, {{DMS}}, {{RESEARCH_PROVIDER}},
  {{UPLOAD_PORTAL}}, {{ROLE_DRAFTER}}, {{ROLE_REVIEWER}}, {{ROLE_APPROVER}}, {{ROLE_INTAKE}}.
- Bracket placeholders like [CLIENT NAME], [CASE NO.], [JUDGE] are matter-level and are
  filled by the attorney at draft time — never programmatically.

## Install

1. Install via plugin file or `/plugin marketplace add` from the suite repository (Git add,
   not direct URL — relative paths only resolve via Git).
2. Run the LAL install process to substitute firm tokens from the firm profile.
3. Verify with a live matter before production use.

## Known gaps / roadmap

- lal-mediation-prep is the Financial Discovery add-on: pulls ED chart/equalizer, CS worksheet, and income analysis from Discovery Core/Advanced when installed; manual-entry fallback otherwise. Position it as the add-on SKU for Advanced Discovery buyers.
- lal-mediation-advocate (live session) and lal-mediator-session (neutral, Suite 04) must never share state — advocate/neutral firewall.

## Cross-suite behavior

Missing suites degrade gracefully: if a referenced suite is not installed, the skill
notes the limitation and continues with its own scope. It never errors and never
silently omits.


## Changelog

### 1.0.1 (08/06/2026)
- Fixed: `lal-msa-drafter`'s Output Steps referenced `scripts/office/validate.py`, a script that
  was never bundled with the skill. Replaced with an explicit manual conformance check (font,
  margins, spacing, justification, footer, exhibit table DXA widths) so the step no longer points
  at a missing file. No script was fabricated to close this gap, per packager policy.
