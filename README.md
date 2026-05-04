# IT Maturity Assessment

A self-contained, single-page web tool for assessing an organisation's IT maturity across **4 areas**, **13 traits**, and **56 weighted questions**, scored on a 1–5 IT Maturity Level (IML) scale (Nascent → Innovating).

The app runs entirely in the browser — no server, no install. Just browse to https://itmi.stallio.nz.

## What it does

- Walks the user through 56 capability questions, grouped by area and trait.
- Each question is rated on the IML 1–5 scale via a slider, with the matching descriptor revealed inline. Optional commentary can be captured against every question.
- On completion, generates a results page with:
  - Overall score, percentage, and headline IML level
  - **Maturity by area** radar chart
  - **Rating distribution** donut chart
  - Score breakdown by area and by trait
  - **Priority focus order** — questions ranked by `weighting × (6 − IML)`, with each row expandable to show the current state, target state, and 5 tailored recommendations to advance to the next level

## How to use

1. Visit https://itmi.stallio.nz in any modern browser (Chrome, Edge, Safari, Firefox).
2. Enter the customer name and your name, then click **Begin assessment**.
3. Move through each section, rating every question. Add commentary where useful.
4. When all 56 questions are rated, click **View results** to see the scored report.

## Sample data button

On the intro screen, click **Fill with sample data** to skip the questionnaire entirely. The tool populates a realistic low-to-mid maturity profile across all 56 questions and jumps straight to the results page — useful for demos, walkthroughs, or exploring the report layout without filling everything in manually.

## Excel export

From the results page, click **Export to Excel** to download an `.xlsx` file containing the full prioritised list:

- Rank, question number, question text, area, trait, foundational flag
- IML rating, weighting, your commentary
- The 5 recommendations to advance each question to its next IML level

The file is named `<Customer> - Assessment - <Date>.xlsx` and uses [SheetJS](https://sheetjs.com/) to generate the workbook client-side.

## Requirements

- A modern browser with JavaScript enabled.
- Internet access on first load (for the DM Sans web font and the SheetJS CDN). After that, the assessment itself runs offline.

## Files

- `index.html` — the entire app (HTML + CSS + JS + question bank + recommendations).
