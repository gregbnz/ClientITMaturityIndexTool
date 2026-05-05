# IT Maturity Assessment

A self-contained web tool for assessing an organisation's IT maturity across **4 areas**, **13 traits**, and **56 weighted questions**, scored on a 1–5 IT Maturity Level (IML) scale (Nascent → Innovating).

The app runs entirely in the browser, hosted on GitHub pages - no install required. Just browse to https://itmi.stallio.nz.

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
  - **Priority focus order** — questions ranked by IML with an added influence of weighting, where high weight (ie high impact, low cost) items are prioritised. Each row is expandable to show the current state, target state, and 5 tailored recommendations to advance to the next level

## How to use

1. Visit https://itmi.stallio.nz in any modern browser (Chrome, Edge, Safari, Firefox) with JavaScript enabled. Note: Internet access is required on first load, after which the assessment itself runs offline.
2. Enter the customer name, your name, and pick the **industry** for benchmarking, then click **Begin assessment**.
3. Move through each section, rating every question. Add commentary where useful.
4. When all 56 questions are rated, click **View results** to see the scored report.

## Sample data button

On the intro screen, click **Fill with sample data** to skip the questionnaire entirely. The tool populates a realistic low-to-mid maturity profile across all 56 questions and jumps straight to the results page — useful for demos, walkthroughs, or exploring the report layout without filling everything in manually.

## Exports

The results page provides three exports:

### Export Summary (PDF)

Generates a print-ready summary PDF via the browser's native print dialog (Save as PDF).
- File name: `<Customer> - IT Maturity Assessment Summary - <Date>.pdf`

### Export Answers (XLSX)

Generates n `.xlsx` workbook containing the full prioritised list of questions
- File name: `<Customer> - IT Maturity Assessment Answers - <Date>.xlsx`

Generated client-side with [SheetJS](https://sheetjs.com/).

### Export Recommendations (PDF)

Opens a dialog listing the prioritised questions, defaulting to the top 5. Tick or untick to choose which to include (Shortcuts available along the top). Output:

- For each selected question: priority rank, current state, target state, and 5 tailored recommendations (each with a benefit summary and implementation note)
- File name: `<Customer> - IT Maturity Assessment Recommendations - <Date>.pdf`