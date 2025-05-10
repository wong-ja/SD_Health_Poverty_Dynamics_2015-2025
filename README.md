# Random Forest Analysis of Health and Poverty Dynamics in the U.S. (2015-2025)


## Project Overview

This project analyzes county-level health and socioeconomic data across the United States from 2015–2025. It explores trends in poverty, unemployment, mental and physical health, and other related indicators. The workflow includes robust data cleaning, exploratory data analysis, statistical summaries, and machine learning (Random Forest) modeling to examine patterns and predictors of poor mental and physical health outcomes in relation to poverty.

Read the [Project Report](report.pdf) or view the Project Presentations [I (6-7 min)](present.pdf) &/or [II (10 min)](present-fin.pdf).


## Technologies
- Python 3.13.1, Jupyter Notebooks
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn 
- DuckDB

```
pip install duckdb pandas numpy scikit-learn matplotlib seaborn
```

## Installation & Usage
### Original Datasets 
- see `/data/raw/` for examples
- **[Google Research / Population Dynamics (PDFM)](https://github.com/google-research/population-dynamics)** --
    + **[County Unemployment](https://github.com/google-research/population-dynamics/blob/master/data/benchmarks/county_unemployment.csv) (monthly)**
    + **[ZCTA/ZIP Poverty](https://github.com/google-research/population-dynamics/blob/master/data/benchmarks/zcta_poverty.csv) (annually)**
    + **[CONUS27](https://github.com/google-research/population-dynamics/blob/master/data/benchmarks/conus27.csv) (location - health outcomes & indicators)** 
- **[County Health Rankings - Health Outcomes & Indicators](https://www.countyhealthrankings.org/health-data/methodology-and-sources/data-documentation)** -- manually download *CHR CSV Analytic Data** for each year from 2015-2025
    + **Note**: very limited data for 2023-2025; prevalence of *NaN/Null* values in health-related columns for all years
- **[ZIP to County FIPS codes](https://rowzero.io/datasets/fips-codes-lookup#zip-codes-to-fips-codes-mapping)** -- or find another method to **ZIP <=> FIPS** codes
    + Also used for mapping: [FIPS Codes, States & Abbr.](https://www.bls.gov/respondents/mwr/electronic-data-interchange/appendix-d-usps-state-abbreviations-and-fips-codes.htm)

### Processed Datasets
- see `/data/processed/` for cleaned/processed CSVs

### Notebook

- run preprocessing & analysis: `/notebooks/Health-Poverty_Dynamics.ipynb`

## 

Expected file structure:
```
project
|
|-- data/
|---- raw/
|------ ZIP_FIPS_feb_2025.csv
|------ Population Dynamics (PDFM)/
|-------- conus27.csv
|-------- county_unemployment.csv
|-------- zcta_poverty.csv
|------ County Health Rankings/
|-------- analytic_data2015.csv
|-------- ...        # from 2016 to 2024
|-------- ...        # analytic data CSVs
|-------- analytic_data2025.csv
|---- processed/
|------ clean_conus27.csv
|------ clean_county_health.csv
|------ clean_poverty.csv
|------ clean_unemployment.csv
|------ clean_zip_fips.csv
|------ final_conus27.csv
|------ final_county_health.csv
|------ final_poverty.csv
|------ final_unemployment.csv
|-- Health-Poverty_Dynamics.ipynb
|
```

- **Note**: `data/raw/ne_110m_admin_1_states_provinces/` and `data/raw/zip2fips.json` were intended for state-based analysis by mapping ZIP codes to FIPS codes and then to States (inc/not done) -- may exclude in project replication