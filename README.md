# Longitudinal Analysis (2015-2025) of Health-Poverty Dynamics Across U.S. Counties

## Project Overview

This project analyzes county-level health and socioeconomic data across the United States from 2015–2025. It explores trends in poverty, unemployment, mental and physical health, and other related indicators. The workflow includes robust data cleaning, exploratory data analysis, statistical summaries, and machine learning (Random Forest) modeling to examine patterns and predictors of poor mental and physical health outcomes in relation to poverty.


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
- **[ZIP to County FIPS codes](https://rowzero.io/workbook/8DBEAEC93C53EF406AFD4543/163?ref=fips-codes)** -- or find another method to **ZIP <=> FIPS** code

### Processed Datasets
- `/data/processed/` was intended for cleaned CSVs (not included in repo)

### Notebook

- run preprocessing & analysis: `Health-Poverty_Dynamics.ipynb`