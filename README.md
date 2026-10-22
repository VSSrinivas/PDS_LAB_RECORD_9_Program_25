# Scala Data Analysis Exercises (Weeks 13-14)

A collection of four Scala exercise programs covering case classes, data manipulation, numerical computing, exact arithmetic and interactive visualization.

| # | Program | Week | Libraries | Output |
|---|---------|------|-----------|--------|
| 22 | `Program22_CaseClasses.scala` | 13 | Scala standard library | Console |
| 23 | `Program23_SaddleVegas.scala` | 13 | Saddle 1.3.4, Vegas 0.3.11 | `apple_price_trend.html` |
| 24 | `Program24_BreezePlotly.scala` | 14 | Breeze 0.13.2, plotly-scala 0.5.4 | `fruit_revenue.html` |
| 25 | `Program25_SpireSaddleVegas.scala` | 14 | Spire 0.13.0, Saddle 1.3.4, Vegas 0.3.11 | `fruit_price_trends.html` |

**Scala version:** 2.11 for all programs.

---

## Program 22: Case Classes in Scala
Defines a `Person(name, age, city)` case class and builds a list of five people. Demonstrates functional collection operations:
- Filter people older than 30
- Group people by city (`groupBy`)
- Transform each person into a descriptive string (`map`)
- Sort people by age in ascending order (`sortBy`)

## Program 23: Data Manipulation with Saddle and Visualization with Vegas
Loads `fruit_prices.csv` into a Saddle `Frame` and works with typed `Series` for Date, Fruit, Price and Quantity.
- Prints dataset shape, column names and the first 8 records
- Filters the Apple records
- Computes the number of records, and the average, minimum and maximum apple price
- Plots the apple price trend over time as an interactive Vega-Lite line chart, saved to `apple_price_trend.html`

## Program 24: Revenue Analysis with Breeze and Plotly-Scala
Reads the fruit dataset and stores Price and Quantity as Breeze `DenseVector`s.
- Computes revenue for every record using element-wise multiplication (`price *:* qty`)
- Computes total revenue per fruit using a 0/1 mask and dot product
- Reports overall revenue and the highest-revenue fruit
- Creates an interactive bar chart of total revenue by fruit type with Plotly-Scala, saved to `fruit_revenue.html`

## Program 25: Fruit Price Statistics with Spire, Saddle and Vegas
Loads the dataset with Saddle and groups prices by fruit.
- Calculates mean, variance and standard deviation per fruit using Spire `Rational` numbers (exact arithmetic, no floating-point rounding)
- Prints the exact rational mean and variance for Apple
- Plots the price trend of every fruit over time as a multi-line Vega-Lite chart, saved to `fruit_price_trends.html`

---

## Dataset
Programs 23-25 read `fruit_prices.csv` from the working directory. Expected columns:

```
Date, Fruit, Price, Quantity
```

## How to Run
1. Install Scala 2.11 and sbt, and add the required libraries to `build.sbt`.
2. Place `fruit_prices.csv` in the project root.
3. Run a program, for example:
   ```
   sbt "runMain Program23_SaddleVegas"
   ```
4. Open the generated `.html` file in a browser to view the interactive chart.
