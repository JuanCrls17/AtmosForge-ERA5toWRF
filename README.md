ERA5 Data Download Scripts for WRF Initial and Boundary Conditions
This repository contains two scripts, Era_5_singlelevels.ipynb and Era_5_levelpressure.ipynb, designed to download ERA5 reanalysis data from the Copernicus Climate Data Store (CDS). These scripts retrieve single-level and pressure-level data necessary for running the WRF (Weather Research and Forecasting) model as initial and boundary conditions.

Prerequisites
Before running these scripts, ensure you have the following:

Software Requirements
Python 3.x: Make sure Python is installed on your system. You can download it from python.org.

cdsapi library: This is the official Python library for accessing the Copernicus Climate Data Store. Install it via pip:

bash
Copiar código
pip install cdsapi
Jupyter Notebook: To run the .ipynb files, you need Jupyter Notebook installed. You can install it using:

bash
Copiar código
pip install notebook
CDS API Key
To use the Copernicus Climate Data Store, you must have an account and set up your API key. Follow these steps:

Register for a free account at Copernicus Climate Data Store.

Log in and go to Your API key.

Copy the provided API key and configure it on your local machine by adding it to the ~/.cdsapirc file:

bash
Copiar código
url: https://cds.climate.copernicus.eu/api/v2
key: <YOUR_UID>:<YOUR_API_KEY>
Script Descriptions
1. Era_5_singlelevels.ipynb
This script retrieves single-level ERA5 data. It allows the user to specify the year, months, and days of interest, and downloads the selected variables for the specified time range.

Variables Retrieved:
Wind components at 10m (10m_u_component_of_wind, 10m_v_component_of_wind)
2m temperature and dewpoint (2m_temperature, 2m_dewpoint_temperature)
Surface and soil parameters, including pressure, temperature, and water content
Radiation variables and precipitation
Output Format: GRIB
Download Path: /home/juantuf/Descargas/ERADATA/single_levels-ERA5.grib
2. Era_5_levelpressure.ipynb
This script retrieves ERA5 data on multiple pressure levels. Users can specify the year, months, and days of interest, and download data for a range of meteorological variables on various pressure levels.

Variables Retrieved:
Atmospheric parameters like temperature, humidity, wind components, and cloud properties
Geopotential, divergence, vorticity, and other dynamical fields
Pressure Levels: From 1 hPa to 1000 hPa
Output Format: GRIB
Download Path: /home/juantuf/Descargas/ERADATA/pressure_levels-ERA5.grib
Execution Instructions
Clone the Repository:

Clone the repository to your local machine:

bash
Copiar código
git clone <repository_url>
cd <repository_directory>
Run the Jupyter Notebooks:

Open the terminal, navigate to the directory containing the scripts, and start Jupyter Notebook:

bash
Copiar código
jupyter notebook
Open either Era_5_singlelevels.ipynb or Era_5_levelpressure.ipynb in Jupyter and run the cells sequentially. You will be prompted to enter the year, months, and days for which you want to retrieve data.

Check the Downloaded Files:

The downloaded GRIB files will be saved to the specified paths. These files can be used directly as initial and boundary conditions for WRF model simulations.

Troubleshooting
API Connection Issues: Ensure your CDS API key is correctly configured and you have a stable internet connection.
Data Download Issues: Check that the specified year, month, and day inputs are valid and that the requested data is available in the CDS.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgements
The scripts use the cdsapi library to interact with the Copernicus Climate Data Store.
The ERA5 data is provided by the European Centre for Medium-Range Weather Forecasts (ECMWF).

# AtmosForge-ERA5toWRF
