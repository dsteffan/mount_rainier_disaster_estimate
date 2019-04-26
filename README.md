# Mount Rainier Eruption Disaster Estimate

## Disaster Estimates

Assessing the potential effects of a disaster is as important as it is complex.  Given measurable financial factors such as land and structural property it is possible to make a good prior estimate as a beginning to understanding the scope in one way to an event.  We chose to focus on the volcanic eruption of Mt. Rainier to add the element of defined geographic hazard zones based on historic evidence of volcanic behavior.

## Problem Statement

> Estimate the property damages caused by the lahar flow of Mount Rainier, when it erupts.

## Data Science Process

We collected tax parcel data from three different counties, and looked into finding data for two more. Specifically, we accessed the Pierce, King, and Thurston county's assessor's offices to gather the taxable land and structure value, along with address and coordinates, amongst some other miscellaneous data. We also acquired shape files for Mount Rainier volcanic lahar flows, from a study conducted by USGS. We used QGIS to map these and overlay the tax parcel data by latitude and longitude. From there, we isolated the properties that were at risk of being caught in the lahar. We then aggregated all the at-risk property values to get our baseline estimate. However, the taxable value from the tax parcels data consistently underestimates the true market value of the property. We turned to Zillow to find a more accurate estimate of the true value of the property. However, Zillow does not have a complete database of every single parcel in every county, ____________ .

This process allowed us to reach a baseline estimation of just under 20.5 billion dollars in total property damage caused by the lahar flow from a potential eruption of Mount Rainier. This model is a fairly conservative estimate, as it only considers lahar flows. In addition, it only estimates the property values and not the overall economic impact. 

This model could be easily generalized to other volcanic eruptions, and potentially even other disasters with definable boundaries such as flooding. Given tax parcel data and a shapefile of historic evidence of the disaster area in question, a baseline property value could be assessed. Even without a specific disaster, the process of collecting tax parcel data and cross referencing that with data collected from Zillow or other real estate websites can be generalized to any area of interest. 

__**__NOTEBOOK HEADINGS GO HERE__**__
