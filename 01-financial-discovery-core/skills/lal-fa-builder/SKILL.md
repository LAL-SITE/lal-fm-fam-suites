---
name: lal-fa-builder
description: "Builds a completed Florida Financial Affidavit (12.902(b) or (c)) from the FA intake and discovery documents. Use to draft or update an FA - selects the form, maps fields, audits deductions."
---

## When to use this skill (full trigger reference)

Feinstein & Mendez, PA Financial Affidavit Builder — builds a completed Florida Family Law Financial Affidavit (Form 12.902(b) or 12.902(c)) from the Feinstein & Mendez, PA FA Intake Questionnaire and/or uploaded discovery documents. Use immediately whenever a client has submitted the FA intake form via {{PM_SYSTEM}} or when discovery documents are uploaded and the FA needs to be drafted or updated. Triggers on: "FA Intake uploaded. Build the FA for [Name]", "build the financial affidavit", "draft the FA", "populate the FA from intake", "client completed the intake form", "update the FA with documents", or any request to produce a completed Financial Affidavit for filing. Automatically selects short form 12.902(b) or long form 12.902(c) based on income, maps every intake field to the correct FA line, calculates net income, audits deductions for double-counting, flags attorney items, and produces a fully populated Word document matching the Supreme Court approved form exactly.


## Feinstein & Mendez, PA Firm-Wide Conventions (apply to every run of this skill)

These six conventions govern all Feinstein & Mendez, PA skills and override any narrower instruction
below that conflicts with them.

1. **Environment-flexible.** Complete the task in the environment you are already in
   — chat, Desktop, or Cowork. If a different environment would be materially better,
   say so in one line and keep working. Never block, never redirect, never hand off
   instead of doing the work.
2. **Identity over lanes.** Staff assignments in this skill are defaults, not gates.
   Anyone may run any skill. **Attorneys self-approve** — if the person running this
   skill is {{ROLE_APPROVER}}, they *are* the approving attorney. Never tell an attorney to
   route their own work to an attorney for approval. Approval gates mean an approving-
   attorney action is recorded, not that the user must go find someone.
3. **Just run it.** Prerequisite stages are soft checks, never hard gates. Pause only
   for a physically necessary input, and ask for that specific item by name — never
   "complete Stage X first."
4. **Read files first.** Search the entire matter file — including misnamed and
   misfoldered documents — before declaring anything missing. If the file is
   disorganized, offer a file-organizer cleanup rather than reporting a gap.
5. **Transcripts preferred, never required.** A typed memo or rough notes always
   suffice as input.
6. **Write to the command center.** Every stage completion, deadline, lifecycle move,
   and attorney flag is written to the matter's command center before the run ends.

---

# SKILL: lal-fa-builder
## Feinstein & Mendez, PA Financial Affidavit Builder — Florida Supreme Court Forms 12.902(b) and 12.902(c)

**Version:** 1.0 | **Assigned To:** {{ROLE_APPROVER}} / Paralegal  
**Output:** One completed Financial Affidavit as a Word (.docx) file, formatted to match the Florida Supreme Court Approved Form exactly  
**Trigger:** Intake questionnaire submitted (FA_INTAKE.pdf from {{PM_SYSTEM}}) AND/OR discovery documents uploaded  

---

## SECTION 1 — PURPOSE AND SCOPE

This skill builds a completed Florida Family Law Financial Affidavit (Form 12.902(b) or 12.902(c)) from one or both of the following inputs:

1. **FA Intake Questionnaire** — the Feinstein & Mendez, PA client intake PDF (45 pages, {{PM_SYSTEM}}-generated)
2. **Discovery / Supporting Documents** — pay stubs, bank statements, tax returns, etc.

When only the intake form is available, Claude builds the FA from intake data and footnotes every estimated or calculated figure. When supporting documents are also uploaded, Claude cross-checks intake figures against the documents and updates the FA accordingly, footnoting any discrepancy.

**The output is always a fully populated Word document that mirrors the Supreme Court form field-by-field, line-by-line.** It is never a summary, never a memo, and never a partial draft. Every line of the form is addressed — either populated with a value or explicitly marked "N/A" or "0.00."

---

## SECTION 2 — FORM SELECTION: SHORT vs. LONG

Before populating any field, Claude must determine which form applies.

| Condition | Form |
|---|---|
| Gross annual income **under** $50,000 | Form 12.902(b) — Short Form |
| Gross annual income **$50,000 or above** | Form 12.902(c) — Long Form |
| Court order requires upgrade | Long Form regardless of income |
| Income unknown or unclear from intake | Build Long Form; flag for attorney |

**Income threshold calculation:** Total all income sources from intake before making the form selection. If total gross monthly income × 12 is under $50,000, use short form. When in doubt, build the long form. Never build the short form if income is ambiguous.

---

## SECTION 3 — INPUT PARSING PROTOCOL

### 3A — FA Intake Questionnaire Field Map

The intake questionnaire is organized in sections. Map each section to the FA form as follows:

**SECTION: Case & Personal Information (Pages 1–2)**
- First name, last name → Party name on caption
- Date of birth → FA header field
- Current residential address → FA header field
- How long at address → Attorney note (not on FA)
- Phone / email → Attorney note
- Marital status → Attorney note
- Role in case (Petitioner/Respondent) → Caption
- Children from prior relationship + child support order info → Section III deductions (child support paid)

**SECTION: Employment & Primary Employer Details (Pages 3–7)**
- Employer name, job title, address → Section I, Line 1 employer fields
- Employment type (FT/PT/Seasonal/Temp) → Attorney flag if non-FT
- Start date → Attorney note
- Pay type (Salary/Hourly/Commission/Salary+Commission) → drives Line 1 calculation method
- Hourly rate + hours/week → calculate monthly: (rate × hours × 52) ÷ 12
- Annual salary → divide by 12 for monthly
- Average monthly overtime → Line 1 or separate income line
- Bonuses (last 3 years) → average, add to Line 1 footnote
- Commissions (average monthly) → Line 1 or separate line
- Additional compensation (car allowance, per diem) → included in income with flag
- Overtime frequency (regularly/occasionally/no) → attorney flag if regularly expected

**Additional Employers (Pages 6–7):** Repeat for each employer. Each additional W-2 employer maps to a separate income line.

**SECTION: Additional Employment & Self-Employment (Pages 8–10)**
- Side income / freelance / gig work → Line 1 other income or self-employment line
- Payment method (1099/W-2/Cash) → attorney flag if cash
- Business ownership → Schedule C / self-employment section
  - Business name, type, ownership % → SE income section
  - Gross monthly revenue → note
  - Monthly ordinary/necessary expenses → deducted from gross
  - Net monthly income from business → Line 1 SE income
  - Owner salary from business → coordinate with W-2 to avoid double-count
  - Uses business account for personal expenses → RED FLAG, attorney flag required
  - CPA contact info → attorney note

**SECTION: All Income Sources (Pages 10–13)**
- Rental property (per property):
  - Address → rental income section
  - Gross monthly rental income → note
  - Monthly ordinary expenses → deduct
  - Net monthly rental income = gross − expenses → FA income line (Rule 12.902 requires NET)
- Disability / Social Security:
  - Monthly SS benefit → Line 1 Social Security income
  - Monthly SSI/SSDI benefit → Line 1 disability income
- Dividend/Trust/Investment income:
  - Monthly pension or retirement distribution → Line 1
  - Monthly dividend income (stocks/investments) → Line 1
  - Monthly trust or annuity distribution → Line 1
- Alimony:
  - Receives alimony from prior case → income (note case)
  - Pays alimony in prior case → Section III mandatory deduction
  - Neither → skip
- Workers' comp monthly → Line 1
- Unemployment compensation monthly → Line 1
- Royalty income → Line 1
- Gifts from family (regular/monthly) → Line 1 with flag
- Venmo/PayPal/Zelle/CashApp income → Line 1 with attorney flag
- Investment income (interest from savings/CDs/bonds) → Line 1
- Other income (freeform) → Line 1 other, description in notes
- Income notes → footnote in FA

**SECTION: Payroll Deductions (Pages 13–15)**
- Federal income tax withheld monthly → Section II, mandatory deductions
- State income tax → Section II (enter $0 if none; Florida has no state income tax — flag if amount entered)
- FICA/Social Security (6.2%) → Section II
- Medicare (1.45%) → Section II
- Mandatory retirement contribution (employer-required) → Section II mandatory
- Health insurance premium (employee share only) → Section II
  - **CRITICAL:** This amount also appears in Section IV expenses (Line 45). Flag if client enters same amount in both places — double-count audit required.
- Other mandatory deductions (1st and 2nd) → Section II mandatory with description
- Voluntary 401(k)/403(b) contribution → Section II voluntary deductions
- FSA/HSA monthly contribution → Section II voluntary
- Other voluntary deductions (life insurance, union dues, etc.) → Section II voluntary with description

**SECTION: Monthly Expenses — Housing & Utilities (Pages 15–19)**
Map to Section IV of the FA (Monthly Expenses), Lines as follows:
- Monthly rent → Line: Rent
- Monthly mortgage (P&I) → Line: Mortgage (principal and interest)
- Monthly real estate taxes → Line: Real estate taxes (or include in mortgage if escrowed — footnote)
- Homeowner's/renter's insurance → Line: Homeowner's/renter's insurance
- HOA fees → Line: HOA/Condo fees
- Condo fees → combined with HOA or separate line
- Lawn care/pest control/maintenance → Line: Lawn/maintenance
- Home repairs/upkeep → Line: Home repairs
- Other housing expenses (freeform) → other expenses line with description
- Electric → Line: Electric
- Gas/propane → Line: Gas/propane

**SECTION: Monthly Expenses — Continued (Pages 16–20 continued)**
- Water/sewer → Line: Water/sewer
- Trash → Line: Trash
- Phone (landline/cell) → Line: Telephone
- Cable/streaming/internet → Line: Cable/internet
- Other utilities → other expenses with description

**SECTION: Monthly Expenses — Children, Personal & Insurance (Pages 20–24)**
- Child care/daycare/after-school → Line: Child care
- Private/charter school tuition → Line: School tuition
- School supplies/fees/activities → Line: School-related expenses
- Extracurricular/sports/lessons → Line: Activities/sports
- Clothing for children → Line: Children's clothing
- Unreimbursed medical for children → Line: Children's unreimbursed medical
- Allowance for children → Line: Allowance
- Summer camp → Line: Summer activities
- Health insurance for children (if paid separately from payroll) → Line: Health insurance for children
- Life insurance → Line: Life insurance
- Dental insurance → Line: Dental insurance
- Vision insurance → Line: Vision insurance
- Disability insurance → Line: Disability insurance
- Personal unreimbursed medical → Line: Personal medical/dental
- Personal clothing → Line: Personal clothing
- Grooming/personal care → Line: Grooming/personal care
- Dry cleaning → Line: Dry cleaning/laundry
- Food/groceries → Line: Food/groceries (at home)
- Meals outside home → Line: Meals outside home
- Household supplies → Line: Household supplies/sundries
- Entertainment → Line: Entertainment/recreation
- Vacations → Line: Vacations

**SECTION: Transportation (Pages ~18–20)**
- Vehicle 1: monthly payment (principal/interest only) → Line: Auto loan payment, Vehicle 1
- Vehicle 1: insurance → Line: Auto insurance, Vehicle 1
- Vehicle 1: tag/registration → Line: Tag/registration
- Vehicle 1: gas/fuel → Line: Fuel
- Vehicle 1: maintenance/repairs → Line: Auto maintenance
- Vehicle 2: repeat same lines

**SECTION: Assets — Bank Accounts (Pages ~22–27)**
- Checking Account 1: institution, last 4 digits, current balance, sole/joint, date opened → Section V, Assets
- Checking Account 2: same
- Savings Account 1 and 2: same, note if joint
- Money Market/CD: institution, balance
- Cash on hand: amount
- Note "when acquired" for marital/non-marital tracing analysis (attorney flag if pre-marriage)

**SECTION: Assets — Retirement, Investments, Business & Other (Pages 30–33)**
- Deferred compensation value → Section V, retirement assets
- Brokerage/investment account: institution, current value, sole/joint → Section V
- Stock options/RSUs: employer, estimated value → Section V with flag
- Retirement accounts (401k, IRA, pension, etc.): institution, plan type, current value, sole/joint → Section V
- Business ownership interest: business name, type, ownership %, estimated value → Section V
- Note: business value is estimated — attorney flag for formal valuation

**SECTION: Assets — Real Property and Vehicles (Pages ~26–33)**
- Marital home: address, estimated value, how acquired, current mortgage balance, equity → Section V
- Other real property: same
- Vehicle 1: year/make/model, value (KBB), loan balance → Section V
- Vehicle 2: same

**SECTION: Debts and Liabilities (Pages ~33–38)**
- Mortgage(s): creditor, current balance, monthly payment, sole/joint → Section VI
- Home equity loan/HELOC: same
- Vehicle loan 1 and 2: creditor, balance, monthly payment, sole/joint → Section VI
- Credit Card 1 through 3+: issuer, balance, minimum payment, sole/joint → Section VI
- Student loans: lender, balance, monthly payment, sole/joint → Section VI
- Medical bills: creditor, balance, monthly payment → Section VI
- Personal loans: creditor, balance, monthly payment, sole/joint → Section VI
- IRS/tax debt: amount owed, payment plan amount → Section VI with flag
- Other debts: describe, balance, payment → Section VI

**SECTION: Attorney Flags & Background (Pages ~38–45)**
- Bankruptcy: year, chapter → RED FLAG, attorney alert
- Transferred/gifted/sold significant asset in last 3 years → RED FLAG, dissipation flag, attorney alert
- Income changed significantly in last 2 years → attorney flag, Income Analysis (Stage 5) trigger
- Recently changed jobs or reduced hours → attorney flag
- Receiving financial support from family/new partner → income flag, potential undisclosed income

---

## SECTION 4 — CALCULATION RULES

### 4A — Income Annualization and Monthly Conversion

All income and expenses on the FA must be expressed as **monthly** amounts.

| Pay Frequency | Conversion |
|---|---|
| Weekly | × 52 ÷ 12 |
| Bi-weekly (every 2 weeks) | × 26 ÷ 12 |
| Semi-monthly (twice per month) | × 2 |
| Monthly | no conversion |
| Annual | ÷ 12 |
| Hourly | × hours/week × 52 ÷ 12 |

### 4B — Gross Monthly Income (Line 1 Calculation)

Base monthly gross = primary employer income (salary ÷ 12, or hourly × hrs × 52 ÷ 12)

Add each additional income source separately. Total all sources to arrive at **Total Monthly Gross Income**.

**Bonus averaging:** Sum the last 3 years of bonuses → divide by 36 → add to monthly gross. If only 1 or 2 years available, average what is provided and footnote.

**Overtime:** If "regularly expected," include in gross. If "occasionally," include with footnote flagging for attorney review.

**Self-employment net:** Use net (gross revenue − ordinary expenses), not gross revenue. Flag if client-provided expenses seem unusually high.

**Rental income:** Always use net (gross rent − ordinary monthly expenses). Never include gross rental in income without the expense deduction. Flag if client reports gross.

### 4C — Net Monthly Income Calculation

Net Monthly Income = Gross Monthly Income − All Mandatory Deductions

**Mandatory deductions** (only these reduce gross for purposes of Line 2):
1. Federal income tax (actual withholding from paycheck)
2. State income tax (Florida = $0; flag if client enters amount)
3. FICA/Social Security (6.2% of gross up to annual cap)
4. Medicare (1.45%)
5. Mandatory retirement (employer-required, not voluntary)
6. Health insurance premium — employee share only (payroll-deducted)
7. Court-ordered child support for other children
8. Court-ordered alimony paid in prior/separate case
9. Other mandatory payroll deductions as described

**Voluntary deductions** (do NOT reduce gross income for Line 2, but ARE listed separately):
- 401(k), 403(b), voluntary retirement savings
- FSA/HSA contributions
- Life insurance through payroll
- Other voluntary payroll elections

**CRITICAL DEDUCTION AUDIT — RUN AUTOMATICALLY:**
1. Check if health insurance premium appears in both the payroll deductions section AND in the monthly expenses section. If so, flag as potential double-count. Paralegal must confirm with client before filing.
2. Verify FICA and Medicare are both present if client is a W-2 employee. If absent, calculate from gross and footnote.
3. Verify federal tax withholding is reasonable relative to gross income. Flag if it appears unusually low or zero for a working person.
4. If self-employed, verify SE tax (15.3%) is addressed. SE filers typically have no payroll withholding — half of SE tax is deductible; address in footnote.

### 4D — Net Income Calculation Example

> Gross Monthly Income: $6,500  
> Less: Federal Tax (-$800), FICA (-$403), Medicare (-$94), Health Ins (-$220)  
> **Net Monthly Income: $4,983**

Show this calculation in a footnote on the FA document.

---

## SECTION 5 — FORM STRUCTURE: LONG FORM 12.902(c)

Build the document in this exact order, matching the Supreme Court form structure:

### CAPTION BLOCK
```
IN THE CIRCUIT COURT OF THE _____ JUDICIAL CIRCUIT
IN AND FOR _____ COUNTY, FLORIDA
Case No.: _____________
Division: _____________

In re: _______________, Petitioner,
and _______________, Respondent.

FAMILY LAW FINANCIAL AFFIDAVIT
(Long Form — For use when individual gross income is $50,000 or more per year)
Florida Family Law Rules of Procedure Form 12.902(c)
```

### PARTY IDENTIFICATION BLOCK
- Full legal name
- Date of birth
- Occupation
- Employer name

### SECTION I — INCOME

**Monthly Gross Income:**

Line 1: Monthly gross salary or wages (from primary employment) ..................... $______  
*(Footnote: Annual salary $_____ ÷ 12 = $_____ OR hourly rate $_____ × _____ hrs/wk × 52 ÷ 12 = $_____)*

Line 2: Monthly bonuses, commissions, allowances, overtime, tips, and similar payments (list separately if from different employers) ............................. $______  
*(Footnote: 3-year bonus average: $_____/$____/$_____ = $_____ ÷ 3 yrs ÷ 12 = $_____/mo)*

Line 3: Monthly business income (if self-employed or own a business)  
*(Footnote: Gross $_____ − Expenses $_____ = Net $_____ per month)* ........................ $______

Line 4: Monthly disability benefits (SS, SDI, private) .................................... $______

Line 5: Monthly unemployment compensation .............................................. $______

Line 6: Monthly workers' compensation .................................................... $______

Line 7: Monthly retirement/pension/annuity income ....................................... $______

Line 8: Monthly Social Security benefits (not disability) ................................. $______

Line 9: Monthly interest and dividends .................................................... $______

Line 10: Monthly rental income (net of ordinary/necessary expenses) ..................... $______  
*(Footnote: Gross rent $_____ − Expenses $_____ = Net $_____)*

Line 11: Monthly income from royalties, trusts, estates .................................. $______

Line 12: Monthly reimbursed expenses and in-kind payments .............................. $______

Line 13: Monthly spousal support received from a previous or other case ................. $______  
*(Footnote: Case name and county: _______________)*

Line 14: Monthly child support received for _____ child(ren) from a previous or other case . $______

Line 15: Monthly other income (identify: __________________________________) ......... $______

**Line 16: TOTAL MONTHLY GROSS INCOME (add Lines 1–15) .............................. $______**

---

**Monthly Deductions from Gross Income:**

Line 17: Monthly federal income tax (actual withholding) ................................ $______

Line 18: Monthly state income tax (enter $0 if none) .................................... $______  
*(Footnote if non-zero: Florida has no state income tax — verify)*

Line 19: Monthly FICA — Social Security (6.2%) .......................................... $______  
*(Footnote if not from intake: Calculated at 6.2% × $_____ = $_____)*

Line 20: Monthly Medicare (1.45%) ........................................................ $______  
*(Footnote if not from intake: Calculated at 1.45% × $_____ = $_____)*

Line 21: Monthly mandatory retirement payments (employer-required) ...................... $______

Line 22: Monthly health insurance premium (employee's share only) ....................... $______  
**⚠ AUDIT FLAG: Verify this amount is NOT also entered in Section IV, Line 45. Double-count if both populated.**

Line 23: Monthly court-ordered child support paid for child(ren) from other cases ........ $______  
*(Case: _______________ County: _______________)*

Line 24: Monthly spousal support paid from a prior or separate case ...................... $______

Line 25: Monthly other mandatory deduction (describe: _________________________) ....... $______

Line 26: Monthly other mandatory deduction (describe: _________________________) ....... $______

**Line 27: TOTAL MONTHLY DEDUCTIONS (add Lines 17–26) ................................ $______**

**Line 28: NET MONTHLY INCOME (Line 16 minus Line 27) ................................ $______**

---

**Voluntary Deductions (not reducing income, listed for transparency):**

Line 29: Monthly voluntary retirement savings (401k/403b) ............................... $______

Line 30: Monthly FSA/HSA contribution ................................................... $______

Line 31: Monthly other voluntary deductions (describe: ________________________) ....... $______

---

### SECTION II — AVERAGE MONTHLY EXPENSES

*(All figures must be monthly averages. Attach conversion worksheet if not monthly.)*

**HOUSING**
| Line | Description | Monthly Amount |
|---|---|---|
| 32 | Rent | $______ |
| 33 | Mortgage (principal and interest only) | $______ |
| 34 | Real estate taxes (if not escrowed) | $______ |
| 35 | Homeowner's/renter's insurance | $______ |
| 36 | HOA fees | $______ |
| 37 | Lawn/pest control/maintenance | $______ |
| 38 | Home repairs/upkeep | $______ |
| 39 | Other housing expenses | $______ |

**UTILITIES**
| Line | Description | Monthly Amount |
|---|---|---|
| 40 | Electric | $______ |
| 41 | Gas/propane | $______ |
| 42 | Water/sewer | $______ |
| 43 | Trash collection | $______ |
| 44 | Phone (cell and/or landline) | $______ |
| 45 | Cable/internet/streaming | $______ |
| 46 | Other utilities | $______ |

**FOOD AND HOUSEHOLD**
| Line | Description | Monthly Amount |
|---|---|---|
| 47 | Groceries/household supplies | $______ |
| 48 | Meals outside the home | $______ |

**PERSONAL CARE**
| Line | Description | Monthly Amount |
|---|---|---|
| 49 | Clothing (personal) | $______ |
| 50 | Medical/dental/vision (unreimbursed) | $______ |
| 51 | Prescriptions | $______ |
| 52 | Grooming/hair/personal care | $______ |
| 53 | Dry cleaning/laundry | $______ |

**TRANSPORTATION**
| Line | Description | Monthly Amount |
|---|---|---|
| 54 | Vehicle 1 loan payment | $______ |
| 55 | Vehicle 2 loan payment | $______ |
| 56 | Auto insurance (all vehicles) | $______ |
| 57 | Gas/fuel | $______ |
| 58 | Tag/registration/license | $______ |
| 59 | Auto maintenance/repairs | $______ |
| 60 | Other transportation | $______ |

**INSURANCE (not deducted from paycheck)**
| Line | Description | Monthly Amount |
|---|---|---|
| 61 | Health insurance for self (if not payroll-deducted) | $______ |
| 62 | Health insurance for children | $______ |
| 63 | Life insurance | $______ |
| 64 | Disability insurance | $______ |
| 65 | Other insurance | $______ |

**CHILDREN'S EXPENSES**
| Line | Description | Monthly Amount |
|---|---|---|
| 66 | Child care/daycare/after-school | $______ |
| 67 | Private/charter school tuition | $______ |
| 68 | School supplies/fees/activities | $______ |
| 69 | Extracurricular/sports/lessons | $______ |
| 70 | Children's clothing | $______ |
| 71 | Children's unreimbursed medical/dental | $______ |
| 72 | Allowance | $______ |
| 73 | Summer camp/activities | $______ |
| 74 | Other children's expenses | $______ |

**ENTERTAINMENT AND RECREATION**
| Line | Description | Monthly Amount |
|---|---|---|
| 75 | Entertainment | $______ |
| 76 | Vacations (monthly average) | $______ |
| 77 | Clubs/memberships | $______ |

**MISCELLANEOUS**
| Line | Description | Monthly Amount |
|---|---|---|
| 78 | Gifts | $______ |
| 79 | Religious/charitable contributions | $______ |
| 80 | Pet expenses | $______ |
| 81 | Credit card payments (minimum) | $______ |
| 82 | Student loan payments | $______ |
| 83 | Medical bills (monthly payment) | $______ |
| 84 | Other monthly payments/debts | $______ |
| 85 | Other expenses (describe: _________________) | $______ |

**Line 86: TOTAL MONTHLY EXPENSES (add Lines 32–85) ................................. $______**

---

### SECTION III — ASSETS

*(List all assets — marital and non-marital. Note source/acquisition date for tracing.)*

**CASH AND BANK ACCOUNTS**
| Account | Institution / Last 4 Digits | Current Balance | Sole or Joint | Date Acquired |
|---|---|---|---|---|
| Checking 1 | | $______ | | |
| Checking 2 | | $______ | | |
| Savings 1 | | $______ | | |
| Savings 2 | | $______ | | |
| Money Market/CD | | $______ | | |
| Cash on Hand | | $______ | N/A | N/A |

**REAL PROPERTY**
| Property | Address | Estimated Value | Mortgage Balance | Net Equity | Sole or Joint | Acquired |
|---|---|---|---|---|---|---|
| Marital Home | | $______ | $______ | $______ | | |
| Other Property | | $______ | $______ | $______ | | |

*(Values are client estimates unless documented; flagged as unverified)*

**VEHICLES**
| Vehicle | Year/Make/Model | Estimated Value | Loan Balance | Net Equity | Sole or Joint |
|---|---|---|---|---|---|
| Vehicle 1 | | $______ | $______ | $______ | |
| Vehicle 2 | | $______ | $______ | $______ | |

**RETIREMENT AND INVESTMENT ACCOUNTS**
| Account | Institution / Plan Type | Current Value | Sole or Joint | Acquired |
|---|---|---|---|---|
| 401(k)/403(b) | | $______ | | |
| IRA | | $______ | | |
| Pension | | $______ | | |
| Deferred Compensation | | $______ | | |
| Brokerage/Investment | | $______ | | |
| Stock Options/RSUs | | $______ (est.) | | |

**BUSINESS INTERESTS**
| Business | Name / Type | Ownership % | Estimated Value | Notes |
|---|---|---|---|---|
| | | | $______ | Unverified — attorney flag for valuation |

**OTHER ASSETS**
| Item | Description | Estimated Value |
|---|---|---|
| | | $______ |

---

### SECTION IV — LIABILITIES

| Debt | Creditor | Current Balance | Monthly Payment | Sole or Joint |
|---|---|---|---|---|
| Mortgage | | $______ | $______ | |
| HELOC/2nd Mortgage | | $______ | $______ | |
| Vehicle Loan 1 | | $______ | $______ | |
| Vehicle Loan 2 | | $______ | $______ | |
| Credit Card 1 | | $______ | $______ | |
| Credit Card 2 | | $______ | $______ | |
| Credit Card 3 | | $______ | $______ | |
| Student Loan | | $______ | $______ | |
| Medical Bills | | $______ | $______ | |
| IRS/Tax Debt | | $______ | $______ | |
| Other | | $______ | $______ | |

**TOTAL MONTHLY DEBT PAYMENTS: $______**  
*(Note: Mortgage is included in Section II expenses — do not double-count in total monthly expenses)*

---

### SIGNATURE / CERTIFICATION BLOCK
```
I certify that the information provided in this financial affidavit is true and correct to the best of my knowledge.

_________________________________          _______________
[PARTY NAME], [Petitioner/Respondent]       Date

STATE OF FLORIDA
COUNTY OF _______________

Sworn and subscribed before me this _____ day of _____________, 20_____.

_________________________________
Notary Public / Deputy Clerk
Commission No.: ___________
My Commission Expires: ___________
```

---

## SECTION 6 — SHORT FORM 12.902(b) STRUCTURE

If short form is applicable (gross income < $50,000/year), build the same structure but with simplified expense categories. The short form condenses the expense section into broader categories. The income section remains the same line-by-line structure. The asset and liability sections remain the same. The key difference: expenses are grouped into approximately 12 broader categories rather than the line-by-line detail of the long form.

Short form income threshold note: If gross income is close to $50,000 (within $5,000 above or below), flag for attorney review — the opposing party or court may require upgrade to long form.

---

## SECTION 7 — FOOTNOTE AND FLAG PROTOCOL

Every figure that is estimated, calculated, averaged, or uncertain must carry a footnote. Use sequential footnote numbers. At the bottom of the document, produce a **Footnote & Flag Register** in this format:

| # | Field/Line | Note Type | Detail |
|---|---|---|---|
| 1 | Line 1 — Gross Income | Calculated | Annual salary $_____ ÷ 12 = $_____/month |
| 2 | Line 2 — Overtime | Attorney Flag | Client reports overtime "regularly expected" — confirm inclusion with attorney |
| 3 | Line 22 — Health Ins | Audit Flag | Amount matches Line 65 expense entry — potential double-count, confirm with client |
| 4 | Line 10 — Rental Income | Calculation | Gross rent $_____ − expenses $_____ = net $_____ per month |
| 5 | Vehicle 1 — Value | Unverified | Client estimate only — no KBB or title document provided |
| 6 | Business Interest | RED FLAG | Client uses business account for personal expenses — attorney review required |
| 7 | Section I — Income Change | Attorney Flag | Client reports significant income change in last 2 years — Income Analysis (Stage 5) required |
| 8 | Asset Transfer | RED FLAG | Client transferred/sold significant asset in last 3 years — dissipation review required |

**RED FLAG items go to attorney immediately.** Regular flags and calculations are noted for paralegal review before submission to attorney.

---

## SECTION 8 — DISCOVERY DOCUMENT CROSS-CHECK (WHEN DOCUMENTS UPLOADED)

When supporting documents are uploaded alongside or after the intake form, run a cross-check before finalizing the FA:

**Pay stubs:**
- Compare year-to-date gross on most recent stub to intake-reported income
- Annualize YTD gross (YTD gross ÷ pay periods elapsed × total pay periods in year)
- Flag discrepancy if annualized figure differs from intake figure by more than 5%
- Confirm FICA, Medicare, federal tax deductions match intake entries

**Tax returns:**
- Compare Line 1 (wages) on most recent 1040 to FA income
- Review Schedule C for self-employment income
- Review Schedule E for rental and pass-through income
- Compare prior 2 years for income trend — flag if declining

**Bank statements:**
- Compare stated account balances to intake-reported balances
- Flag unidentified large deposits (potential undisclosed income)
- Flag large transfers out (potential dissipation)
- Confirm rent/mortgage payments match expense section

**When document figures differ from intake figures:**
- Use the document-supported figure in the FA
- Footnote: "Intake form stated $_____; [document type] shows $_____; document figure used"
- If discrepancy is material (>10%), add attorney flag

---

## SECTION 9 — OUTPUT REQUIREMENTS

**Primary Output:** Word document (.docx) formatted to match the Florida Supreme Court approved form layout

**Document formatting standards:**
- Header: "FLORIDA FAMILY LAW FINANCIAL AFFIDAVIT — [LONG/SHORT] FORM" centered, bold
- Sub-header: Form 12.902(c) [or (b)], date of completion
- Caption block: standard circuit court caption
- Sections labeled with bold underlined headings matching the Supreme Court form
- All dollar amounts right-aligned in a consistent column
- Every line addressed — no blank lines (use $0.00 or N/A)
- Footnote register at end of document, before signature block
- Footer on every page: "DRAFT — INTERNAL USE ONLY — SUBJECT TO ATTORNEY REVIEW — NOT FOR FILING"
- Page numbers

**Secondary Output (optional, attorney can request):** Separate Attorney Flags Summary memo — one page, bullets only, listing all RED FLAGS and attorney flags from the footnote register. Request with: "Generate the FA Flag Summary."

---

## SECTION 10 — COMMANDS

| What to type | What Claude does |
|---|---|
| `FA Intake uploaded. Build the FA for [Name].` | Parse intake, determine form type, populate all fields, produce .docx |
| `Build long form FA for [Name].` | Force long form regardless of income |
| `Build short form FA for [Name].` | Force short form — will flag if income exceeds threshold |
| `Pay stubs uploaded. Update [Name]'s FA.` | Cross-check income section against stubs, update and footnote |
| `Tax returns uploaded. Update [Name]'s FA.` | Cross-check income against returns, update |
| `Bank statements uploaded. Update [Name]'s FA.` | Cross-check accounts, flag unidentified deposits/transfers |
| `All documents uploaded. Finalize [Name]'s FA.` | Final cross-check pass, footnote all discrepancies, produce final .docx |
| `Generate the FA Flag Summary for [Name].` | Produce one-page attorney flags memo |
| `Recalculate Net Income for [Name].` | Rerun deduction audit and net income calculation |

---

## SECTION 11 — MANDATORY PRE-FILING AUDIT CHECKLIST

Before the FA is submitted to the attorney for review, Claude runs this audit automatically:

- [ ] Correct form selected (short vs. long) based on total gross income
- [ ] All income sources from intake are addressed on the FA
- [ ] Total monthly gross income calculated and shown
- [ ] All deductions itemized — FICA and Medicare present if W-2 employee
- [ ] Net monthly income calculated and shown
- [ ] Health insurance: confirm no double-count between deductions (Line 22) and expenses (housing/insurance section)
- [ ] All expense lines populated (zeros where applicable, not blanks)
- [ ] Total monthly expenses calculated
- [ ] All bank accounts listed with current balances
- [ ] All real property listed with estimated values and mortgage balances
- [ ] All vehicles listed with values and loan balances
- [ ] All retirement accounts listed
- [ ] All liabilities listed with balances and monthly payments
- [ ] RED FLAG items documented in footnote register
- [ ] Signature block and certification language present
- [ ] "DRAFT — INTERNAL USE ONLY" footer on every page
- [ ] Footnote register complete

If any item fails, Claude notes the gap and does not mark the FA as complete.

---

## SECTION 12 — LIMITATIONS

This skill populates the FA from client-provided intake data and uploaded documents. It does not:
- Make legal conclusions about income characterization
- Classify assets as marital or non-marital
- Verify property values beyond client estimates
- Calculate child support guidelines amounts
- Draft MSA terms
- Authorize filing

All FA output is internal work product requiring attorney review before filing.

---

## AMBIENT STANDARD — Feinstein & Mendez, PA PLEADING FORMAT & DRAFT-STATE RULES

`lal-pleading-standard` governs every court-bound document this skill produces.
Two rules, from the first keystroke:

1. **Format correctly immediately** — portrait, Times New Roman 12 black, single
   spacing 0pt before/after, left aligned, 1" margins, Feinstein & Mendez, PA caption (court centered ·
   case/division right · parties left · rule line ending in `/` · title centered
   bold ALL CAPS), numbering I. → 1. → a. → i. continuous. No bullets, no dividers.
   There is no rough-format stage that gets fixed later.
2. **Drafts show their work, highlighted** — attorney notes 🟨, outstanding facts 🟨,
   alternative provisions 🟩 drafted in full. When unclear what the pleading should
   contain, present highlighted ALTERNATIVES — never assume and draft one version
   as if decided. Never strip flags at draft stage; only `lal-finalize-draft`
   strips, after the attorney resolves them.

---

## MANDATORY HANDOFF — PRE-FILING QC GATE

Any document this skill produces that will be **filed with a court, served on a
party, or sent outside the firm** goes to `lal-prefiling-qc` before it reaches
an attorney. This handoff is not optional and is not skippable for urgency.

```
THIS SKILL  →  lal-prefiling-qc  →  ATTORNEY SIGN-OFF  →  FILE / SERVE / SEND
```

- Do not present a draft as "ready for {{ROLE_APPROVER}}" or "ready to file" until the gate has run.
- A **BLOCKED** verdict returns the draft here for correction. Fix and re-run the gate.
- A **CONDITIONAL** verdict goes to the attorney with the findings attached.
- Never resolve a flagged item by deleting the language to make the gate pass.

- After the gate clears, hand the document to `lal-finalize-draft` to produce the
  filing-ready Word file and PDF. That skill enforces portrait, Times New Roman 12,
  all black, single spacing, the Feinstein & Mendez, PA caption layout, strips every internal artifact,
  and checks `lal-judicial-procedures` for the assigned judge before output.

**Approval behavior:** if the person in the session is an Feinstein & Mendez, PA attorney ({{ROLE_APPROVER}} or
{{ROLE_APPROVER}}), her instruction IS the sign-off — do not ask her to approve what she just
directed. If staff, every attorney-gated item routes to {{ROLE_APPROVER}} and waits.

---

## OUTPUT DELIVERY — FIRM STANDARD (v2, {{DMS}}-native)

All output from this skill is delivered through `lal-file-connector` (Operation 4).

**Destination:** `Notes/` in the {{DMS}} matter folder
`Last, First - [Matter Type] (####-####)`. There is no `CLAUDE OUTPUT` folder and
no {{DMS}} path. (`GAL Notes/` on GAL matters.)

**Filename:** `MM.DD.YY - LastName - DocTitle - v1.ext` — versioned, never overwritten.

**Delivery depends on where this skill is running:**

- **Claude.ai (chat / Projects)** — Claude cannot write to {{DMS}}. Present the file
  as a **download** and print the destination block: matter folder → `Notes/`, filename,
  version. Never write "saved to {{DMS}}."
- **Cowork (desktop)** — write to the folder designated for the session (ask once at
  first delivery, reuse thereafter), confirm the **actual path written**, and state
  where the file belongs in {{DMS}}.

Nothing is filed or sent without attorney sign-off. Time is tracked in {{PM_SYSTEM}},
including Claude-assisted work.

