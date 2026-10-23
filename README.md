# Humanitarian Funding Triage

## Open the interactive dashboard

**Recommended:** [download HumanitarianFundingTriage.pbix](HumanitarianFundingTriage.pbix) and open it in a recent Power BI Desktop. The PBIX contains the report and its embedded data model, so you only need this one file to explore the saved dashboard. For reproducible source files and the included CSV snapshot, [download the complete repository ZIP](https://github.com/KhalidSaadaldinYahia/humanitarian-funding-triage/archive/refs/heads/main.zip), extract it, and open `project/HumanitarianFundingTriage.pbip` with its sibling `.Report`, `.SemanticModel`, and `data` folders intact. The PDF below is a static preview. A data refresh may require network access to the documented source snapshot.

## Dashboard pages

- **Funding Triage** — portfolio-level requirements, reported funding, unmet requirements, coverage, and the largest financing gaps.
- **Intervention Queue** — a decision-support view for comparing plans by financial exposure and coverage.
- **Plan Deep Dive** — an interactive plan-level workspace with detailed funding and benchmark context.
- **Methodology & Sources** — metric definitions, data provenance, analytical rules, and interpretation limitations.

## Key validated figures

- 46 plans and appeals: 23 humanitarian response plans, 9 regional response plans, 8 flash appeals, and 6 other plans
- USD 45.47 billion in requirements
- USD 15.59 billion in reported funding
- USD 29.88 billion in unmet requirements
- 34.29% overall funding coverage

## Data source

The project uses public 2025 plan and funding records from the [UN OCHA Humanitarian Programme Cycle API](https://api.hpc.tools/) and [Financial Tracking Service](https://fts.unocha.org/), retrieved on 13 August 2026. The exact API request URLs, response files, and transformation script used for the original extract were not retained; this repository's [`project/data/humanitarian_funding_2025.csv`](project/data/humanitarian_funding_2025.csv) is the reproducible analytical snapshot. Do not interpret a future API refresh as the same snapshot.

Language-code values (`en`, `es`, `fr`) that were accidentally loaded into `PlanType` were reconciled to `Humanitarian response plan`; regional, flash-appeal, and other plan categories remain unchanged.

The nine regional response plans are assigned the scope label `Regional / multi-country` and a blank ISO3. The prior extract attached each full regional requirement to one country, which falsely implied that the amount belonged to that country. The Country / Plan Scope slicer now shows regional plans separately; its country selections describe only plans with a country-level scope. Do not allocate regional totals across participating countries without a separate allocation source.


## Methodology and limitations

- Funding coverage equals reported funding divided by plan requirements.
- Unmet requirement equals the larger of plan requirements minus reported funding or zero. Portfolio unmet requirements therefore sum plan-level non-negative gaps.
- The priority index is a transparent portfolio construct used only to organise financial exposure; it is not an official OCHA indicator and does not measure severity, access, implementation capacity, or programme quality.
- FTS records are continually revised as new contributions are reported or corrected, so the dashboard represents the retrieval-date snapshot.
- Non-plan funding flows are excluded from plan-level comparisons.
- “Largest Unmet Requirements” is sorted by descending plan-level funding gap.

## Quality assurance

The packaged PBIP was validated for report structure, visual definitions, dataset row count, and reconciliation of requirements, funding, funding gap, and coverage before publication.

## Author

**Khalid SaadAldin Yahia**  
Data Analyst · Power BI · Python · SQL · Excel

## Open and inspect the report

- [Preview the dashboard PDF](Humanitarian_Funding_Triage_Dashboard.pdf). This PDF is a newly calculated, source-backed data preview; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/humanitarian-funding-triage/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`HumanitarianFundingTriage.pbip`](project/HumanitarianFundingTriage.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository at fixed commit `9177727ec8ee`. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.

### Reproducible data snapshot

The semantic model reads CSV files from immutable commit `9177727ec8ee8ad0b3aa6cf817e57703d445c0b2`. The same files are included in `project/data/` for inspection. Refreshing this project will not silently switch to a later `main` branch snapshot. To analyze newer data, update the CSV and source URL together and revalidate the measures and preview.
