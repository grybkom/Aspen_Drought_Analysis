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




