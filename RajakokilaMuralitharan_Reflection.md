# Reflection — Global COVID-19 Health Equity and Recovery Analysis

## 1. What was the most difficult part of this project?

The most difficult part was preparing the dataset correctly before analysis. The raw Our World in Data COVID-19 dataset was large and contained many columns, missing values and aggregate rows. It was important to understand which records represented individual countries and which represented broader groups. The merge stage also required careful checking to ensure that no rows were lost or duplicated. Verifying that `daily_metrics` and the merged dataset both contained 402,910 rows was an important quality-control step.

## 2. What data-cleaning decision was most important?

The most important cleaning decision was removing rows where `continent` was missing for the main country-level analysis. These rows often represented aggregate locations such as world totals or income groups rather than individual countries. Keeping them would have distorted continent and country comparisons.

It was also important to fill missing `new_cases` and `new_deaths` with zero only where appropriate, while keeping missing country-profile indicators such as GDP per capita, hospital beds and Human Development Index as missing rather than inventing values.

## 3. Which pandas skill did you use most?

The pandas skills used most frequently were DataFrame filtering, `groupby()`, aggregation, sorting and missing-value checks. `groupby()` was particularly useful for creating continent summaries and monthly global case and death totals.

Other important methods included `dropna()`, `drop_duplicates()`, `fillna()`, `sort_values()`, `merge()`, `pivot_table()` and `crosstab()`.

## 4. Which chart best explained your findings?

The Global Monthly Reported New Cases line chart was one of the clearest visualisations because it showed how the reported COVID-19 burden changed over time. The chart clearly displayed several major waves rather than a constant pattern.

The deaths-per-million by continent box plot was also useful because it showed both regional differences and outlier countries, helping demonstrate that regional averages can hide substantial variation.

## 5. What would you improve with more time?

With more time, the analysis could include more detailed regional comparisons, additional health-system indicators and more advanced data-quality checks. I would also improve the presentation by adding a correlation heatmap, reusable Python functions and an additional dashboard-style regional comparison page.

A further improvement would be to investigate missing-data patterns in greater detail and compare reported outcomes across different phases of the pandemic. Any extended analysis would still remain descriptive and avoid unsupported causal conclusions.
