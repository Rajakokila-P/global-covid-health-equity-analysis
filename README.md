# Global COVID-19 Health Equity and Recovery Analysis

## Project Overview
This Python data analytics project analyses global COVID-19 health equity, regional burden, time trends, data quality and recovery indicators using the Our World in Data COVID-19 dataset.

## Objective
The purpose of the project is to identify differences in reported COVID-19 burden across countries and continents and provide descriptive, evidence-based recommendations for public-health recovery monitoring.

## Tools Used
- Python
- pandas
- Matplotlib
- Seaborn
- Jupyter Notebook
- VS Code

## Dataset
Source: Our World in Data Complete COVID-19 Dataset.

The raw dataset was not uploaded to GitHub because of its large file size. It can be downloaded from Our World in Data.

## Data Preparation
The analysis included:
- Inspection of rows, columns, data types and missing values
- Selection of relevant COVID-19 and country-profile variables
- Removal of aggregate rows for country-level analysis
- Missing-value treatment
- Duplicate checks
- Date conversion
- Calculated rate fields
- Merge validation

## Key Analysis
The project includes:
- Continent-level summaries
- Top 10 countries by cases per million
- Top 10 countries by deaths per million
- Monthly global trends
- Pivot tables
- Crosstabs
- GDP and mortality comparison
- Regional mortality distributions

## Key Findings
- Reported COVID-19 burden differed considerably across continents.
- Population-adjusted measures provide more useful country comparisons than totals alone.
- Global reported cases and deaths occurred in distinct waves.
- Reported deaths per million varied substantially within and between regions.
- GDP per capita alone did not explain differences in reported COVID-19 mortality.

## Visualisations
The repository contains six main charts:
1. Reported Total Deaths by Continent
2. Global Monthly Reported New Cases
3. Global Monthly Reported New Deaths
4. Distribution of Reported Deaths per Million
5. GDP per Capita vs Reported Deaths per Million
6. Reported Deaths per Million by Continent

## Recommendations
- Use population-adjusted indicators alongside total counts.
- Prioritise countries with unusually high reported mortality rates for further review.
- Maintain monthly trend monitoring.
- Include data-quality limitations in management reporting.

## Limitations
This analysis is descriptive. Reported COVID-19 figures may be affected by differences in testing, reporting systems, missing values and revisions. Relationships between variables should not be interpreted as proof of causation.

## Repository Contents
- Jupyter Notebook
- Final Report
- Presentation
- Reflection
- Summary Tables
- Exported Charts
