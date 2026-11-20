# DAX Measures

Total Net Sales = SUM('Pakistan_Pharmaceutical_Sales_2023_2026'[Net_Sales_PKR])

Total Net Profit = SUM('Pakistan_Pharmaceutical_Sales_2023_2026'[Profit_PKR])

Profit Margin % = 
DIVIDE(
    [Total Net Profit],
    [Total Net Sales],
    0
)

Total Units Sold = SUM('Pakistan_Pharmaceutical_Sales_2023_2026'[Units_Sold])

Previous Year Sales = 
CALCULATE([Total Net Sales], SAMEPERIODLASTYEAR('Date'[Date]))

YoY Sales Growth % = 
VAR Prev = [Previous Year Sales]
VAR OneYear = HASONEVALUE('Date'[Year])
RETURN
    IF(
        OneYear && NOT ISBLANK(Prev),
        DIVIDE([Total Net Sales] - Prev, Prev)
    )