# FRE 521D Final Project  
## Climate Variability and Global Agricultural Productivity

---

## Project Overview

This project examines how climate variability affects global agricultural productivity by integrating historical crop production data with temperature and precipitation indicators. The analysis focuses on identifying climate-sensitive crops, understanding differences in vulnerability across income groups, and classifying agricultural systems as resilient or vulnerable under climate stress.

Completed as part of **FRE 521D: Data Engineering for Food and Resource Economics**, the project emphasizes reproducible data infrastructure, relational database integration, and applied climate–agriculture analysis.
---

## Research Questions Addressed

This project addresses the following research questions:

- **Crop Vulnerability (Q1):**  
  Which major staple crops are most vulnerable to climate variability (temperature and precipitation)?

- **Agricultural Resilience (Q3):**  
  Which agricultural systems are resilient versus vulnerable when exposed to high climate variability?

- **Production Trends (Q4):**  
  What long-run trends in crop production suggest increasing or decreasing climate risk?

---

## Data Sources

The project integrates multiple datasets:

- **FAO Crop Production Data**  
  - Crop yields (kg/ha), harvested area, and production by country and year.

- **NOAA Climate Data**  
  - Annual temperature measures and climate indicators.

- **Open-Meteo API (ETL Pipeline)**  
  - Daily weather data used to construct:
    - Extreme heat days  
    - Freeze days  
    - Precipitation variability  
    - Growing degree days (GDD)

---

## Data Infrastructure

- Data were ingested into a **MySQL relational database** using a normalized schema.
- Primary and foreign keys include `country_id`, `country_name`, and `year`.
- SQL joins and database views were used to create integrated country–year datasets.
- An ETL pipeline extracted, transformed, and loaded weather data into the database with validation and logging.

---

## Methodology Summary

- **Q1:**  
  Two-way fixed effects regressions (country and year fixed effects) were estimated to assess crop yield sensitivity to:
  - Average temperature  
  - Precipitation variability  
  Heteroskedasticity-robust (HC1) standard errors were applied.

- **Income Group Extension:**  
  Regressions were estimated separately for low, lower-middle, upper-middle, and high-income countries.

- **Q3:**  
  Climate exposure indices were constructed using temperature and precipitation variability.  
  Yield variability (coefficient of variation) was used to classify systems as:
  - Resilient  
  - Vulnerable  
  Median-based thresholds were applied and visualized using scatter plots.

- **Q4:**  
  Long-run production trends were analyzed to identify stagnating or declining crop–region combinations.

All results represent **associational relationships**, not causal effects.

---

## Limitations 

Several limitations should be acknowledged:

The analysis relies on historical data and a relatively limited time horizon for certain climate indicators, which may not fully capture long-term climate dynamics.

Measures of adaptive capacity (e.g., irrigation intensity, technology adoption) are proxied rather than directly observed.

The regression framework identifies statistical associations rather than causal relationships.

Country-level aggregation may mask important subnational heterogeneity in climate exposure and agricultural responses.


## How to Run the Analysis

#All analysis for this project is contained in:

FRE_521D_Final_Project.ipynb

To Reproduce the Results

Ensure Python and required dependencies are installed:
pip install -r requirements.txt

Ensure the MySQL database is running and properly configured.

Open FRE_521D_Final_Project.ipynb and execute all cells from top to bottom.




## Repository Structure

```text
Final_Project/
├── notebooks/
│   └── FRE_521D_Final_Project.ipynb
├── sql/
│   ├── schema.sql
│   └── views.sql
├── data/
│   └── processed/
├── README.md
└── requirements.txt
```
## The Notebook Includes

- Data ingestion and cleaning
- Database integration and SQL queries
- Q1: Climate sensitivity regression analysis

Q3: Resilience classification and visualization

Q4: Long-run production trend analysis

All tables and figures reported in the final submission

## Acknowledgments

We are grateful to Prof. Neloy for his guidance and support in developing for this project.
```




