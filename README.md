# Mount Rainier Eruption Disaster Estimate
___

## Disaster Estimates

Assessing the potential effects of a disaster is as important as it is complex.  Given measurable financial factors such as land and structural property it is possible to make a good prior estimate. This can be used as a starting point to understand the scope of an event.  We chose to focus on the lahar flows from a volcanic eruption of Mt. Rainier. These lahar flows are well defined geographical boundaries based on historic flow information.
___

## Problem Statement

Estimate the property damages caused by the lahar flow of Mt. Rainier, when it erupts.
___

## Data Science Process

We collected tax parcel data from three different counties, and unsucessfully attemped to collect from one additional county. Specifically, we accessed the Pierce, King, and Thurston County Tax Assessor offices to gather the taxable land and structure value, along with address and coordinates. We also acquired shapefiles for the Mt. Rainier volcanic lahar flows from a study conducted by the USGS. We used QGIS to map these and overlay the tax parcel data by latitude and longitude. From there, we isolated the properties that were at risk of being caught in the lahar. We then aggregated all the at-risk property values to get our baseline estimate. However, the taxable value from the tax parcels data consistently underestimates the true market value of the property. We turned to Zillow to find a more accurate estimate of the true value of the property. However, Zillow does not have a complete database of every single parcel in every county. We gathered almost 900 parcels of data to compare and then ran a related t-test to prove the statistical signifiance of the differences. The difference in mean of the 900 properties was used to compute the true market value across our population.

This process allowed us to reach a baseline estimation of just under 20.5 billion dollars in total property damage caused by the lahar flow from a potential eruption of Mount Rainier. This model is a fairly conservative estimate, as it only considers lahar flows. In addition, it only estimates the property values and not the overall economic impact. 

This model could be easily generalized to other volcanic eruptions, and potentially even other disasters with definable boundaries such as flooding. Given tax parcel data and a shapefile of historic evidence of the disaster area in question, a baseline property value could be assessed. Even without a specific disaster, the process of collecting tax parcel data and cross referencing that with data collected from Zillow or other real estate websites can be generalized to any area of interest. 
___

## Issues

1. Data collection
    - Data colletion was a significant challenge. All the counties had the data in some form or another, but obtaining the data in a useable form proved challenging. Lewis County in particular did not have data readily accessible for download. They had an intertactive GIS map on their website, but there was no way to download the data.
    - Thurston County did not have the lattitude and longitude coordinates on their data file. This was solved by doing a geo-coding look-up using the Nominatum (https://wiki.openstreetmap.org/wiki/Nominatim) geocoding tool. While this tool was free, it had significant gaps. Thurston County data is incomplete, and we are unaware of a way to statistically relate our sample results to the population in order to generalize.
2. Software
    - QGIS was the tool we had available to determine if our tax parcels were within the lahar shapefile boundaries. While this worked, we were unable to find a way to do it entirely within Python, thereby streamlining the process.

___
    
## Moving Foward
1. Better Data.
    - Having the time and, more importantly, the resources, to gather better data will result in a much more accurate model.
2. Python Script
    - Having the time and resources to impliment a pure Python approach will make this project generalizable and portable.
___

## Sources

1. USGS (https://volcanoes.usgs.gov/volcanoes/mount_rainier/hazard_lahars.html)
2. King County (https://gis-kingcounty.opendata.arcgis.com/search?tags=property_OpenData)
3. Pierce County (https://gisdata-piercecowa.opendata.arcgis.com/datasets/tax-parcels)
4. Thurston County (https://gisdata-thurston.opendata.arcgis.com/datasets/thurston-parcels)
5. Lewis County (https://gis.lewiscountywa.gov/webmap/)
    - Note: This is only the interactive webmap.


## Directory Structure
```
project-3
|__ notebooks
|   |__ King_County_Data_Prep.ipynb  
|   |__ Thurston_County_Data_Prep.ipynb  
|   |__ Get_Zillow_Values.ipynb  
|   |__ baseline_model.ipynb  
|   |__ data_cleaning.ipynb  
|   |__ lat_long_coordinates.ipynb   
|   |__ shape_file_display.ipynb 
|   |__ zipcodes.ipynb  
|__ datasets
|   |__ bar.csv
|   |__ fb.csv
|   |__ mc.csv
|   |__ mls.csv
|   |__ ssfc.csv
|   |__ tfr.csv
|   |__ tfys.csv
|__ DSI-007-SEA Group Recording
|   |__ audio_only.m4a
|   |__ playback.m3u
|   |__ zoom_0.mp4
|__ project_04_presentation.pdf
|__ README.md
```