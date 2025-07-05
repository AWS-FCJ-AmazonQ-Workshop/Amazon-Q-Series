---
title: "Python End-to-End Solution with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Step 1: Setup

- Use a Python IDE (e.g., VS Code) with Amazon Q Developer enabled.
- Install Python 3.9+ and the following libraries:
  - `streamlit`, `pandas`, `matplotlib`, `seaborn`, `jupyter`
- Install with:

```sh
pip install streamlit pandas matplotlib seaborn jupyter
```

- Project structure:
  - `base-folder/`
    - `data/`
      - `data.ipynb` (Jupyter notebook for data cleanup)
      - `weather_data_orig.csv` (original dataset)
      - `weather_data.csv` (cleaned dataset)
    - `configuration.ini` (config file)
    - `weather.py` (main Streamlit app)

#### Step 2: Data Preparation

- Use a weather dataset (CSV) with columns: NAME, DATE, TAVG, TMAX, TMIN.
- Clean and transform data step-by-step in `data/data.ipynb` using Amazon Q Developer prompts:
  - Import CSV as DataFrame
  - Remove rows with null TMAX/TMIN
  - Keep columns: STATION, NAME, DATE, TAVG, TMAX, TMIN
  - Create new columns (Country, StationName) by splitting NAME
  - Convert TMIN, TMAX, TAVG to float
  - Fill TAVG if NaN: `TAVG = (TMAX + TMIN)/2`
  - Convert DATE to datetime
  - Write cleaned DataFrame to CSV
- Try both single-line and multi-line prompting for code generation.

#### Step 3: Streamlit Application

- Create `configuration.ini` to specify the cleaned dataset path.
- In `weather.py`, import required libraries:
  - `streamlit`, `configparser`, `os`, `sys`, `pandas`, `matplotlib.pyplot`, `seaborn`
- Read config and load data with caching (`st.cache_data`).
- Convert DATE column to datetime.
- Layout:
  - Use Streamlit Markdown for header
  - Add two tabs: 'Data Set' and 'Single City Charts'
  - First tab: show DataFrame
  - Second tab: widgets to select country, station, date range; show line chart and heatmap
- Use Amazon Q Developer prompts for each step, and experiment with suggestions.
- Best practices:
  - Use config files for paths
  - Use caching for data loading
  - Modularize code with functions

> **Note:** Amazon Q Developer is non-deterministic; generated code may differ. Always review and adapt suggestions to your needs.