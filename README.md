# Tracking-Atmospheric-CO-A-Historical-Analysis-of-Emission-Trends-1958-2016-
This data science research project investigates the long-term trends in atmospheric carbon dioxide (CO₂) concentrations from 1958 to 2016


## Project Overview
This data science research project investigates the long-term trends in atmospheric carbon dioxide (CO₂) concentrations from 1958 to 2016.

Utilizing high-resolution time-series data from the Mauna Loa Observatory and other verified sources, the project explores the seasonal and annual patterns of CO₂ emissions over nearly six decades.

Through trend analysis and robust data visualization, the study provides compelling evidence of the accelerating rise in CO₂ levels driven by anthropogenic activity.

By presenting clear, data-backed insights into historical CO₂ emissions, this project aims to inform public discourse, support environmental advocacy, and encourage policy interventions for climate action.
### Objectives
- To analyze the trend of atmospheric CO₂ concentrations from 1958 to 2016.

- To quantify the annual growth rate in CO₂ levels.

- To communicate findings using visualizations that are accessible to both scientific and non-scientific audiences.
  ### Data Source
  **Mauna Loa Observatory CO₂ Data:** Provided by NOAA [National Oceanic and Atmospheric Administration](https://gml.noaa.gov/ccgg/trends/)
  ### Methodology
  - Loaded the data from a CSV file into a Pandas Dataframe

- Converted the data into time-series format for seasonal decomposition

- Handled missing values and smoothed data using rolling averages

- Visualized the data to uncover the trend in co2 emmision from 1958 to 2016.
  ### Data Pre-Processing
  The dataset is provided by NOAA [National Oceanic and Atmospheric Administration](https://gml.noaa.gov/ccgg/trends/),  contains records of the change in climate in the last half a century or so. 

The data is in a CSV file called `climate_change` with three columns. 

- 1. The `"date"` column indicates when the recording was made and is stored in the year-month-date format.
     A measurement was taken on the 6th day of every month from 1958 until 2016. 


- 2. The  `"co2"` column contains measurements of the carbon dioxide in the atmosphere.
     The number shown in each row is parts-per-million of carbon dioxide. 


- 3. The  `"relative_temp"` column denotes the temperature measured at this date, relative to a baseline which is the average        temperature in the first ten years of measurements.
### Data Loading
```python
# solution 
import pandas as pd
climate_change_df = pd.read_csv("C:/Users/HP/OneDrive/Documents/_DATA SCIENCE BOOK CAMP TRANINIG/DATA SET/climate_change.csv")

climate_change_df

```


###  Data Analysis
- **Time-Series Decomposition**: This was used to separate trend, seasonality, and residuals.

- **Visualization:** Created line plots,  seasonal subseries plots, and anomaly detection visuals using Python library (Matplotlib)
  ```python
# converting the data set into time series decomposition

climate_change_df = pd.read_csv("C:/Users/HP/OneDrive/Documents/_DATA SCIENCE BOOK CAMP TRANINIG/DATA SET/climate_change.csv",parse_dates =["date"], index_col = "date")

climate_change_df.head()


  ```
![data analysis 3](https://github.com/user-attachments/assets/446bf28d-856e-4f8d-974d-464081ed4126)



###  Data Inspection(check for missing values)
```python
# check for any missing value and column

climate_change_df.isna().any()

```
```python
# counting the number of missing value

climate_change_df.isna().sum()
```
### Data Cleaning (handling missing values) 

```python
climate_change_df.shape

```
```python
climate_change_df["co2"].mean()

```
```python
# filling the missing values with the mean value 352.32 on the co2 column
climate_change_df = climate_change_df.fillna(352.32)
climate_change_df.head()

```
### Data Visualization
```python
climate_change_df
```
```pytho
# to confirm, that there are no more missing values
climate_change_df.isna().any()
```

## DATA VISUALIZATION
```python

# data visualization using the object oriented interface of matplotlib
import matplotlib.pyplot as plt
fig, ax = plt.subplots()

# data visualization
ax.plot(climate_change_df.index, climate_change_df["co2"], color = "red")

# labeling the x-axis and y-axis
ax.set_xlabel("time")
ax.set_ylabel("co2 (part per million)")

# adding a title to our plot
fig.suptitle ("The Atmospheric co2 Emmission Trends(1958-2016)")

# to show the plot
plt.show()
```
## DATA INTERPRETATION
 The data visualization above shows that there is an overall steady increase of c02 emission from 958 to 2016
 
 ### Key Findings
 **Steady Increase**: CO₂ levels rose from approximately 315 ppm in 1958 to over 403 ppm by 2016.

**Seasonal Patterns**: A regular saw-tooth pattern was observed, corresponding to seasonal plant activity (photosynthesis cycles).

**Acceleration in Emissions**: Linear curve indicates steady growth and increasing acceleration in emissions, especially post-2000.
### Recommendations
- I strongly reconmmend  the global adoption of renewable energy sources.

- I strongly reconmmend the Promotion of  global CO₂ emission monitoring for real-time policy response.

- I strongly reconmmend that this  findings should be used as part of educational material in environmental science curricula.

- I strongly reconmmend the Extension of this  study to include temperature anomaly data for correlation analysis.

### Recommendations
- I strongly reconmmend  the global adoption of renewable energy sources.

- I strongly reconmmend the Promotion of  global CO₂ emission monitoring for real-time policy response.

- I strongly reconmmend that this  findings should be used as part of educational material in environmental science curricula.

- I strongly reconmmend the Extension of this  study to include temperature anomaly data for correlation analysis.




