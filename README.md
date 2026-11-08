# Sales & Financial Performance Dashboard — Power BI

An interactive Power BI dashboard built to analyze sales, profit, and discount performance across products, countries, and customer segments.

## 📁 Repository Contents

| File | Description |
|---|---|
| `finance_dashboard.pbit` | Power BI **template** file containing the full report/dashboard (visuals, layout, and data model). Opening it will prompt Power BI Desktop to load/refresh the underlying data source. |
| `sales_raw_data.xlsx` | Raw sales data (Orders, Customers, and Products) used as a data source for analysis. |

> **Note:** This is a Power BI **`.pbit` (template)** file, so it does not contain data on its own — it stores the report design, DAX measures, and query structure only. On first open, Power BI Desktop will ask you to supply/refresh the data source before the visuals populate.

## 📊 Dashboard Overview

The dashboard provides a single-page executive summary view with:

**KPI Cards**
- Total Sales
- Total Units Sold
- Total Profit
- Number of Countries

**Visuals**
- Bar Chart — Sales by Country
- Column Chart — Profit by Product
- Donut Chart — Sales by Segment
- Line Chart — Sales trend by Month
- Pie Chart — Units Sold by Product
- Area Chart — Profit by Country

**Interactive Slicers**
- Country
- Product
- Segment

These slicers let users filter every visual and KPI on the page simultaneously, enabling quick drill-down by market, product line, or customer segment.

## 🗂️ Data Model

The report's data model (`financials` table) includes the following fields:

| Column | Type | Description |
|---|---|---|
| Segment | Text | Customer segment |
| Country | Text | Country of sale |
| Product | Text | Product name |
| Discount Band | Text | Discount tier applied |
| Units Sold | Number | Quantity sold |
| Manufacturing Price | Number | Cost to manufacture per unit |
| Sale Price | Number | Price sold per unit |
| Gross Sales | Number | Revenue before discounts |
| Discounts | Number | Discount amount |
| Sales | Number | Net sales revenue |
| COGS | Number | Cost of goods sold |
| Profit | Number | Net profit |
| Date / Month Number / Month Name / Year | Date | Transaction date fields, also used to build a built-in Date table for time intelligence |

## 🧾 Raw Data (`sales_raw_data.xlsx`)

The included Excel workbook is a separate sample retail dataset with three sheets, useful for practicing data modeling/ETL in Power BI:

| Sheet | Rows | Key Columns |
|---|---|---|
| Orders | 1,200 | Order ID, Order/Ship Date, Ship Mode, Customer, Segment, Region, State, Category, Sub-Category, Product, Quantity, Unit Price, Discount, Sales, Profit |
| Customers | 150 | Customer ID, Name, Segment, Region, State |
| Products | 65 | Category, Sub-Category, Product Name, Unit Price |

Orders span **Jan 2023 – Dec 2024**, across 3 segments (Consumer, Corporate, Home Office), 4 regions, and 3 product categories.

> **Note:** `sales_raw_data.xlsx` is included as a separate practice/sample dataset and does not currently feed `finance_dashboard.pbit` — the dashboard shown above is built on its own `financials` data source (Country, Product, Segment, Sales, COGS, Profit, etc.). If you want a single connected pipeline, point the dashboard's Power Query source at data matching the `financials` schema instead.

## 🛠️ Tools Used

- **Power BI Desktop** — data modeling, DAX measures, report design
- **Power Query** — data transformation
- **Excel** — raw data source

## 🚀 How to Use

1. Clone or download this repository.
2. Open `finance_dashboard.pbit` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
3. When prompted, point the data source to `sales_raw_data.xlsx` (or your own dataset matching the `financials` schema above).
4. Let the data load, then explore the dashboard using the Country / Product / Segment slicers.
5. (Optional) Use **File → Save As** and choose `.pbix` if you want to save a version with data embedded.

## 📈 Key Metrics Tracked

- Total Sales & Total Profit
- Units Sold by Product
- Sales trend over time (by month)
- Profit and Sales distribution by Country and Segment

## 📌 Future Improvements

- Add a Profit Margin % measure and trend visual
- Add Year-over-Year / Month-over-Month comparison cards
- Expand to a multi-page report (Overview, Product Deep-Dive, Regional Analysis)
- Align the raw data schema with the dashboard's data model for a true end-to-end refreshable pipeline

## 📄 License

Feel free to use and adapt this project for learning purposes.
