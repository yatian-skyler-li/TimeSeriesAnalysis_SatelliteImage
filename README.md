# TimeSeriesAnalysis_SatelliteImage
This project examined a time series of Normalized Difference Vegetation Index (NDVI) values from the MODIS Terra satellite imagery using terra, sf packages for spatial data and bfast algorithm for time series analysis. This project also analyzed 33 years time series of land cover maps from Landsat satellite imagery and generated forest dynamics map.

## Packages used in this project
- Spatial Data Analysis
  library(terra)
  library(sf)
  
- Tidyverse Packages used for Data Frame Management and Visualization
  library(readr)
  library(stringr)
  library(lubridate)
  library(dplyr)
  library(tidyr)
  library(ggplot2)

- Algorithm for time series analysis
  library(bfast)
  The Breaks for Additive Season and Trend (BFAST) algorithm has been developed to identify long term trends and abrupt changes (breaks) in time series while explicitly accounting for the seasonal component (Verbesselt et al., 2010).

## MODIS time series analysis
This project uses NDVI Data from the MODIS Terra product MOD13Q1. Feel free to navigate to the following website to read about the product: https://lpdaac.usgs.gov/products/mod13q1v006/ 

Here are some key information on the MODIS Terra dataset
- spatial resolution: 250 meter
- temporal resolution: 16 days
- temporal availability: 2000-02-18 to 2023-02-17
- valid range of NDVI values (1st layer in dataset): -2000 to 10000

The time series of cleaned MOD13Q1 NDVI layers is located in the "data/MOD13Q1_TS" directory. The date of the time series is indicated in the file name a sequence of 7 numbers after the letter `A`. The first four numbers indicate the year and the next three numbers indicate the day of the year. 

## Land cover time series analysis
The land cover maps classified from Landsat imagery was also used in this project. The classification was performed using the Virtual Land Cover Engine (VLCE; [Hermosilla et al., 2017](https://www.tandfonline.com/doi/full/10.1080/07038992.2018.1437719)). 

The VLCE classifies land cover into the following classes: 
- Water (class 20)
- Snow/Ice (class 31)
- Rock/Rubble (class 32)
- Exposed/Barren Land (class 33)
- Bryoids (class 40)
- Shrubland (class 50)
- Wetland (class 80)
- Wetland-Treed (class 81)
- Herbs (class 100)
- Coniferous (class 210)
- Broadleaf (class 220)
- Mixed Wood (class 230)

The folder "data/VLCE_TS" contains the time series of VLCE land cover maps for the study area. This project focused on a ~ 25 x 20 km area near Williams Lake, BC where active forest management practices take place. The aim of the lab is to examine the evolution of total forested area through time in this area as a balance between forest area loss (e.g. harvesting) and gain (e.g. forest regeneration). 

## Credits
The original design of these project are from Prof. Nicholas Coops (nicholas.coops@ubc.ca) and Liam Irwin (lakirwin@ubc.ca). The scripts are developed by Skyler Li.



