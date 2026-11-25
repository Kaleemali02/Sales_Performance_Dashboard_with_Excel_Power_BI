# Power BI DAX Measures

Assumed model table name: `Sales`. Rename the imported query to Sales or change the table name in each formula.

```DAX
Total Revenue = SUM(Sales[revenue])

Total Target = SUM(Sales[target])

Target Variance = [Total Revenue] - [Total Target]

Target Achievement % = DIVIDE([Total Revenue], [Total Target])

Total Units Sold = SUM(Sales[units_sold])

Average Discount % = DIVIDE(AVERAGE(Sales[discount_pct]), 100)

Sales Records = COUNTROWS(Sales)

Distinct Products = DISTINCTCOUNT(Sales[product_id])

Distinct Sales Reps = DISTINCTCOUNT(Sales[sales_rep])

Revenue Validation Failures =
CALCULATE(
    COUNTROWS(Sales),
    Sales[revenue_check] = FALSE()
)
```

Format `Target Achievement %` and `Average Discount %` as Percentage. Format revenue and target measures as currency (INR).

**Data notes**
- `discount_pct` is stored on a 0–100 scale (for example, 15.9 means 15.9%), so the average is divided by 100.
- Target achievement is total revenue divided by total target, not the average of row-level achievement percentages.
- Do not calculate profit or profit margin: cost/profit fields are not present in the source data.
