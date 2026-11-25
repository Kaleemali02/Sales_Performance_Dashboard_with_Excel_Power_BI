# Power BI DAX Measures

Create these measures after loading `sales_performance_dataset.csv` (table name: `Sales`).

```DAX
Total Revenue = SUM(Sales[revenue])
Total Target = SUM(Sales[target])
Target Variance = [Total Revenue] - [Total Target]
Target Achievement % = DIVIDE([Total Revenue], [Total Target])
Total Units Sold = SUM(Sales[units_sold])
Average Discount % = AVERAGE(Sales[discount_pct]) / 100
Sales Records = COUNTROWS(Sales)
Distinct Products = DISTINCTCOUNT(Sales[product_id])
Distinct Sales Reps = DISTINCTCOUNT(Sales[sales_rep])
```

**Important:** `discount_pct` is stored as values such as 15.9, not 0.159. Divide its average by 100 for percentage display. Do not calculate profit or profit margin: neither field exists in the source dataset.
