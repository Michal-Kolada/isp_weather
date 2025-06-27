# Weather Data Analysis Results for Warsaw

This file presents the results of weather data analysis for Warsaw, based on data fetched from the Open-Meteo API and processed using Apache Spark and Pandas. The goal was to analyze meteorological conditions in Warsaw over recent months using hourly, weekly, and monthly aggregations, with visualizations and comparisons of key weather indicators.

## Used Libraries and Environment

The code was executed in a PySpark environment, which enabled efficient processing of large datasets directly within the notebook. The following tools were used:
- `pyspark` – for CSV reading and basic data transformation,
- `pandas` – for more advanced manipulation and statistics,
- `matplotlib` – for creating plots and heatmaps,
- `numpy` – for supporting numerical operations.

The data was read from three CSV files: hourly (`hourly`), weekly (`weekly`), and monthly (`monthly`). Example configuration:

```python
hourly_sdf = (spark.read.options(**read_opts)
                        .csv(f"{PREFIX}/warsaw_weather_hourly.csv")
                        .withColumn("time", to_timestamp("time")))
```

After conversion to Pandas DataFrames, data was sorted, filtered, and prepared for visualization and statistical analysis.

## Data Analysis and Visualization

### 1. Weekly Average Temperature Heatmap

The heatmap shows weekly average temperatures over the past 13 months, grouped by weeks within each month. This helps to observe seasonal trends, temperature spikes, and stability in weather conditions.

![avg temp heatmap](./images/heatmap.png)

---

### 2. Monthly Trends (last year)

This visualization shows changes in temperature, precipitation, and wind speed on a monthly basis. For each variable, minimum, maximum, and average values are presented.

![monthly](./images/monthl.png)

Code fragment used for plotting:

```python
plot_trends(monthly_df, "Monthly (last year)")
```

---

### 3. Weekly Trends (last month)

Similar to the monthly analysis, this chart presents data from the last 5 weeks. It allows a closer look at short-term weather trends, particularly useful during spring and summer.

![weekly](./images/weekly.png)

---

### 4. Hourly Trends (June 24, 2025)

This visualization captures weather conditions on an hourly basis for a single day – showing fluctuations in temperature, rainfall, and wind speed from morning to evening.

![hourly](./images/hourly.png)

---

### 5. Comparison: Monthly vs Weekly

This chart compares monthly and weekly data for temperature, precipitation, and wind speed. It helps to identify differences and variability across different levels of data aggregation.

![copmarison](./images/copmarison.png)

Code used for comparison:

```python
compare_monthly_weekly(monthly_df, weekly_full_year_df)
```

---

## Summary

This complete analysis provides a full picture of atmospheric conditions in Warsaw – from granular hourly data to high-level monthly overviews. Using Spark and Pandas for data processing, followed by visualization in Matplotlib, enabled the creation of clear and informative charts.
