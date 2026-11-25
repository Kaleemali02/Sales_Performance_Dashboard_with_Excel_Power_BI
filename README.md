# Sales Performance Analysis | Excel & Power BI

**Author:** Kaleem Ali  
**Dataset:** 500 sales records, 1 Jan 2024 – 9 Apr 2024  
**Tools:** Microsoft Excel, Power BI, Power Query, DAX, Python (data preparation)

## Project overview
This refreshed project analyzes revenue and target performance across dates, regions, sales representatives, products, product categories, and discount levels. The replacement source dataset contains 500 records and 10 original fields. Derived fields include month, target variance, target achievement percentage, and discount band.

## Dataset fields
`date`, `region`, `sales_rep`, `product_id`, `category`, `units_sold`, `unit_price`, `revenue`, `target`, `discount_pct`.

The source does not include product cost, profit, customer identifiers, order identifiers, shipping dates, or customer satisfaction. Therefore this project does not report profit, profit margin, customer-level, order-level, or delivery-performance metrics.

## Headline metrics
- Total revenue: ₹112,403,305.67
- Total target: ₹112,509,362.47
- Target achievement: 99.91%
- Target variance: -₹106,056.80
- Units sold: 14,570
- Average row-level discount: 12.14%

## Analysis questions
1. How does monthly revenue compare with the monthly sales target?
2. Which region contributes the most revenue and which has the highest target achievement?
3. Which sales representatives lead on revenue and target achievement?
4. Which product categories contribute the most revenue and units sold?
5. Which products are the top revenue contributors?
6. How does revenue and target achievement vary across discount bands?

## Files in this repository
- [Cleaned dataset with derived fields](sales_performance_dataset.csv)
- [Power BI DAX measures](PowerBI_DAX_Measures.md)
- [Power BI setup and Power Query guide](PowerBI_Setup_Guide.md)
- [Monthly summary](monthly_sales_summary.csv)
- [Regional summary](regional_sales_summary.csv)
- [Sales representative summary](sales_rep_summary.csv)
- [Category summary](category_sales_summary.csv)
- [Product summary](product_sales_summary.csv)
- [Discount analysis summary](discount_analysis_summary.csv)

## Excel workbook and report
The companion project bundle contains the rebuilt Excel dashboard workbook and a PDF analysis report. The workbook includes a Dashboard sheet with five charts, a 500-row cleaned-data sheet, monthly, regional, representative, category, product and discount analysis sheets, plus a data dictionary.

## Power BI report layout
Recommended visuals: KPI cards for revenue, target, target achievement, target variance, units sold and average discount; monthly revenue-vs-target line chart; regional revenue bar chart; category revenue donut; sales-rep ranking; discount-band revenue chart. Add slicers for date, region, category and sales representative.

## Data quality notes
- 500 records; no missing values in the 10 source fields.
- No exact duplicate rows detected.
- Dates span 1 Jan 2024 through 9 Apr 2024.
- `discount_pct` uses a 0–100 scale (for example, 15.9 means 15.9%).
- Target achievement is calculated as total revenue divided by total target, not as the average of row-level percentages.

## Author
**Kaleem Ali** · [GitHub](https://github.com/Kaleemali02)
