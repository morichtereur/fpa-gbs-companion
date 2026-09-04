# fpa-gbs-companion

**EY's 2026 survey of FP&A in Global Business Services, redrawn as an
answer-first interactive brief — with a positioning tool that locates a
function inside the survey's own cohorts.**

**Live page: <https://morichtereur.github.io/fpa-gbs-companion/>**

This is an independent reading of a published study, not an EY publication.
Every figure belongs to *The state of Financial Planning and Analysis in
Global Business Services in 2026 and beyond* (EY, May 2026) by Christian
Willenbruch, Maria Saggese and Alexandre Magnou —
[the PDF is public](https://www.ey.com/content/dam/ey-unified-site/ey-com/en-gl/services/consulting/documents/ey-gl-the-state-of-financial-planning-in-global-business-services-in-2026-and-beyond-07-2026.pdf).
The structure, the exhibit titles and every interpretive sentence are the
compiler's, and the page says so on its face.

## What the survey says, in one pass

**Scale decides adoption. Maturity decides scope.** Three findings carry the
page:

1. **Adoption is a function of scale, and the direction is settled.** GBS
   delivery of FP&A rises step for step with the size of the FP&A
   organization — 33% below 100 FTE, 100% above 2,000 — and 85% of today's
   non-adopters plan to follow within one to three years.
2. **Scope follows maturity, not ambition.** The transactional core (cost
   accounting, financial analysis, performance reporting) is broadly shared;
   planning arrives second; the strategic tier opens only for mature
   functions. The planned expansion concentrates on budgeting (+24pt) and
   forecasting (+24pt).
3. **The binding constraint rotates as functions mature** — from scope and
   silos (basic), to stakeholder buy-in (developing), to data and tooling
   (mature) — and AI separates the field where automation alone no longer
   does: 40% of the smallest companies report no AI/ML use in FP&A, against
   9% of the largest.

## What the page is

A single self-contained HTML file. No build step, no framework, no tracking;
the only external dependency is Google Fonts.

- **Five exhibits** with action titles, unit lines, hover tooltips and
  per-exhibit "so what" bars: the adoption staircase, scope by maturity
  (click a cohort to isolate it), current-vs-planned penetration, the blocker
  rotation as a dot plot, and automation vs AI side by side.
- **A positioning tool.** Describe a function — FP&A size band, the processes
  its GBS supports, optionally its AI tier — and the page matches the scope
  profile to the nearest survey cohort, names the processes the next cohort
  typically hands over next, and says which blocker the rotation predicts.
  Nothing is scored; every output sentence is read directly off the published
  figures.
- **The five CFO decisions** from the study, condensed faithfully, each
  tagged with the exhibit that evidences it.

## Data provenance

The figures were not transcribed from the PDF's reading order — plain text
extraction scrambles two of its charts. Every data label was instead matched
to its position on the page (pypdf `visitor_text` coordinates), so each value
sits under the bar it belongs to. Example, the scope-by-maturity chart (p. 5),
share of companies whose GBS supports each process:

| process | basic | developing | mature |
|---|---|---|---|
| Financial Analysis | 33% | 78% | 100% |
| Cost Accounting | 67% | 72% | 100% |
| Performance Reporting | 33% | 78% | 100% |
| Budgeting & Annual Planning | 33% | 61% | 100% |
| Forecasting | 33% | 61% | 75% |
| Capex Management | 33% | 39% | 50% |
| Strategic Planning | 0% | 17% | 75% |
| Strategic Projects / M&A | 0% | 11% | 50% |

One erratum surfaced in the process: the published AI/ML chart (p. 12) reuses
the automation chart's legend, while the prose defines different tiers. The
page follows the prose and footnotes the discrepancy.

## What it cannot say

- **~50 companies, fieldwork H2 2025.** Split three ways by maturity, each
  cohort is small — positions are meaningful, decimal points are not.
- **Maturity is self-assessed**, and the study itself flags the possible bias.
- **"Supported by GBS" measures presence, not extent** — the study's own
  clarification, carried on the page wherever it applies.

## Run locally

```
python3 -m http.server -d . 8080
```

Or just open `index.html` — the file declares its own encoding and has no
build step.

## License

Code and page structure: MIT. All survey figures remain the property of the
study and its authors; they are reproduced here in redrawn form, with
attribution, for commentary.
