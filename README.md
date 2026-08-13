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

## Open the project

Download and extract `Humanitarian_Funding_Triage_PBIP.zip`, then open `HumanitarianFundingTriage.pbip` in a recent version of Power BI Desktop. The included CSV is the reproducible source snapshot used by the semantic model.

## Methodology and limitations

- Funding coverage equals reported funding divided by plan requirements.
- Unmet requirement equals plan requirements minus reported funding.
- The priority index is a transparent portfolio construct used only to organise financial exposure; it is not an official OCHA indicator and does not measure severity, access, implementation capacity, or programme quality.
- FTS records are continually revised as new contributions are reported or corrected, so the dashboard represents the retrieval-date snapshot.
- Non-plan funding flows are excluded from plan-level comparisons.

## Quality assurance

The packaged PBIP was validated for report structure, visual definitions, dataset row count, and reconciliation of requirements, funding, funding gap, and coverage before publication.

Created by **Khalid Saadaldin Yahia**.
