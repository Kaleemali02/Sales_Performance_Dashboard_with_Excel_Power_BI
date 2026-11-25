# Power Query setup

1. In Power BI Desktop choose **Get Data → Text/CSV** and select `sales_performance_dataset.csv`.
2. Set `date` to Date; `region`, `sales_rep`, `product_id`, `category`, `month`, and `discount_band` to Text; `units_sold` to Whole Number; numeric money/percentage fields to Decimal Number.
3. Use the following M query in Advanced Editor if desired (update the file path).

```powerquery
let
    Source = Csv.Document(File.Contents("C:\\PATH\\sales_performance_dataset.csv"), [Delimiter=",", Encoding=65001, QuoteStyle=QuoteStyle.Csv]),
    PromotedHeaders = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    ChangedTypes = Table.TransformColumnTypes(PromotedHeaders, {
        {"date", type date}, {"region", type text}, {"sales_rep", type text},
        {"product_id", type text}, {"category", type text}, {"units_sold", Int64.Type},
        {"unit_price", type number}, {"revenue", type number}, {"target", type number},
        {"discount_pct", type number}, {"month", type text},
        {"target_variance", type number}, {"target_achievement_pct", type number},
        {"discount_band", type text}
    })
in
    ChangedTypes
```

## Suggested report layout
- KPI cards: Total Revenue, Total Target, Target Achievement %, Target Variance, Units Sold, Average Discount %.
- Line chart: monthly Revenue and Target.
- Clustered bar: Revenue by Region.
- Donut: Revenue by Category.
- Bar: Revenue by Sales Representative (Top N = 10).
- Column chart: Revenue by Discount Band.
- Matrix: Category × Region with Revenue, Target, Target Achievement %.
- Slicers: Date, Region, Category, Sales Rep.

Use a date hierarchy or a dedicated calendar table for time intelligence if you extend the dataset beyond the current period.
