---
name: lal-adversarial-verification-rules
description: "Ambient rule: fires when a skill enters data (names, SSNs, dollar figures, dates) into a filing, affidavit, discovery response, or client deliverable — requires independent second-pass verification."
---

# Feinstein & Mendez, PA Adversarial Data Verification (Ambient)

## When to use this skill (full trigger reference)

AMBIENT FIRM-WIDE RULE for Feinstein & Mendez, PA. Fires automatically whenever ANY skill or task produces, extracts, or enters data-bearing content — party names, addresses, phone/email/contact profiles, SSNs, account numbers, dollar figures or calculations, dates, case numbers, docket data — that is destined for an e-filing portal, a financial affidavit or worksheet, a discovery response, a GAL report, or any client-facing or attorney-facing deliverable that will be relied on. Requires an INDEPENDENT, blind second-pass verification — a separate agent that re-derives the data from source without seeing the first draft — before that content is presented as done. This is additional to, not a replacement for, existing QC gates (`lal-prefiling-qc`, `lal-disco-qc`, `lal-gal-qc`, and similar), which remain mandatory. Triggers on any data extraction or data entry task, any e-filing/e-portal prep, any financial affidavit, worksheet, or chart with dollar figures, any pull of a {{PM_SYSTEM}} or {{DMS}} contact/party record used downstream, any GAL report, and any discovery response or certificate of compliance.

These rules apply to every task in every Feinstein & Mendez, PA session that touches data-bearing content. They are non-negotiable and require no prompt from the user.

## Why this rule exists

Self-review catches formatting problems and forgotten sections. It does not reliably catch a model inventing a person. Firm testing across live matter work found that adding an independent second pass — a separate reviewer trying to disprove the data rather than the same pass checking its own work — caught an error roughly 90% of the time, and caught a **fabrication** (an invented SSN, an invented address, a completely fabricated contact profile for a real party) something like 30–40% of the time, including one incident where a draft e-filing had three of four parties, and all of their contact data, as total fabrications. Every existing QC gate in this skill library — `lal-prefiling-qc`, `lal-disco-qc`, `lal-gal-qc`, and the rest — is a single pass checking the draft it (or a teammate in the same session) just produced. That is valuable and stays mandatory. It is not the same thing as an independent check, and it will not catch everything the independent check catches. This rule adds the independent layer as a firm-wide non-negotiable for data-bearing output. It is not a "nice to have."

## Rule 1 — What triggers the independent pass

Any of the following requires an independent adversarial verification pass before the output is presented as ready, filed, submitted, or sent:

1. **E-filing / e-portal data entry.** Every party name, address, phone, email, and identifying number (SSN, case number, docket number) keyed into a state e-filing platform or prepared for e-filing.
2. **Financial affidavits and any dollar-figure output.** Financial Affidavits, child support worksheets, ED charts, income analyses, deep-scan findings, equalization/mediation numbers — anything where a dollar figure, account number, or calculation will be relied on.
3. **Any {{PM_SYSTEM}}- or {{DMS}}-sourced contact or party record used downstream.** Before a pulled record (matter lookup, contact lookup, dossier, snapshot) is used in a filing, discovery response, or client communication, the party's name, address, and contact details must be independently cross-checked against the underlying source ({{DMS}} intake, the case caption, a prior filing) — not just passed through because the tool returned it. This category is the most common gap: most firm installations have a matter/contact lookup skill with no cross-check requirement at all, and it is the exact failure mode behind real-world hallucination incidents.
4. **GAL reports and any document asserting facts about a party or a child.** Names, dates of birth, addresses, and relationship facts.
5. **Discovery responses and certificates of compliance.** Every represented production item, date, and figure.

If a task doesn't touch data-bearing content — pure formatting, a status question, a scheduling question — this rule does not fire.

## Rule 2 — What "independent" means

An independent pass is NOT: the same drafting pass reviewing its own checklist, a second person reading the same document with the same context, or a QC gate that "traces" facts back to a source document within the same continuous session where the draft was produced. Those are valuable but they inherit whatever the first pass already believed. A model that fabricated a name will also, with high probability, "confirm" that name when checking its own work, because the fabrication is now sitting in its context as if it were established fact.

An independent pass IS: a **separate agent invocation** (via the Agent tool, or an equivalent fresh subagent call) that:

- Is given the **source documents only** — the matter's {{DMS}} file, the uploaded PDFs, the {{PM_SYSTEM}} record, the intake form — and NOT the draft or extraction the first pass produced.
- Is asked to **independently extract or re-derive** the specific data-bearing facts at issue (the party list and their contact details; the dollar figures and their sources; the dates and case numbers) from those source documents, from scratch.
- Returns its own extraction, which is then **diffed** against the first pass's draft — by a person or by a third comparison step, not by the first pass itself.

Any mismatch is treated as a fabrication until proven otherwise — not smoothed over, not resolved by picking whichever value "sounds right."

**Where the source documents come from.** This skill never locates files itself and never
invents a path, folder, or connector. Like every other skill in this suite, it reaches matter
files only through `lal-file-connector` — Operation 1 to resolve the matter root, Operation 3
to read a document. The independent-pass agent is handed that same resolved root (or the
specific documents Operation 3 already returned) and re-reads from there. Two things this is
**not**: it is never a re-read of anything cached in the first pass's own conversation context
(that is not independent — see above), and it is never pulled from this firm's GitHub suite
repository. No client data — no party name, SSN, dollar figure, or matter document — is ever
stored in that repository or any other LAL marketplace repo; those repos ship skill code
only. Source documents live exclusively in the firm's own bound storage.

## Rule 3 — Findings and blocking

Report independent-verification findings in the same severity language the firm's QC gates already use:

- **CRITICAL** — the two passes produced different values for a party name, address, contact detail, SSN, account number, or dollar figure; or the independent pass could not find support in the source documents for something the draft asserted as fact. The document does not advance — not to the e-portal, not to the client, not to the attorney for sign-off — until this is resolved against the actual source.
- **SIGNIFICANT** — the independent pass flags something as unclear or under-sourced that the draft treated as settled, without an outright conflict.

State plainly which pass found what. Never report "verified" without saying what the independent pass actually checked and against what source.

## Rule 4 — Relationship to existing QC gates

This rule does not replace `lal-prefiling-qc`, `lal-disco-qc`, `lal-gal-qc`, `lal-fa-crosscheck`, or any other checklist-style QC gate already in the skill library. Those remain mandatory and run as before. This rule is an additional, independent layer that runs alongside or after them for data-bearing content, and it is the one that catches what a self-review checklist structurally cannot: a fact the drafting pass itself invented.

Where a QC gate already includes a step that looks like verification (for example `lal-prefiling-qc` Screen 1's "every fact must trace to the file"), that step still must be satisfied — but satisfying it inside the same session does not substitute for the independent pass this rule requires for the categories in Rule 1.

## Rule 5 — Nothing changes about sign-off

This rule adds a verification step. It does not change who may clear a document for filing or service. Only an attorney signs off. Independent verification passing is a precondition to reaching the attorney, not a substitute for the attorney's review.
