# Humanitarian Funding Triage — local review changes

- Renamed the `Severity–Coverage Matrix` to `Requirements–Coverage Matrix` because its x-axis is plan requirements, not severity.
- Reconciled accidental language-code values (`en`, `es`, `fr`) in `PlanType` to `Humanitarian response plan` based on the affected country-plan records.
- Sorted the priority chart and action queue by `Priority Index` descending.
- Changed `Selected Plan` wording to `Current Selection` so the all-plans default is truthful.
- Moved the OCHA badge away from the plan slicer.
- Removed the phantom fifteenth CSV column from the semantic model and replaced the obsolete local CSV path with a `DataFolder` parameter.

The 46-plan totals were independently reconciled to $45.47B requirements, $15.59B reported funding, $29.88B non-negative gap, and 34.29% coverage. The gap is floored at zero for the overfunded Philippines plan, so it is not identical to portfolio requirements minus portfolio funding. A native PDF re-export still requires Power BI Desktop.
