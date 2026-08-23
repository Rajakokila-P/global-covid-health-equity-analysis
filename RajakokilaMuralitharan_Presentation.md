# Slide 1 — Title
Global COVID-19 Health Equity and Recovery Analysis  
Prepared by: Rajakokila Muralitharan  
Role: Junior Data Analyst  

# Slide 2 — Project Scenario
Purpose: Analyse global COVID-19 data to support public-health recovery monitoring.  
Stakeholder: Global Health and Development Analytics Unit.  
Main question: How did reported COVID-19 burden differ across countries and continents?

# Slide 3 — Dataset Overview
Dataset: Our World in Data Complete COVID-19 Dataset  
Format: CSV  
Raw data: 429,435 rows and 67 columns  
Cleaned country-level data: 402,910 records  
Main fields: location, continent, date, cases, deaths, population, GDP per capita, hospital beds and HDI.

# Slide 4 — Methodology
Loaded CSV in pandas.  
Inspected shape, columns, data types and missing values.  
Selected relevant columns.  
Cleaned country-level records.  
Created calculated columns.  
Merged daily metrics with country profile data.  
Created grouped summaries, pivot table, crosstab and charts.

# Slide 5 — Data Cleaning Summary
Removed aggregate rows where continent was missing.  
Filled missing new_cases and new_deaths where suitable.  
Kept missing country-profile indicators as missing.  
Converted date to datetime.  
Created case fatality rate, per-million fields and year_month.

# Slide 6 — Key Finding 1: Regional Burden
Reported COVID-19 burden differed considerably by continent.  
Europe showed one of the highest reported total mortality burdens.  
Total counts should be reviewed alongside population-adjusted indicators.

# Slide 7 — Key Finding 2: Time Trends
Global monthly reported cases and deaths changed in clear waves.  
Cases rose strongly around 2021–2022.  
Deaths peaked earlier and then generally declined over time.

# Slide 8 — Key Finding 3: Country-Level Rates
Deaths per million varied strongly between countries.  
Some countries were clear outliers compared with regional averages.  
Population-adjusted rates support fairer country comparison.

# Slide 9 — Recommendations
Use cases and deaths per million alongside total counts.  
Prioritise countries with unusually high deaths per million.  
Maintain monthly trend monitoring.  
Record data-quality limitations in management reporting.

# Slide 10 — Limitations and Conclusion
Reported data depends on testing, reporting systems and delays.  
Missing profile indicators affect comparison.  
This is descriptive analysis and does not prove causation.  
Conclusion: Recovery monitoring should combine population-adjusted indicators, monthly trends and transparent data-quality notes.