# Flight Fare EDA
## Project Overview
This project performs Exploratory Data Analysis (EDA) on flight fare data to uncover patterns, trends, and insights that influence ticket pricing. The analysis examines various factors like airline, route, departure time, number of stops, and duration to understand pricing behavior in the Indian aviation market.

Dataset
Source: Flight_Fare.xlsx
Size: 10,683 records (reduced to 10,463 after removing duplicates)
Time Period: March 2019 - June 2019
Scope: Indian domestic flights
Features
Column	Description	Data Type
Airline	Operating airline name	Object
Date_of_Journey	Travel date	Object
Source	Departure city	Object
Destination	Arrival city	Object
Route	Flight routing (with stops)	Object
Dep_Time	Departure time	Object
Arrival_Time	Arrival time and date	Object
Duration	Total flight duration	Object
Total_Stops	Number of stops (non-stop, 1 stop, 2 stops)	Object
Additional_Info	Service info (meal inclusions)	Object
Price	Ticket price (INR)	Integer
Key Findings
Data Quality
Duplicates: 220 duplicate records identified and removed
Missing Values: 1 record with null Route and Total_Stops (removed)
Final Dataset: 10,463 clean records
Airlines Covered
IndiGo
Air India
Jet Airways
SpiceJet
Multiple carriers
Price Range
Minimum: ₹3,873
Maximum: ₹22,270
Price influenced by: number of stops, flight duration, departure time, and airline
Methodology
Data Loading: Imported Excel file using pandas
Data Cleaning:
Removed duplicate entries
Handled missing values
Validated data integrity
Exploratory Analysis:
Statistical summaries
Distribution analysis
Relationship exploration
Tools & Libraries
Python 3
Pandas: Data manipulation and analysis
NumPy: Numerical computations
Matplotlib: Data visualization
Seaborn: Statistical visualizations
Usage
Run the notebook in Google Colab or Jupyter Notebook:

Python
# Load required libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_excel("Flight_Fare.xlsx")

# View structure
df.info()
df.head()
Key Insights
Direct flights (non-stop) are generally more expensive
Multi-stop flights show significant price variation based on route efficiency
Price peaks during peak travel dates (weekends, holidays)
Different airlines have distinct pricing strategies
Additional services (meals) impact pricing
Next Steps
Potential areas for deeper analysis:

Predictive modeling for fare prices
Airline comparison and competitive analysis
Seasonal pricing trends
Route optimization for budget travelers
Time-series analysis across months
