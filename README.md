## GSV Coverage Summaries

This repository provides a simple Python script to generate Google Street View (GSV) image‐capture summaries enriched with U.S. Census ACS demographic data. It supports both census‐tract and block‐group geographies, and lets you specify any city (by name) and FIPS codes at runtime—and requires you to supply your own ACS API key.

---

## Features

- **Tract-level summaries**  
  Computes average image staleness (in years), dominant season, and road-type metrics for each census tract in your chosen city, and joins on key ACS variables (e.g., population, median income, mode shares).

- **Block-group-level summaries**  
  The same set of metrics, but aggregated at the census block-group level (requires county FIPS).

- **No hard-coded keys or cities**  
  All inputs—including your ACS API key, the GSV metadata file, city name, and FIPS codes—are passed via command-line arguments.

- **GeoJSON output**  
  Writes an EPSG:3857 GeoJSON file ready for mapping or GIS analyses.

---

## Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/gsv-coverage.git
   cd gsv-coverage
   ```

2.	**Create a virtual environment (optional but recommended)**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install pandas geopandas shapely osmnx requests
   ```

---

## Usage

Argument
Description
--gz_path
Path to the input GSV metadata CSV.gz file.
--city_name
Full city name for OSM geocoding (e.g. "Austin, Texas, USA").
--state_fips
Two-digit state FIPS code (e.g. 53 for Washington).
--county_fips
(Block-group only) Three-digit county FIPS code (e.g. 033 for King County).
--acs_api
Your U.S. Census ACS API key (register at https://api.census.gov/data/key_signup.html).
--output_path
File path for the output GeoJSON (will be written in EPSG:3857).
--year
ACS year to pull (default: 2023).
--level
tract or blockgroup (default: tract).


   


