# Feinstein & Mendez, PA MSA — Word Formatting Specification

This file defines the EXACT formatting for all Feinstein & Mendez, PA Marital Settlement Agreements.
Match this spec precisely. The output must be visually identical to the signed
executed MSA examples in the project files.

---

## Page Setup
- **Paper:** US Letter (8.5" × 11") — 12240 × 15840 DXA in docx-js
- **Margins:** 1 inch all sides — 1440 DXA each in docx-js
- **Orientation:** Portrait

## Font
- **Face:** Times New Roman throughout — override docx-js default
- **Size:** 12pt (24 half-points in docx-js size property)
- **Color:** Black

## Body Text
- **Line spacing:** Double-spaced — `spacing: { line: 480, lineRule: "auto" }`
- **Alignment:** Fully justified (both left and right) — `AlignmentType.BOTH`
- **First-line indent:** 0.5 inch for the first line of each body paragraph — `indent: { firstLine: 720 }` (720 DXA = 0.5 inch)
- **Space before/after paragraphs:** 0 — no extra spacing between paragraphs

## Footer
- **Content:** "Page X of Y" — using PageNumber.CURRENT and PageNumber.TOTAL_PAGES
- **Alignment:** Centered
- **Font:** Times New Roman, 12pt
- **Appears on:** ALL pages including first page
- No header on any page

---

## Heading Styles

### Document Title
```
MARITAL SETTLEMENT AGREEMENT
```
- ALL CAPS
- Bold
- Underlined
- Centered (AlignmentType.CENTER)
- No first-line indent
- Font: Times New Roman 12pt

### WITNESSETH
```
W I T N E S S E T H:
```
- Spaced letters (add a space between each character)
- Underlined
- NOT bold
- Centered
- Followed by a blank line before WHEREAS clauses

### Top-Level Section Headings (1. RECITALS. / 2. SEPARATION. etc.)
```
1.      RECITALS.
```
- Numbered with a period: `1.`
- Tab character between number and section name (~0.75 inch tab stop)
- Bold
- Underlined
- ALL CAPS
- Left aligned (NOT centered)
- No first-line indent (hanging style: number at left margin, text after tab)
- Line above and below: use paragraph spacing (not blank paragraphs)

### Subsection Headings (4.1 / 4.2 / 4.3 etc.)
```
      4.1   Parenting Plan:
```
- Indented approx. 0.5 inch from left margin
- Underlined
- NOT bold
- Mixed case (e.g., "Parenting Plan:" not "PARENTING PLAN:")
- Followed by body text continuing on the same line OR on next line indented

### Subsection Headings 5.1 / 5.2 etc. (Property Settlement subsections)
```
      5.1      RETIREMENT ACCOUNTS
```
- Indented 0.5 inch
- ALL CAPS
- Bold
- Underlined

### Sub-Subsection Headings (A. B. C. under Section 4)
```
            A.      NOTIFICATION OF ILLNESS OR ACCIDENT:
```
- Indented approximately 1 inch
- Letter + period: `A.`
- Tab to heading text (~0.75 inch tab after letter)
- ALL CAPS
- Underlined
- NOT bold
- Heading text followed by colon
- Body text follows on same line, with a space after the colon

### Numbered Sub-Items (1. 2. 3. under E. MISCELLANEOUS)
```
                  1.      When the children are living...
```
- Indented approximately 1.5 inches
- Number + period: `1.`
- Tab to text
- Regular body text (no bold, no underline)
- Double spaced

### Lettered Sub-Items (a. b. c. d. under numbered items)
```
                        a.      Fight within the hearing...
```
- Indented approximately 2 inches
- Lowercase letter + period: `a.`
- Tab to text
- Regular body text

---

## Inline Formatting

### WHEREAS Keyword
- **WHEREAS** — Bold, immediately followed by comma, then normal weight text
- Example: `**WHEREAS**, the Parties were married...`

### NOW, THEREFORE
- **NOW, THEREFORE** — Bold, followed by comma, then normal weight text

### IN WITNESS WHEREOF
- **IN WITNESS WHEREOF** — Bold, followed by comma, then normal weight text

### Exhibit References
- Bold AND Underlined: **<u>Exhibit "A"</u>**, **<u>Exhibit "B"</u>**

### Underlined Amounts / Dates (in WHEREAS section)
- Specific dates and places in the first WHEREAS clause are underlined
- Example: "married on or about <u>October 4, 2008</u> in <u>Daytona Beach, Florida</u>"

### Vehicle Names (in §5.4)
- Underline the year/make/model: e.g., <u>2021 Chevrolet Traverse</u>

---

## Signature Block Formatting
```
      IN WITNESS WHEREOF, the Parties have hereunto set their hands and seals as
of this day and year first above written.

Signed, sealed and delivered in the presence of:


_______________________________          _______________________________
[HUSBAND FULL NAME], HUSBAND             [WIFE FULL NAME], WIFE
```
- "IN WITNESS WHEREOF" bold
- Signature lines: 31 underscore characters each
- Parties side by side (use tab stops or table with invisible borders — NOT a visible table)
- Name and role label (HUSBAND / WIFE) typed below each signature line
- Approximately 1.5 inches of vertical space above signature lines for handwriting

## Notary Block Formatting
```
STATE OF FLORIDA
COUNTY OF [COUNTY]

      The foregoing instrument was acknowledged before me this _____ day of
______________, 20___, by [PARTY FULL NAME], [Petitioner/Respondent], who is personally
known to me or who has produced his/her driver's license as identification.

      WITNESS my hand and official seal this _____ day of ______________, 20___.


                                     ___________________________________
                                     Notary Public – State of Florida

My Commission Expires: ____________________  Commission # ______________
```
- "STATE OF FLORIDA" and "COUNTY OF [COUNTY]" flush left, single spaced, no bold
- Notary signature line: right-aligned or center-right
- Notary label below signature line: "Notary Public – State of Florida"
- Commission info below that: "My Commission Expires: ___  Commission # ___"
- Two separate notary blocks — one for the Petitioner, one for the Respondent — on final page(s)

---

## docx-js Implementation Notes

```javascript
// Times New Roman throughout
styles: {
  default: {
    document: {
      run: { font: "Times New Roman", size: 24, color: "000000" }
    }
  }
}

// US Letter, 1-inch margins
properties: {
  page: {
    size: { width: 12240, height: 15840 },
    margin: { top: 1440, right: 1440, bottom: 1440, left: 1440 }
  }
}

// Body paragraph style (most paragraphs)
new Paragraph({
  alignment: AlignmentType.BOTH,
  spacing: { line: 480, lineRule: "auto" },
  indent: { firstLine: 720 },  // 0.5 inch first-line indent
  children: [new TextRun({ font: "Times New Roman", size: 24, text: "..." })]
})

// Section heading (1. RECITALS.)
new Paragraph({
  alignment: AlignmentType.LEFT,
  spacing: { line: 480, lineRule: "auto" },
  tabStops: [{ type: TabStopType.LEFT, position: 1080 }],  // 0.75 inch tab
  children: [
    new TextRun({ bold: true, underline: {}, text: "1." }),
    new TextRun({ text: "\t" }),
    new TextRun({ bold: true, underline: {}, text: "RECITALS." })
  ]
})

// Footer with Page X of Y
new Footer({
  children: [
    new Paragraph({
      alignment: AlignmentType.CENTER,
      children: [
        new TextRun({ text: "Page ", font: "Times New Roman", size: 24 }),
        new TextRun({ children: [PageNumber.CURRENT], font: "Times New Roman", size: 24 }),
        new TextRun({ text: " of ", font: "Times New Roman", size: 24 }),
        new TextRun({ children: [PageNumber.TOTAL_PAGES], font: "Times New Roman", size: 24 }),
      ]
    })
  ]
})
```

---

## Common Mistakes to Avoid
- ❌ Do NOT use Arial — MSA uses Times New Roman
- ❌ Do NOT use single spacing — everything is double-spaced
- ❌ Do NOT use left-only justification — body text is BOTH (full justification)
- ❌ Do NOT skip the footer — every page needs "Page X of Y"
- ❌ Do NOT bold section numbers or use ALL CAPS for subsections (4.1, 4.2) — those are underlined only
- ❌ Do NOT use numbered lists from docx-js LevelFormat for the section numbers — manually build them with tab stops to match Feinstein & Mendez, PA style exactly
- ❌ Do NOT use visible table borders for signature blocks — use tab stops
- ❌ Do NOT omit both notary blocks
