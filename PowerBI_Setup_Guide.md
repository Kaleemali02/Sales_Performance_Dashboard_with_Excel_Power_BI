# Power BI setup guide

## 1. Import the dataset
1. Open Power BI Desktop.
2. Select **Home → Get data → Text/CSV**.
3. Choose `cleaned_sales_dataset.csv` from this repository.
4. Select **Transform Data**.

## 2. Set column data types
The actual CSV contains these columns:

| Column | Data type |
|---|---|
| date | Date |
| region | Text |
| sales_rep | Text |
| product_id | Text |
| category | Text |
| units_sold | Whole number |
| unit_price | Decimal number |
| revenue | Decimal number |
| target | Decimal number |
| discount_pct | Decimal number |
| revenue_check | True/False |

Do not add references to `month`, `target_variance`, `target_achievement_pct` or `discount_band` unless you create those columns yourself. The supplied CSV does not contain them.

## 3. Optional Power Query M
Update the path to your local CSV file.

```powerquery
let
    Source = Csv.Document(
        File.Contents("C:\\YOUR_FOLDER\\cleaned_sales_dataset.csv"),
        [Delimiter=",", Encoding=65001, QuoteStyle=QuoteStyle.Csv]
    ),
    PromotedHeaders = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    ChangedTypes = Table.TransformColumnTypes(PromotedHeaders, {
        {"date", type date},
        {"region", type text},
        {"sales_rep", type text},
        {"product_id", type text},
        {"category", type text},
        {"units_sold", Int64.Type},
        {"unit_price", type number},
        {"revenue", type number},
        {"target", type number},
        {"discount_pct", type number},
        {"revenue_check", type logical}
    })
in
    ChangedTypes
```

## 4. Create a month column
In Power Query, add a custom column:

```powerquery
Date.ToText([date], "yyyy-MM")
```

Name it `month`. Optionally create a discount band using a conditional column based on `discount_pct`; document the thresholds you choose.

## 5. Add DAX measures
Use the measures in [PowerBI_DAX_Measures.md](PowerBI_DAX_Measures.md). The source table name in the examples is `Sales`; rename the imported query to `Sales` or update the DAX table references.

## 6. Recommended visuals
- KPI cards: Total Revenue, Total Target, Target Achievement %, Target Variance, Total Units Sold, Average Discount %.
- Line chart: monthly Revenue and Target.
- Bar chart: Revenue by Region.
- Donut chart: Revenue by Category.
- Bar chart: Revenue by Sales Representative.
- Column chart: Revenue by Discount Band (after creating the band).
- Matrix: Category by Region with Revenue and Target.

Add slicers for date, region, category and sales representative.

## 7. Final validation checklist
- Refresh completes without errors.
- Total revenue equals ₹112,403,305.67.
- Total target equals ₹112,509,362.47.
- Total units sold equals 14,570.
- All 500 rows have `revenue_check = TRUE`.
- Each visual responds to the slicers.
- Save the finished report as `PowerBI_Report.pbix`.
