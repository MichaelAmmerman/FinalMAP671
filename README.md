# McDonald's Location's in Contiguous US

## Data Source's
* McDonald's location data was provided by [Gavin Rehkemper](https://github.com/gavinr/usa-mcdonalds-locations) data accessed October 2023.
* State population and state's shape file was provided by [US Census Bureau](https://www.census.gov/en.html).
* North American shape file was extracted from [The University of Texas at Austin](https://geodata.lib.utexas.edu/?f%5Bdc_format_s%5D%5B%5D=Shapefile&f%5Bdct_spatial_sm%5D%5B%5D=North+America&f%5Blayer_geom_type_s%5D%5B%5D=Polygon&per_page=50&sort=score+desc%2C+dc_title_sort+asc).
* McDonald's location data was provided by [Gavin Rehkemper](https://github.com/gavinr/usa-mcdonalds-locations) data accessed October 2023.
* State population and state's shape file was provided by [US Census Bureau](https://www.census.gov/en.html).
* North American shape file was extracted from [The University of Texas at Austin](https://geodata.lib.utexas.edu/?f%5Bdc_format_s%5D%5B%5D=Shapefile&f%5Bdct_spatial_sm%5D%5B%5D=North+America&f%5Blayer_geom_type_s%5D%5B%5D=Polygon&per_page=50&sort=score+desc%2C+dc_title_sort+asc).

## Reason for Creating this Map

I am an extension associate at the Universiy of Kentucky for the Dapartment of Forestry. My job requires that I travel all over the state of Kentucky. While traveling throughout the state, I have spent a lot of time in the state's largest and smallest cities. Over time I have noticed one thing that almost everytown has and that is either a Subway or McDonalds. This observation made me start to wonder what states have the most McDonalds and what trends cause this. I hypothesised that states with smaller populations would have more McDonalds for fewer people. After analysing and mapping the data I relized that my hypothesis wasa mostly correct, but it seems states within the southern us had more McDonald's.

## Map Creation
1. I downloaded the McDonald's data from Gavin Rehkemper's github repository, then I downloaded data from the Census Bureau and the University of Texas at Austin.
2. I then used MS Access to get a a count of McDonald's per state by using the query SELECT state, COUNT(state) AS CountState FROM Mcdonalds.
3. I then used QGIS to join the McDonald's count per state by joining the us_states_name and name. Then I joined the state polutlations using the attribute's name on both the us_States file and the State_pop file.
4. After the joins I then used the field calculator to creatve a field called mcds_per_state by diving state_pop by CountState.
5. I then created three Choropleth Map using the fields State_pop, mcds_per_state, personPermcds. 
6. I then uploaded the geojson to mapbox studio and then published it and added it to the HTML file.

## Link to Map
[Map](https://michaelammerman.github.io/FinalMAP671/)

## Projection

All of the orginal data was originally projected into NAD 83, I then reprojected all layers into North_America_Albers_Equal_Area_Conic (ESRI 102008).
