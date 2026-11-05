# Global Layoffs Analysis (SQL + Python)

End-to-end analysis of 240K+ layoff records: data cleaning in SQL, trend analysis with CTEs and window functions, and a Python EDA script for charts.

## Key Findings
- Layoffs rose about **50% year over year** in the analysed period.
- The **US accounts for roughly 76%** of the records analysed.
- Post-IPO companies make up a large share of total layoffs.
- Industry-level trends were ranked per year using window functions (`DENSE_RANK`).

> Replace/confirm these numbers with your own query output before publishing. Add screenshots to `outputs/`.

## Tech Stack
SQL (MySQL), Python (Pandas, Matplotlib, Seaborn)

## Project Structure
```
global-layoffs-analysis/
├── data/                  # raw CSV (not committed, see data/README.md)
├── docs/data_dictionary.md
├── sql/
│   ├── 01_data_cleaning.sql
│   └── 02_exploratory_analysis.sql
├── src/eda.py
├── outputs/               # charts and screenshots
├── requirements.txt
└── LICENSE
```

## Workflow
1. **Clean** (`sql/01_data_cleaning.sql`): staging tables, remove duplicates with `ROW_NUMBER()`, standardize text (company, industry, country), convert dates, handle nulls, drop unusable rows.
2. **Explore** (`sql/02_exploratory_analysis.sql`): totals, top companies, yearly and monthly trends, rolling totals, top-5 companies per year.
3. **Visualize** (`src/eda.py`): charts for yearly trend, top industries, top countries.

## How to Run
```bash
git clone https://github.com/<your-username>/global-layoffs-analysis.git
cd global-layoffs-analysis
pip install -r requirements.txt
```
1. Download the dataset (see `data/README.md`) into `data/layoffs.csv`.
2. Import into MySQL as table `layoffs`, then run the SQL files in order.
3. Export the cleaned table to `data/layoffs_cleaned.csv`, then:
```bash
python src/eda.py --input data/layoffs_cleaned.csv
```

## Author
**Yuvaraj Kumar** | [LinkedIn](https://linkedin.com/in/yuvarajkumar-m) | yuvarajkumarm442@gmail.com
