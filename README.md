# 📊 Craster Sales Insights Dashboard

This project is a Power BI dashboard designed to analyze and visualize Craster's sales performance using multiple datasets. The dashboard provides actionable insights into revenue trends, product performance, and market dynamics to support strategic business decisions.

## 🧾 Key Features

- Interactive executive summary view
- Product-wise sales and profit analysis
- Trend forecasting and margin breakdown
- Market-level filtering and performance comparison
- Currency normalization for consistent analysis

## 🛠 Tools & Technologies

- Power BI
- DAX (Data Analysis Expressions)
- Power Query (ETL)
- Excel / CSV as data sources

## 📁 Files Included

- `Craster-sales-analysis-dashboard.pbix` – Main Power BI dashboard file
- `README.md` – Project overview and instructions
- `dashboard_screenshot.png` – Visual preview of the report

## 🔄 Normalization Logic

```powerbi
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] = "USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)
