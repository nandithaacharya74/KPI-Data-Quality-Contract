# KPI Dictionary & Data Quality Contract

Built from the two supplied sales CSV files.

## Deliverables
- `KPI_Dictionary.xlsx` — 10 KPI definitions plus data dictionary and quality summary.
- `data_quality_profile.ipynb` — executable data-quality checks and KPI calculations.
- `data_quality_contract.md` — rules, thresholds and escalation actions.
- `data/sales_data.csv` — primary supplied dataset.
- `data/my_sales_data.csv` — second supplied dataset; retained to document header inconsistencies.

## Run the notebook
```bash
pip install pandas notebook
jupyter notebook
```
Open `data_quality_profile.ipynb` and choose **Run All**.

## Note
The supplied datasets contain only 2 records. Therefore, the deliverables are valid for demonstrating the task workflow, but the KPI results will change when a larger raw retail dataset is supplied.
