# Project 5: Predicting the Economic Impact of Natural Disasters :ocean:

---
## Project Authors:

Andrew Davis <br>
Victor Voskovsy  - [LinkedIn](https://www.linkedin.com/in/victorvoskovsky) <br>
Bryan Lange  - [LinkedIn](https://www.linkedin.com/in/bryanrobertlange) 

---
## Executive Summary

-[Introduction and problem statement](#Introduction "Intro")

-[Data wrangling process](#Data-Information "Data")

-[EDA and visualizations](#Data-Preprocessing-and-EDA "EDA")

-[Modeling the data](#MOdeling-Process "Models")

-[Key observations from analysis](#Key-Findings "Go to Key-Findings")

-[Challenges and recommendations](#Obstacles-and-recommendation "EDA")

### Introduction

According to the NOAA, since 1980 the United States has experienced 265 weather and climate disasters where the overall costs reached or exceeded one billion dollars 

Given the overall increase in disasters in the recent past combined with population growth in coastal regions, planning effective response and relief efforts has never been more critical

The ability to predict potential wage loss from natural disasters will help communities focus their rebuilding efforts on the industries that need it most and help to mitigate economic impact. 

### Problem Statement

Using major hurricane information in combination with data from the Bureau of Labor Statistics, our goal is to use employment and wage figures to help cluster data and predict economic impact on local industries after a hurricane.  

---
## Data Information

| Data Source | Description | Link |
| --- | --- | --- |
| U.S. Bureau of Labor Statistics (BLS) | The Quarterly Census of Employment and Wages (QCEW) | [Link](https://www.bls.gov/cew/about-data/data-files-guide.htm)|
| NOAA | Location, wind, and pressure of tropical cyclones in Atlantic and Pacific Oceans | [Link](https://www.kaggle.com/noaa/hurricane-database)|

---

### BLS Quarterly Employment Data
- Used Google BigQuery and SQL to pull quarterly employment data stretching back 30 years to help compare wage and unemployment rates during natural disasters 
    - Monthly emplyoment levels by industry, average weekly wages and over-the-year percent change data was pulled using BigQuery

### NOAA hurricane data 
- Used CSV file provided by The National Hurricane Center (NHC) to determine hurricane category
    - These databases (Atlantic HURDAT2 and NE/NC Pacific HURDAT2) contain six-hourly information on the location, maximum winds, central pressure, and (starting in 2004) size of all known tropical cyclones and subtropical cyclones.        
1. Hurricane trajectory maps: <br>
    -Visualizing major and minor impacts for localities <br>
    -Picking target hurricanes <br>
2. Considerations:<br>
             - Impact extent<br>
             - Locations<br>
             - Year<br>
             - Quarters

---
## Data Preprocessing and EDA

Our hurricane data is broken down by 3 main categories:<br>
1. Quarterly establishments<br>
2. Average weekly wages by quarter <br>
3. Employment over-all for county for month 3 of the quarter

Our industries are split between real regular values and their Location Quotient. **The LQ was the key for our analysis.** 

“Location quotient (LQ) is basically a way of quantifying how concentrated a particular industry, cluster, occupation, or demographic group is in a region as compared to the nation. It can reveal what makes a particular region “unique” in comparison to the national average.” 

---
## Modeling Process

- Using industries, averaged LQ quotients over quarters preceding hurricane
- K-Means Clustering to group together counties with similar economic snapshots
- 5 total clusters
- Realized that the same county used in different hurricanes assessments should be in same cluster

![Modeling](https://github.com/vic-voskovsky/project_5_master/blob/master/photos/modeling.png)
---

![Modeling](https://github.com/vic-voskovsky/project_5_master/blob/master/photos/modeling2.png)
---
## Key Findings

- Nothing in any of the models groundbreaking<br>
- Hurricanes disproportionately affect real estate, tourism, mining, and oil/gas industries<br>
- Areas that rely on those industries likely to see significant economic problems<br>
- Expanding geographically or periodically might help expand data which is badly needed<br>
- Economic data has many important exogenous factors <br>
- Predictions are tough<br>
- Eventually, economic recovery possible if not probable

---
### Obstacles and recommendation

- Economic effects mixed in with hurricanes
- Limited data (only 20 hurricanes in recent times that caused a large blip)
- Only 118 counties, any classifier will have SSS issues
- Null values for LQ codes or quarters missing
- Economic snapshots changing over time may be misclassified
- Could improve by using better hurricane data other than ‘Category’
- Economic data acquisition extremely time intensive

