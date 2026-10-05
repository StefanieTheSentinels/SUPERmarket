# Supermarket Sales Analysis

Exploratory data analysis of **1000 supermarket transactions** across three branches in Myanmar (Yangon, Mandalay, Naypyitaw), using **pandas** and **Plotly**.

## Key findings

- **Naypyitaw** leads in total sales for both `Member` and `Normal` customer types.
- **Unit price has no clear effect on quantity sold** — the LOWESS trendline is essentially flat.
- **Customer rating is independent** of total, gross income, and payment method.
- Sales volume is roughly balanced across product lines, with `Food and beverages` slightly ahead.
- Member vs. Normal split is nearly even within each gender.

## Dataset

| | |
|---|---|
| Rows | 1000 |
| Columns | 17 |
| Period | Jan–Mar 2019 |
| Branches | Yangon, Mandalay, Naypyitaw |
| Source | [Kaggle: Supermarket sales](https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales) |

Columns: `Invoice ID`, `Branch`, `City`, `Customer type`, `Gender`, `Product line`, `Unit price`, `Quantity`, `Tax 5%`, `Total`, `Date`, `Time`, `Payment`, `cogs`, `gross margin percentage`, `gross income`, `Rating`.

## Project structure

```
.
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   └── supermarket_sales.csv
├── notebooks/
│   └── analysis.ipynb
└── assets/                 # static PNG exports of plots for the README
```

## Setup

```bash
git clone https://github.com/<you>/supermarket-sales-analysis.git
cd supermarket-sales-analysis
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/analysis.ipynb
```

## Viewing the notebook

GitHub renders `.ipynb` files but strips interactive Plotly output. For the full interactive version, open the notebook via **[nbviewer](https://nbviewer.org/)**.

## Sections in the notebook

1. **Descriptive statistics** — mean, median, std across numeric fields.
2. **Data cleanup** — null checks, rounding, dropping redundant columns.
3. **Plots** — sales by product line, city, payment method, customer type.
4. **Detailed overview** — sunburst (city → product line), 3D scatter (date × time × total) per city, average sales per half-hour window.
5. **Data transformation** — derived ratios (`Price/Rating`, `Total/Quantity`).
6. **Hypotheses** — tested against the data with supporting visualizations.

