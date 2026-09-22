# Retail Sales KPI & Data Quality Contract

## Dataset
Primary source: `data/sales_data.csv`

The supplied primary file has 2 records and the columns `Date, Product, Category, Region, Units, Revenue`.

## Decision ownership
- Business KPI owner: Sales Manager
- Data quality escalation: Data/Analytics Owner

## Rules and thresholds

| Dimension | Rule | Failure threshold | Action |
|---|---|---|---|
| Completeness | Required fields are not null | Any missing required value | Flag and correct before KPI publication |
| Uniqueness | No duplicate sales rows | Any duplicate row | Quarantine duplicate and investigate |
| Validity | Date parses; Units > 0; Revenue >= 0 | Any invalid record | Hold/reject invalid record and investigate |
| Consistency | Product, Category and Region are non-blank and standardized | Any blank/inconsistent value | Flag for correction |
| Freshness | Data is refreshed daily | Age > 1 day | Raise freshness alert and escalate |

## Current supplied data
- Records: 2
- Total Revenue: 342000
- Total Units: 60
- Products: 2
- Regions: 2
- Latest record date: 2026-01-12
- Reference date: 2026-09-17
- Daily freshness: FAIL because the supplied data is older than one day relative to the reference date.

## Important schema issue
The second supplied file, `my_sales_data.csv`, uses `Data` instead of `Date` and `Catergory` instead of `Category`. This is a schema/header-quality issue. The primary file `sales_data.csv` is used for KPI calculations because its headers are correctly spelled.

## Publication and escalation
1. Run the notebook after each refresh.
2. If completeness, uniqueness, validity or consistency fails, do not publish affected KPIs until corrected or an exception is documented.
3. If freshness fails, alert the Data/Analytics Owner and Sales Manager.
4. Record the corrective action and rerun the checks.
