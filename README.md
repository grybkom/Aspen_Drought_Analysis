# Aspen_Drought_Analysis
Environmental factors influencing drought conditions in Aspen, Colorado, from mid-2010 to December 2023.
---

## Background
Drought is an environmental phenomenon when there is not enough water available is to meet demand (Bolinger et al., 2024). This project evaluates the impact of environmental factors on drought conditions in Aspen, Colorado, using data from mid-2010 to December 2023. Supervised and unsupervised machine learning techniques were applied to assess feature importance and predict drought severity. A neural network classified five drought levels with approximately 95% accuracy. Principal Component Analysis (PCA) identified air temperature, soil moisture, and soil temperature as the most influential features. PCA improved K-means clustering performance but did not enhance neural network predictions. Given the economic and environmental risks of drought, understanding key drivers and improving predictive models could aid mitigation efforts (Colorado Climate Action, United States Department of Agriculture).

## Project Structure

- `AspenClimateDataCleaning` — Downloads, cleans, and merges raw climate and drought datasets. Outputs a cleaned `.parquet` file.
  - Five datasets of environmental features were merged by date and saved as class_aspen.parquet
      - AspenCO.csv, weather data
      - CRNSSM0101-CO_Montrose_11_ENE.csv, soil moisture and temperature data 
      - site 09073005 using [dataretrieval.nwis](https://pypi.org/project/dataretrieval/), streamflow data
      - site 395136108210004 using [dataretrieval.nwis](https://pypi.org/project/dataretrieval/), drought well data
      - USDM-pitkin-county-co.csv, drought data (response variable with 5 classes of drought)
- `AspenDroughtPredictionModels` — Loads `class_aspen.parquet` and applies statistical models to explore and predict climate-driven drought patterns.
- `data/class_aspen.parquet` — The cleaned and merged dataset used in the analysis notebook.

## Data
### Predictors
- date: Date of Observations in Format year-month-day from 2010-06-22 to 2023-12-27
- prcp: Total Precipitation in Centimeters
- tmax: Maximum Temperature in Celsius
- tmin: Minimum Temperature in Celsius
- gwl: Level of the Water Table in Centimeters (measures how far the water is from the surface, larger measurements indicating there is less water in the well)
- sm_20cm: Soil Moisture Volumetric Water Content at 20 Centimeters depth
- st_20cm: Soil Temperature at 20 Centimeters depth
- sm_50cm: Soil Moisture Volumetric Water Content at 50 Centimeters depth
- st_50cm: Soil Temperature at 50 Centimeters depth
- sm_100cm: Soil Moisture Volumetric Water Content at 100 Centimeters depth
- st_100cm: Soil Temperature at 100 Centimeters depth
- daily_discharge_cms: Water Flow in Cubic Centimeters per Second

### Response
Drought severity is classified into four stages, No Drought (0), Moderate (1), Severe (2), Extreme (3), 'Exceptional (4)
![Drought_Bar](https://github.com/user-attachments/assets/649cd6f8-4c86-4529-acdb-8f2fc37802e7)

## References:

Bolinger, R.A., J.J. Lukas, R.S. Schumacher, and P.E. Goble, 2024: Climate Change in Colorado, 3rd edition. Colorado State University, https://doi.org/10.25675/10217/237323

Colorado Climate Action. Climate Change in Colorado: Public Health and Environmental Impacts | Climate. https://climate.colorado.gov/health-and-environmental-impacts

United States Department of Agriculture. Drought Impacts in the Rocky Mountain Region. Sept. 2017, www.fs.usda.gov/sites/default/files/r2-droughtfactsheet.pdf

## Data Sources:

Weather data, precipitation, max temperature and min temperature, Aspen Pitkin Co Airport Sardy Field, CO US:
https://www.ncdc.noaa.gov/cdo-web/datasets/GHCND/stations/GHCND:USW00093073/detail

Daily discharge data for Lincoln Creek, Near Aspen, CO:
https://dashboard.waterdata.usgs.gov/api/gwis/2.1/service/site?agencyCode=USGS&siteNumber=09073005&open=211313

Ground water level data, drought well near Aspen, CO:
https://dashboard.waterdata.usgs.gov/api/gwis/2.1/service/site?agencyCode=USGS&siteNumber=395136108210004&open=212313

Soil moisture and temperature data Montrose, CO: 
https://www.ncei.noaa.gov/data/us-climate-reference-network/access/derived-products/soil/soilanom/

Drought data, Pitkin County, CO:
https://www.drought.gov/states/colorado/county/pitkin




