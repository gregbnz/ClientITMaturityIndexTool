# IT Maturity Assessment

A self-contained, single-page web tool for assessing an organisation's IT maturity across **4 areas**, **13 traits**, and **56 weighted questions**, scored on a 1–5 IT Maturity Level (IML) scale (Nascent → Innovating).

The app runs entirely in the browser — no server, no install. Just browse to https://itmi.stallio.nz.

## What it does

- Walks the user through 56 capability questions, grouped by area and trait.
- Each question is rated on the IML 1–5 scale via a slider, with the matching descriptor revealed inline. Optional commentary can be captured against every question.
- An **industry baseline** (selected on the intro screen) is carried through the report so every score is shown alongside the comparable industry average.
- On completion, generates a results page with:
  - Overall score, percentage, and headline IML level — with **Your IML / Industry avg / Δ vs industry** comparison
  - **Maturity by area** radar chart (your shape overlaid on the dashed industry shape)
  - **Rating distribution** donut chart
  - **Score by area** bars with a teal industry-average marker on each bar and a delta indicator
  - **Score by trait** table with Your IML, Industry IML, and score
  - **Priority focus order** — questions ranked by `weighting × (6 − IML)`, with each row expandable to show the current state, target state, and 5 tailored recommendations to advance to the next level

## How to use

1. Visit https://itmi.stallio.nz in any modern browser (Chrome, Edge, Safari, Firefox).
2. Enter the customer name, your name, and pick the **industry** for benchmarking, then click **Begin assessment**.
3. Move through each section, rating every question. Add commentary where useful.
4. When all 56 questions are rated, click **View results** to see the scored report.

## Sample data button

On the intro screen, click **Fill with sample data** to skip the questionnaire entirely. The tool populates a realistic low-to-mid maturity profile across all 56 questions and jumps straight to the results page — useful for demos, walkthroughs, or exploring the report layout without filling everything in manually.

## Exports

The results page provides three exports:

### Export Summary (PDF)

Generates a print-ready summary PDF via the browser's native print dialog (Save as PDF). Output:

- A stylised cover page with the company name and industry
- The full on-screen results — overall score with industry comparison, radar chart with industry overlay, rating distribution donut, score by area, score by trait
- File name: `<Customer> - IT Maturity Assessment Summary - <Date>.pdf`

Print-to-PDF is used for this export so SVG charts stay as crisp vectors and the layout matches what's on screen.

### Export Answers (XLSX)

Downloads an `.xlsx` workbook containing the full prioritised list:

- Rank, question number, question text, area, trait, foundational flag
- IML rating, weighting, your commentary
- File name: `<Customer> - IT Maturity Assessment Answers - <Date>.xlsx`

Generated client-side with [SheetJS](https://sheetjs.com/).

### Export Recommendations (PDF)

Opens a modal listing the prioritised questions, defaulting to the top 5. Tick or untick to choose which to include (top 5 / top 10 / all / none shortcuts available). Output:

- A stylised cover page with the company name and industry
- For each selected question: priority rank, current state, target state, and 5 tailored recommendations (each with a benefit summary and implementation note)
- File name: `<Customer> - IT Maturity Assessment Recommendations - <Date>.pdf`

Like the summary export, this uses print-to-PDF for vector charts and crisp text.

## Requirements

- A modern browser with JavaScript enabled.
- Internet access on first load (for the DM Sans web font and the SheetJS CDN). After that, the assessment itself runs offline.

## Files

- `index.html` — the entire app (HTML + CSS + JS + question bank + industry baselines + recommendations + cover-page imagery).
