
# 📊 DAX Measures for Superstore Dashboard

## ✅ Total Sales
```DAX
Total Sales = SUM('Superstore'[Sales])
```

## ✅ Total Profit
```DAX
Total Profit = SUM('Superstore'[Profit])
```

## ✅ Total Orders (Distinct)
```DAX
Total Orders = DISTINCTCOUNT('Superstore'[Order ID])
```

## ✅ Profit Margin (%)
```DAX
Profit Margin = 
DIVIDE(SUM('Superstore'[Profit]), SUM('Superstore'[Sales]), 0)
```
_Format as Percentage (%)_

## ✅ Sales Last Year
```DAX
Sales LY = 
CALCULATE(
    SUM('Superstore'[Sales]),
    SAMEPERIODLASTYEAR('Superstore'[Order Date])
)
```

## ✅ Sales Growth % (YoY)
```DAX
Sales Growth % = 
DIVIDE(SUM('Superstore'[Sales]) - [Sales LY], [Sales LY], 0)
```
_Format as Percentage (%)_

## ✅ Profit Last Year (Optional)
```DAX
Profit LY = 
CALCULATE(
    SUM('Superstore'[Profit]),
    SAMEPERIODLASTYEAR('Superstore'[Order Date])
)
```

## ✅ Profit Growth % (Optional)
```DAX
Profit Growth % = 
DIVIDE(SUM('Superstore'[Profit]) - [Profit LY], [Profit LY], 0)
```
_Format as Percentage (%)_

## 🔥 Note:
- Replace 'Superstore' with your dataset name if different.
- Make sure Order Date is a valid Date column.
