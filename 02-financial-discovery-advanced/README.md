# Financial Discovery — Advanced — Legal Authority Lab

**Suite:** Financial Discovery — Advanced  
**List price:** $1,500 (upgrade only)  
**Version:** 1.0.0  
**Publisher:** Legal Authority Lab — legalauthoritylab.com

Advanced income analysis and contested discovery: interrogatories, RFPs, RFAs, subpoenas, motions to compel, CS worksheet.

## Skills included

- `lal-advanced-discovery`
- `lal-income-analysis`
- `lal-cs-worksheet`
- `lal-alimony-assessment`

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

## Cross-suite behavior

Missing suites degrade gracefully: if a referenced suite is not installed, the skill
notes the limitation and continues with its own scope. It never errors and never
silently omits.
