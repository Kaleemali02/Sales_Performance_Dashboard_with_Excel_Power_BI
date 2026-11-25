# Sales Performance Analysis Dashboard

**Author:** Kaleem Ali  
**Tools:** Microsoft Excel, Power BI, Power Query, DAX, Python  
**Dataset:** 500 sales records | 1 January 2024 – 9 April 2024

## Project overview
An end-to-end sales performance analysis of revenue and target attainment across time, regions, sales representatives, product categories, products and discount levels.

The repository includes the validated source data, summary extracts, Power BI report file, DAX measures and setup instructions. The Power BI file is named `PowerBI_Report.pbix`. Open it in Power BI Desktop and refresh the source using the included CSV. Confirm the report pages and visuals render correctly in your local Power BI Desktop version before presenting it as a finished report.

## Business questions
1. How does revenue compare with target over time?
2. Which regions contribute the most revenue and achieve their targets?
3. Which sales representatives lead on revenue?
4. Which categories and products contribute the most revenue?
5. How does revenue vary by discount band?

## Dataset
File: [cleaned_sales_dataset.csv](cleaned_sales_dataset.csv)

Columns: `date`, `region`, `sales_rep`, `product_id`, `category`, `units_sold`, `unit_price`, `revenue`, `target`, `discount_pct`, `revenue_check`.

The `revenue_check` column is a validation flag confirming whether `units_sold × unit_price = revenue`. It is not a business KPI.

## Headline KPIs
| KPI | Value |
|---|---:|
| Total revenue | ₹112,403,305.67 |
| Total target | ₹112,509,362.47 |
| Target achievement | 99.91% |
| Target variance | -₹106,056.80 |
| Units sold | 14,570 |
| Average row-level discount | 12.14% |
| Sales records | 500 |

Target achievement is calculated as total revenue divided by total target. Average discount is the arithmetic mean of row-level discount percentages.

## Repository contents
- [PowerBI_Report.pbix](PowerBI_Report.pbix) — Power BI report file (verify refresh and visuals in Power BI Desktop).
- [cleaned_sales_dataset.csv](cleaned_sales_dataset.csv) — validated 500-row source dataset.
- [PowerBI_DAX_Measures.md](PowerBI_DAX_Measures.md) — DAX measure definitions.
- [PowerBI_Setup_Guide.md](PowerBI_Setup_Guide.md) — data import, model and visual setup.
- [monthly_sales_summary.csv](monthly_sales_summary.csv)
- [regional_sales_summary.csv](regional_sales_summary.csv)
- [sales_rep_summary.csv](sales_rep_summary.csv)
- [category_sales_summary.csv](category_sales_summary.csv)
- [product_sales_summary.csv](product_sales_summary.csv)
- [discount_analysis_summary.csv](discount_analysis_summary.csv)

## Recommended report pages
1. **Executive Overview:** KPI cards, monthly revenue vs target, region revenue.
2. **Product & Category:** category contribution, top products, units sold.
3. **Regional Performance:** revenue and target attainment by region.
4. **Sales Representatives:** revenue ranking and target attainment.
5. **Discount Analysis:** revenue and average discount by discount band.

Recommended slicers: date, region, category and sales representative.

## Data quality and limitations
- 500 rows; no missing values in the 10 original business fields.
- No exact duplicate rows detected.
- Revenue calculation was validated for all 500 records.
- Dates cover 1 January 2024 through 9 April 2024.
- `discount_pct` is stored on a 0–100 scale (e.g. 15.9 means 15.9%).
- The dataset does not contain product cost, profit, customer IDs, order IDs, shipping dates or customer satisfaction. This project therefore does not claim profit, margin, customer, order or delivery metrics.

## Important validation note
A PBIX file is present in this repository, but the GitHub connection cannot render or inspect Power BI binary report contents. Verify that the report is genuinely built from this dataset, that visuals are populated, and that refresh succeeds before using screenshots or describing the PBIX as fully validated.

## Author
Kaleem Ali · [GitHub profile](https://github.com/Kaleemali02)
