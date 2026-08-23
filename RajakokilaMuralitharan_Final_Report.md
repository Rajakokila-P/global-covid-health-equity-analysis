# Global COVID-19 Health Equity and Recovery Analysis

**Student Name:** Rajakokila Muralitharan
**Role:** Junior Data Analyst
**Organisation:** Global Health and Development Analytics Unit
**Software:** Python, pandas, Matplotlib, Seaborn and Jupyter Notebook in VS Code
**Dataset:** Our World in Data Complete COVID-19 Dataset

---

## 1. Executive Summary

This report analyses the Our World in Data Complete COVID-19 Dataset to identify differences in reported COVID-19 burden across countries and continents and to support public-health recovery monitoring. The project was completed using Python and pandas, following a structured workflow of data inspection, cleaning, calculated fields, data merging, grouped summaries, pivot reporting, crosstabs and visualisation.

The raw dataset contained approximately **429,435 rows and 67 columns**. After selecting relevant variables and removing non-country aggregate records where continent information was unavailable, the main country-level analysis contained **402,910 records**. The analysis identified substantial regional and country-level variation in reported COVID-19 cases, deaths and population-adjusted mortality rates.

Europe showed one of the highest reported total mortality burdens in the continent-level analysis, while the deaths-per-million analysis showed considerable variation both within and between continents. Global monthly trends also demonstrated distinct waves of reported cases and deaths rather than a constant burden over time.

The analysis recommends continued use of population-adjusted indicators, regular monthly monitoring, targeted review of countries with unusually high reported mortality rates and careful documentation of missing or incomplete country-profile data.

---

## 2. Project Background

COVID-19 affected countries and regions differently. Some countries reported very large numbers of cases and deaths, while others reported lower totals or incomplete information. Differences in population size, testing capacity, national reporting systems and health-system characteristics can also affect cross-country comparisons.

The purpose of this project was to support a fictional United Nations-style **Global Health and Development Analytics Unit** by producing descriptive evidence for programme managers, public-health monitoring teams, development policy officers and humanitarian coordination teams. The project focuses on identifying patterns, data-quality risks and areas that may require further investigation rather than making medical or causal conclusions.

The main policy question was:

**How did COVID-19 health outcomes differ across countries and continents, and what basic data-driven recommendations can support public-health recovery planning?**

---

## 3. Dataset Overview

The project used the **Our World in Data Complete COVID-19 Dataset**, a public international dataset containing one row per location and date.

| Item                                  | Description                                                                                                            |
| ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Dataset                               | Our World in Data Complete COVID-19 Dataset                                                                            |
| Source                                | Our World in Data                                                                                                      |
| File type                             | CSV                                                                                                                    |
| Raw records                           | Approximately 429,435                                                                                                  |
| Raw columns                           | 67                                                                                                                     |
| Country-level records after filtering | 402,910                                                                                                                |
| Unit of record                        | Location and date                                                                                                      |
| Main analysis fields                  | Cases, deaths, population, continent, date, GDP per capita, hospital beds, life expectancy and Human Development Index |

The project focused on fields including `iso_code`, `continent`, `location`, `date`, `total_cases`, `new_cases`, `total_deaths`, `new_deaths`, population-adjusted measures and country-profile indicators. These fields are specifically identified as relevant to the assignment.

---

## 4. Methodology

The analysis followed a structured junior data analyst workflow.

First, the CSV dataset was loaded into pandas and inspected using `head()`, `shape`, `columns`, `info()`, `describe()` and missing-value summaries. This established the structure of the dataset and identified variables with substantial missing information.

The dataset was then reduced to the project-relevant variables. Country-level analysis excluded rows where `continent` was missing, which removed aggregate records such as global or income-group observations. Exact duplicates were checked and removed where necessary. Missing daily `new_cases` and `new_deaths` values were filled with zero where appropriate for aggregation, while missing country-profile indicators were retained as missing because they represented unavailable information rather than confirmed zero values. These cleaning principles follow the assessment requirements.

The `date` field was converted to datetime format, and four calculated fields were created:

* `case_fatality_rate`
* `new_cases_per_million_custom`
* `new_deaths_per_million_custom`
* `year_month`

These calculated columns were compulsory elements of the assignment.

Two smaller DataFrames were then created:

* `daily_metrics` for daily COVID-19 measures
* `country_profile` for country-level development information

A left join merged these tables on `iso_code`, `location` and `continent`. The merge preserved all **402,910 daily records**, confirming that the join did not lose or duplicate daily observations.

Grouped summaries, Top 10 country tables, a monthly global summary, a continent-by-month pivot table and a continent-by-burden crosstab were then produced. Finally, six charts were developed and interpreted.

---

## 5. Data Cleaning Summary

| Cleaning Step                       | Action Taken           | Reason                                                      |
| ----------------------------------- | ---------------------- | ----------------------------------------------------------- |
| Selected relevant columns           | Yes                    | Reduced the dataset to fields required for analysis         |
| Removed rows with missing continent | Yes                    | Removed aggregate/non-country records from country analysis |
| Converted date field                | Yes                    | Enabled time-series and monthly analysis                    |
| Checked exact duplicates            | Yes                    | Prevented repeated records affecting results                |
| Filled missing `new_cases`          | Yes, where appropriate | Supported daily/monthly aggregation                         |
| Filled missing `new_deaths`         | Yes, where appropriate | Supported daily/monthly aggregation                         |
| Kept missing profile indicators     | Yes                    | Missing profile data represents unavailable information     |
| Created calculated fields           | Yes                    | Supported rate and monthly analysis                         |
| Exported cleaned dataset            | Yes                    | Required final project deliverable                          |

The initial inspection showed particularly high levels of missing information in specialist fields such as ICU and excess-mortality measures. Core identification fields were substantially more complete.

Country-profile indicators such as GDP per capita, hospital beds, median age and Human Development Index also contained missing values. These values were not artificially replaced.

---

## 6. Key Findings

### Finding 1 — Reported COVID-19 burden differed considerably by continent

**Insight:**
The continent-level summary showed large differences in total reported COVID-19 cases and deaths across regions. Europe recorded one of the highest reported total mortality burdens in the latest-country analysis, followed by other highly affected regions including North and South America.

**Evidence:**
Continent Summary table and *Reported Total Deaths by Continent* bar chart.

**Why it matters:**
Regional differences can help programme managers identify where additional monitoring and deeper country-level investigation may be appropriate. Total counts should, however, be interpreted alongside population-adjusted indicators.

---

### Finding 2 — Population-adjusted indicators provide a more useful basis for country comparison

**Insight:**
Countries with the highest total number of cases or deaths are not necessarily the countries with the highest rates per million people.

**Evidence:**
Top 10 Cases per Million and Top 10 Deaths per Million tables.

**Why it matters:**
Using population-adjusted rates reduces the distortion created by large differences in national population size and allows policy teams to make more meaningful comparisons.

---

### Finding 3 — Global reported cases occurred in distinct waves

**Insight:**
The monthly global new-cases chart showed several pronounced increases rather than a constant level of reported infections. A particularly large rise occurred during the 2021–2022 period.

**Evidence:**
*Global Monthly Reported New Cases* line chart.

**Why it matters:**
Monthly monitoring can help policy teams identify major changes in reported disease burden and periods where additional programme capacity or surveillance attention may be required.

---

### Finding 4 — Global reported deaths declined after major pandemic peaks

**Insight:**
The monthly deaths analysis showed large mortality peaks during earlier pandemic periods, particularly around 2021, followed by an overall decline.

**Evidence:**
*Global Monthly Reported New Deaths* line chart.

**Why it matters:**
The trend provides useful information for recovery monitoring, although differences in national reporting quality and timing must be considered.

---

### Finding 5 — Reported deaths per million vary considerably within and between regions

**Insight:**
The distribution of deaths per million was strongly right-skewed. Most countries were concentrated at lower levels, while a smaller number recorded much higher reported mortality rates.

The continent box plot also showed clear regional variation. Europe and South America displayed comparatively high central values, while Africa and parts of Asia showed lower reported values.

**Evidence:**
*Distribution of Reported Deaths per Million* histogram and *Reported Deaths per Million by Continent* box plot.

**Why it matters:**
Regional averages can hide substantial country-level variation. Outlier countries may therefore require specific investigation rather than being assessed only through regional averages.

---

### Finding 6 — GDP per capita does not completely explain differences in reported COVID-19 mortality

**Insight:**
The GDP-per-capita scatter plot showed considerable variation in deaths per million at similar economic levels. There was no simple relationship showing that GDP per capita alone determines reported mortality.

**Evidence:**
*GDP per Capita vs Reported Deaths per Million* scatter plot.

**Why it matters:**
Economic development should be considered alongside health-system capacity, demographic structure, reporting practices and other contextual factors. The relationship identified in this project is descriptive and must not be interpreted as causal. The assignment specifically requires students to avoid unsupported causal claims.

---

## 7. Summary Tables Produced

The following analytical tables were created and exported:

1. Missing-value summary
2. Continent-level summary
3. Top 10 countries by cases per million
4. Top 10 countries by deaths per million
5. Monthly global cases and deaths summary
6. Continent-by-month cases pivot table
7. Continent-by-burden-category crosstab

The assignment requires grouped summaries, a pivot table and crosstab as part of the full analytical workflow.

---

## 8. Visualisations

Six principal charts were produced:

### Chart 1 — Reported Total Deaths by Continent

The chart shows considerable differences in total reported mortality between regions. Total counts should be considered together with population-adjusted indicators because continental population sizes differ substantially.

### Chart 2 — Global Monthly Reported New Cases

The time series shows repeated waves of reported cases, including a particularly large increase around the 2021–2022 period.

### Chart 3 — Global Monthly Reported New Deaths

Global reported deaths show major earlier peaks followed by an overall decline over the later observation period.

### Chart 4 — Distribution of Reported Deaths per Million

The histogram shows a right-skewed distribution, with many countries at lower mortality rates and a smaller group at substantially higher rates.

### Chart 5 — GDP per Capita vs Reported Deaths per Million

The scatter plot shows considerable dispersion and does not indicate a simple relationship between economic development and reported mortality.

### Chart 6 — Reported Deaths per Million by Continent

The box plot demonstrates substantial variation between regions and identifies outlier countries within several continents.

The assignment expects at least five clear charts with titles, labels and interpretations; the project produced six.

---

## 9. Recommendations

### Recommendation 1 — Use population-adjusted indicators alongside total counts

**Recommendation:**
Policy teams should monitor cases and deaths per million alongside absolute totals.

**Evidence:**
Country rankings differed when population-adjusted rates were used.

**Expected benefit:**
This will support more meaningful comparisons between countries of different population sizes.

---

### Recommendation 2 — Prioritise countries with unusually high mortality rates for further review

**Recommendation:**
Countries appearing as high-rate outliers or in the highest deaths-per-million ranking should receive additional analytical attention.

**Evidence:**
The Top 10 deaths-per-million table, histogram and continent box plot show substantial country-level variation.

**Expected benefit:**
Targeted review can help identify where reporting, health-system capacity or recovery conditions require further investigation.

---

### Recommendation 3 — Maintain regular monthly trend monitoring

**Recommendation:**
Programme teams should continue to review monthly reported cases and deaths rather than relying only on cumulative totals.

**Evidence:**
The time-series charts show several major waves and changing patterns over the pandemic period.

**Expected benefit:**
Regular reporting can help identify emerging changes and support timely programme planning.

---

### Recommendation 4 — Include data-quality indicators in management reporting

**Recommendation:**
Missing profile variables and known reporting limitations should be documented alongside health indicators.

**Evidence:**
The dataset contains substantial missing information in several health-system and development variables.

**Expected benefit:**
Making data quality visible can reduce the risk of managers drawing conclusions from incomplete or non-comparable information.

---

## 10. Limitations

This analysis has several important limitations.

First, reported cases and deaths depend on national testing capacity, reporting systems, definitions and reporting delays. Differences between countries may therefore partly reflect differences in data collection rather than differences in the true disease burden.

Second, several country-profile variables contain missing data. GDP per capita, hospital beds, median age and Human Development Index are not complete for every location.

Third, cumulative variables such as total cases and total deaths must be interpreted carefully. Summing cumulative measures across multiple dates would overstate the burden, so latest available country-level values were used where appropriate.

Fourth, differences in population size can make absolute case and death totals difficult to compare. Population-adjusted indicators provide an additional perspective but are themselves affected by reporting quality.

Fifth, some national statistics may be revised retrospectively or reported later than others.

Finally, this project uses **descriptive analytics**. Relationships observed between indicators do not establish causation. This limitation is explicitly recognised in the project guidance.

---

## 11. Conclusion

This project demonstrated a complete Python data analytics workflow using a large real-world public-health dataset. The analysis included inspection, cleaning, calculated variables, merging, grouped summaries, pivot reporting, crosstabs and six visualisations.

The results show that reported COVID-19 burden varied considerably between countries and continents. Population-adjusted measures were important for fairer comparison, while monthly trend analysis demonstrated that cases and deaths occurred in distinct waves rather than at constant levels.

The analysis also showed that economic indicators such as GDP per capita should not be used alone to explain differences in COVID-19 outcomes. Country-level health burden should instead be assessed alongside population, health-system information, reporting quality and other contextual indicators.

Overall, the findings support continued monthly monitoring, greater use of population-adjusted indicators, targeted review of high-burden countries and transparent communication of data-quality limitations.

---

## Data Source

**Our World in Data — Complete COVID-19 Dataset**

The assignment specifies the Our World in Data dataset as the required public data source and requires it to be saved locally as `data/owid-covid-data.csv`.

---

## Appendix — Project Outputs

The completed project includes:

* `RajakokilaMuralitharan_Global_Health_Analysis.ipynb`
* `RajakokilaMuralitharan_cleaned_covid_data.csv`
* `RajakokilaMuralitharan_summary_tables.xlsx`
* `RajakokilaMuralitharan_Final_Report.md`
* `RajakokilaMuralitharan_Presentation.pptx` or `.md`
* `RajakokilaMuralitharan_Reflection.md`

These deliverables correspond to the required final submission structure.
