---
name: lal-deep-scan
description: "Deep scan for undisclosed accounts and hidden financial activity. Use after statements are in the file to trace transfers and find accounts missing from a party's FA or disclosure."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA deep scan for undisclosed accounts and hidden financial activity. Use after bank, brokerage, and credit card statements are in the file — typically alongside or after the Stage 4 FA cross-check. Triggers on: "run the deep scan," "scan for undisclosed accounts," "are there hidden accounts," "where is the money going," "check for missing accounts," "trace the transfers," "missing statement periods," "what accounts do we not have," or any request to detect accounts, transfers, or income streams that do not appear on a party's Financial Affidavit or disclosure. Runs on either party. Produces the Deep Scan Findings Chart and a discovery follow-up list. Findings are leads for discovery — never accusations. Always assign to {{ROLE_DRAFTER}}; output goes to {{ROLE_REVIEWER}}, then {{ROLE_APPROVER}}.


## Feinstein & Mendez, PA Firm-Wide Conventions (apply to every run of this skill)

These six conventions govern all Feinstein & Mendez, PA skills and override any narrower instruction
below that conflicts with them.

1. **Environment-flexible.** Complete the task in the environment you are already in.
   If a different environment would be materially better, say so in one line and keep
   working. Never block, never redirect.
2. **Identity over lanes.** Staff assignments are defaults, not gates. Attorneys
   self-approve — if the person running this skill is {{ROLE_APPROVER}}, they are the
   approving attorney.
3. **Just run it.** Prerequisite stages are soft checks, never hard gates.
4. **Read files first.** Search the entire matter file before declaring anything missing.
5. **Transcripts preferred, never required.**
6. **Write to the command center.** Every completion, deadline, and attorney flag is
   written to the matter's command center before the run ends.

---

# Feinstein & Mendez, PA Deep Scan — Undisclosed Account & Hidden Activity Detection

## Purpose

Systematically mine the produced financial documents for evidence of accounts,
assets, income streams, and liabilities that were NOT disclosed. The FA cross-check
(Stage 4) verifies what was disclosed; the deep scan hunts for what was not.
Everything found is a **discovery lead** stated in neutral, factual language — the
skill never concludes concealment; the attorney decides what a finding means.

## Inputs

- All produced statements for the target party: checking, savings, brokerage,
  retirement, credit cards, loans (DISCO folders)
- The party's Financial Affidavit and Certificate of Compliance
- The disco tracker (what was produced vs. what was requested)
- Stage 4 cross-check chart if it exists (do not duplicate its findings — extend them)

## The Six Sweeps

Run all six, in order, across every statement month produced:

**1. Transfer destination sweep.** Every outbound transfer, wire, or payment to an
account number, person, or entity that is not matched to a disclosed account. Log:
date, amount, description string, destination hint. Recurring destinations get one
row with the pattern summarized.

**2. Deposit origin sweep.** Every incoming deposit from an unmatched source:
employer names not on the FA, business entities, P2P transfers (Venmo, Zelle,
PayPal, Cash App), rental-pattern deposits, regular third-party deposits with no
identified source.

**3. Statement continuity sweep.** Missing statement periods per account (gaps in
the monthly sequence), accounts that appear mid-production with no opening history,
and accounts whose statements stop with a balance remaining — closing balances with
no visible destination.

**4. Cross-reference sweep.** Account numbers, loan numbers, and institution names
that appear anywhere in the produced documents (statement headers, transfer memos,
linked-account references, insurance and loan paperwork) but are not on the FA and
not in the production.

**5. Lifestyle consistency sweep.** Cash withdrawals disproportionate to stated cash
expenses; payments on debts not disclosed (minimum payments to unlisted cards);
payroll direct deposits absent for a claimed salaried employee; premium payments
suggesting undisclosed policies or assets (marine, aviation, jewelry riders).

**6. Business bleed sweep.** Business-entity transactions running through personal
accounts: deposits from entities, payments of personal expenses by a business,
transfers between personal and business accounts (flag for income-analysis handoff).

## Output — Deep Scan Findings Chart

Excel per lal-output-standards. One row per finding:

| # | Sweep | Party | Account/Source | Date(s) | Amount(s) | What the document shows | Why it matters | Suggested follow-up |

Follow-up column speaks discovery: "request statements for account ending 4412,"
"interrogatory re: recurring $2,000 Zelle transfers to [name]," "subpoena to
[institution]" — routed to lal-advanced-discovery when installed.

Below the chart, two required sections:
1. **Priority findings** — the attorney-attention shortlist, ranked
2. **Follow-up list** — every suggested discovery action, grouped by instrument type

## Hard Rules

- Neutral language only. "Statements show recurring transfers to an unidentified
  account" — never "he is hiding money."
- Every finding cites the exact document and page/line it came from.
- No caselaw. If legal significance needs authority, route to lal-legal-research
  under lal-caselaw-protocol.
- QC gate: run lal-disco-qc before the chart moves to {{ROLE_REVIEWER}}.
- Save to NOTES in the {{DMS}} matter folder via lal-file-connector; update the
  disco tracker and the command center; log time in {{PM_SYSTEM}}.
