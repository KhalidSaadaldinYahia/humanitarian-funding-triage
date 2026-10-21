# Humanitarian Funding Triage

An operational Power BI dashboard for examining the financing position of 2025 humanitarian response plans. It compares plan requirements with reported funding, quantifies unmet requirements, and supports transparent prioritisation without presenting financial exposure as a substitute for humanitarian severity.

## Dashboard pages

- **Funding Triage** — portfolio-level requirements, reported funding, unmet requirements, coverage, and the largest financing gaps.
- **Intervention Queue** — a decision-support view for comparing plans by financial exposure and coverage.
- **Plan Deep Dive** — an interactive plan-level workspace with detailed funding and benchmark context.
- **Methodology & Sources** — metric definitions, data provenance, analytical rules, and interpretation limitations.

## Key validated figures

- 46 released humanitarian response plans
- USD 45.47 billion in requirements
- USD 15.59 billion in reported funding
- USD 29.88 billion in unmet requirements
- 34.29% overall funding coverage

## Data source

The project uses public 2025 plan and funding records from the [UN OCHA Humanitarian Programme Cycle API](https://api.hpc.tools/) and [Financial Tracking Service](https://fts.unocha.org/), retrieved on 13 August 2026.

Language-code values (`en`, `es`, `fr`) that were accidentally loaded into `PlanType` were reconciled to `Humanitarian response plan`; regional, flash-appeal, and other plan categories remain unchanged.


## Methodology and limitations

- Funding coverage equals reported funding divided by plan requirements.
- Unmet requirement equals the larger of plan requirements minus reported funding or zero. Portfolio unmet requirements therefore sum plan-level non-negative gaps.
- The priority index is a transparent portfolio construct used only to organise financial exposure; it is not an official OCHA indicator and does not measure severity, access, implementation capacity, or programme quality.
- FTS records are continually revised as new contributions are reported or corrected, so the dashboard represents the retrieval-date snapshot.
- Non-plan funding flows are excluded from plan-level comparisons.

## Quality assurance

The packaged PBIP was validated for report structure, visual definitions, dataset row count, and reconciliation of requirements, funding, funding gap, and coverage before publication.

## Author

**Khalid SaadAldin Yahia**  
Data Analyst · Power BI · Python · SQL · Excel

## Open and inspect the report

- [Preview the dashboard PDF](Humanitarian_Funding_Triage_Dashboard.pdf). A PDF is a static export; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/humanitarian-funding-triage/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`HumanitarianFundingTriage.pbip`](project/HumanitarianFundingTriage.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository's public `main` branch. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.
