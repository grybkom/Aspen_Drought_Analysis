# Aspen_Drought_Analysis
Environmental factors influencing drought conditions in Aspen, Colorado, from mid-2010 to December 2023.
---

## Project Structure

- `AspenClimateDataCleaning` — Downloads, cleans, and merges raw climate and drought datasets. Outputs a cleaned `.parquet` file.
  - Five datasets of environmental features were merged by date and saved as class_aspen.parquet
      - AspenCO.csv, weather data
      - CRNSSM0101-CO_Montrose_11_ENE.csv, soil moisture and temperature data 
      - site 09073005 using dataretrieval.nwis, streamflow data
      - site 395136108210004 using dataretrieval.nwis, drought well data
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
Drought severity is classified into four stages No Drought (0), Moderate (1), Severe (2), Extreme (3), 'Exceptional (4)
![Drought_Bar](https://github.com/user-attachments/assets/649cd6f8-4c86-4529-acdb-8f2fc37802e7)




