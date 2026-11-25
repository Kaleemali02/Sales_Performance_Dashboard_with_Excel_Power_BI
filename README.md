# Sales Performance Analysis | Excel & Power BI

**Author:** Kaleem Ali  
**Dataset:** 500 sales records, 1 Jan 2024 – 9 Apr 2024  
**Tools:** Microsoft Excel, Power BI, Power Query, DAX, Python (data preparation)

## Project overview
This project analyzes revenue and target performance across dates, regions, sales representatives, products, product categories, and discount levels. The replacement source dataset contains 500 records and 10 original fields. Derived fields include month, target variance, target achievement percentage, and discount band.

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
- [Power BI DAX measures](PowerBI_DAX_Measures.md)
- [Power BI setup guide](PowerBI_Setup_Guide.md)
- [Monthly sales summary](monthly_sales_summary.csv)
- [Regional sales summary](regional_sales_summary.csv)
- [Sales representative summary](sales_rep_summary.csv)
- [Category sales summary](category_sales_summary.csv)
- [Product sales summary](product_sales_summary.csv)
- [Discount analysis summary](discount_analysis_summary.csv)

## Companion project files
The rebuilt Excel workbook and PDF analysis report were generated separately. They are available in the project bundle supplied in this conversation. The current GitHub connection supports text-file commits, but does not provide a binary-file upload action for `.xlsx`, `.pdf`, or `.zip` files; those files have therefore not been committed to this repository.

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
