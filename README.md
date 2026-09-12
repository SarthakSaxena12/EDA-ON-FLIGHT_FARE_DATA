# Flight Fare EDA

## Project Overview

This repository contains an Exploratory Data Analysis (EDA) project on Indian domestic flight fare data. The analysis uncovers patterns, trends, and factors that influence airline ticket prices — including number of stops, flight duration, departure time, and airline.

## Table of Contents

- [Dataset](#dataset)
- [Features](#features)
- [Data Quality & Cleaning](#data-quality--cleaning)
- [Exploratory Analysis & Key Findings](#exploratory-analysis--key-findings)
- [Tools & Libraries](#tools--libraries)
- [Usage](#usage)
- [Next Steps](#next-steps)
- [Contact](#contact)

## Dataset

- **Source:** `Flight_Fare.xlsx`
- **Original size:** 10,683 records
- **Final size after cleaning:** 10,463 records (duplicates and invalid rows removed)
- **Time period:** March 2019 — June 2019
- **Geographic scope:** Indian domestic flights

## Features

| Column          | Description                                    | Data Type |
|-----------------|------------------------------------------------|-----------|
| Airline         | Operating airline name                         | Object    |
| Date_of_Journey | Travel date                                    | Object    |
| Source          | Departure city                                 | Object    |
| Destination     | Arrival city                                   | Object    |
| Route           | Flight routing (with stops)                    | Object    |
| Dep_Time        | Departure time                                 | Object    |
| Arrival_Time    | Arrival time and date                          | Object    |
| Duration        | Total flight duration                          | Object    |
| Total_Stops     | Number of stops (non-stop, 1 stop, 2 stops...) | Object    |
| Additional_Info | Service info (meal inclusions, etc.)           | Object    |
| Price           | Ticket price (INR)                             | Integer   |

## Data Quality & Cleaning

- Removed 220 duplicate records.
- Removed rows with null values in critical columns (e.g., `Route`, `Total_Stops`).
- Converted date/time columns to appropriate datetime types where applicable.
- Validated numeric columns (e.g., `Price`) and inspected for outliers and inconsistencies.

## Exploratory Analysis & Key Findings

- Direct (non-stop) flights are generally more expensive than flights with stops.
- Number of stops, total duration, departure time, and airline are strong drivers of ticket price.
- Price variation exists across different routes and airlines. Some multi-stop routes can still be competitive depending on routing efficiency and airline pricing strategy.
- Price range in the cleaned dataset: **₹3,873** (min) — **₹22,270** (max).
- Price peaks are observed around weekends and likely holiday dates (mapping to an events calendar is recommended for confirmation).
- Additional services (e.g., meal inclusions) correlate with higher fares for some airlines and routes.

## Tools & Libraries

- Python 3
- pandas — data loading and manipulation
- numpy — numerical operations
- matplotlib — plotting
- seaborn — statistical visualizations

## Usage

Open and run the provided Jupyter notebook in Google Colab or a local Jupyter environment. Example steps to load and inspect the data:

```python
# Load required libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_excel('Flight_Fare.xlsx')

# Quick checks
df.info()
df.head()

# Basic statistics
print(df['Price'].describe())

# Check duplicates
print('Duplicates:', df.duplicated().sum())
```

For the full analysis, run the notebook included in this repository and follow the sections in order (data cleaning -> exploratory plots -> insights).

## Next Steps

- Develop predictive models to estimate fares (regression, tree-based models).
- Perform seasonal and time-series analysis by mapping journey dates to holidays and calendar events.
- Compare pricing strategies across airlines and routes.
- Add interactive dashboards (Plotly, Dash, Streamlit) for exploratory use.

## Contact

If you have questions or suggestions, please open an issue in this repository or reach out to the author.
