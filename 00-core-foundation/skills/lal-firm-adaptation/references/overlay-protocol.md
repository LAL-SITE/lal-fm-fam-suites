# Firm Overlay Protocol

Every `firm-overlay.md` written by lal-firm-adaptation follows this contract.

## Header (mandatory, verbatim)

> FIRM OVERLAY — preference layer. Apply these preferences first; the LAL base
> library remains available and authoritative for anything not covered here.
> Never delete the base.

## Entry format

Each entry:

- **Preference:** what the firm does (one line)
- **Layers over:** the LAL base item it takes precedence for
- **Example:** de-identified, tokenized
- **Confidence:** observed-consistently | observed-once | inferred
- **Status:** confirmed | pending-attorney-confirmation

## Precedence rules

1. Legal-compliance rules (approved forms, mandatory language, court format) beat overlays. Conflicts get an attorney flag.
2. Confirmed overlay entries beat LAL defaults for style, format, naming, and clause preference.
3. LAL base governs everything an overlay does not cover.
4. Draft-time tokens — `{{CLIENT_NAME}}`, `{{CASE_NO}}`, `{{JUDGE}}` and the rest of the
   matter-level set — are untouched by overlays, as is every `[CONFIRM LOCALLY: ...]`
   marker. Both token classes use curly braces, so match against the allow-list rather
   than the brace style.

## Update safety

Suite updates never ship a `firm-overlay.md`. Installers and updaters must not
delete existing overlay files. Re-runs of lal-firm-adaptation version overlays
and diff changes; they never silently rewrite.
