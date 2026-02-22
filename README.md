# Capstone-DigitalMarketing-KPIs

## Project Overview
This project involved a comprehensive analysis of digital advertising performance to identify which locations, creative elements, and platforms drive the highest return on investment. While the analysis covers a broad range of marketing metrics, the core of my contribution focused on **Spatial Analysis** (standardizing geographic data to map performance across cities and states) and a secondary deep dive into **Creative Performance**.

Due to team restructuring, our group managed a workload originally designed for four people. Detailed descriptions and data visualizations can be found in the rendered HTML files included in this repository.

The project is split into two primary workflows:
1. **Spatial & Geographic Data Engineering**: Standardizing messy, raw location strings (DMAs) into clean city and state columns.
2. **Creative Performance EDA**: Analyzing the effectiveness of different ad dimensions and marketing messages across various exchanges and websites.

## What was used?
I used **R** and **Quarto** to build a reproducible data pipeline. The following libraries were essential:
* **tidyverse**: Specifically `dplyr` and `stringr` for complex regex cleaning and data manipulation.
* **janitor**: For automated column name cleaning.
* **scales**: To format currency and percentages for human-readable tables.
* **knitr**: To generate professional HTML reports.

## My Workflow
### 1. Geographic Standardization (Primary Focus)
To enable accurate spatial analysis, I developed a process to parse the `location` column:
* **Split & Clean**: Separated raw location strings into standardized `city_primary` and `state` columns.
* **Cross-State Correction**: Manually corrected messy state strings for cross-state DMA entries.
* **Exception Handling**: Implemented specific logic to handle "Tri-Cities" and other hyphenated regions.

### 2. Technical Data Cleaning
* **Encoding Repair**: Used `stringr` to fix corrupted characters in the `audience_segment` column.
* **Audience Hierarchy**: Standardized behavioral targeting levels for cleaner analysis.

### 3. KPI Engineering & Validation
I built a calculation engine to generate performance metrics including **CTR**, **CPA**, **eCPM**, and **vCPM**. To maintain data integrity, I implemented a "cap" on conversion rates to ensure any statistical anomalies where conversions exceeded clicks were normalized to **100%**.

## Key Insights
* **Spatial Consistency**: Standardizing geographic names identified performance trends across specific states and primary cities that were previously obscured.
* **Platform vs. Location**: The data revealed that specific **App/URL** and **Ad Exchanges** often had a more significant impact on CPA than geography alone.
* **Creative Effectiveness**: By sorting by **CPA**, I identified which marketing messages and creative sizes were most cost-effective.

## How to use this repository
1. **Run Data Cleaning First**: You must run `coop_capstone_data_cleaning.qmd` to generate the `dat_kpis.csv` file.
2. **Explore the Analysis**: 
    * Open `coop_capstone_eda_spatial.qmd` for geographic performance breakdowns.
    * Open `coop_capstone_eda_creative.qmd` for breakdowns by site, size, message, and device.
  
## The slides that was used for the project can be found [here](https://docs.google.com/presentation/d/1VHhvBEuPvOfZ3Sk5W6HpFfEdnHfvmMiyYVent5lfBTo/edit?usp=sharing):
