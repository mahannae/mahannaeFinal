# State of Washington Electric Vehicle Density

## Project Table of Contents

- [Introduction](#introduction)
- [Data Source](#data-source)
- [Project Background](#project-background)
- [Purpose](#purpose)
- [Mapmaking Process](#mapmaking-process)
- [Map Summary](#map-summary)
- [Final Project Link](#final-project-link)



***
### Introduction 
<p> This mapping project found its start through the curoisty of going through the United States Data.gov website. This website has over a quarter million data sets to filter through. From registered electric vehicles (EV), average fruit and vegetable prices, and even bird strikes on aircraft this catalog of data is very diverese and deep. While trying to decide what to map for this project I ran across the State of Washington's registered EV dataset that was compiled by their State Department of Licensing. 

This caught my eye because Washington is a state that is commonly associated with environmentalism and being "green". I thought it would interesting to see the the distribution of EV's for the state. This dataset set showed that there are over 150,000 registered EV's for the state which was surprising but allowed for just that many more data points to pull from. While I could have overlayed this over a county map for the state and visualized the density by county I decided to use a hexgrid to better visualize this data. This breaks down the counties into much smaller areas to better visualize their distribution across the state. </p>

### Data Source
<p>The data from this map comes from the Electric Vehicle Dataset from Washingtion State Department of Licensing. This is a registry of all electirc vehicles registered in the state of Washington. This registry contains approximately 150,000 vehicles. 
The county basemap comes from the United States Census Bureau's  County 1:500,000 Shapefile.</p>

[Link to Electrice Vehicle dataset source](https://catalog.data.gov/dataset/electric-vehicle-population-data)

[Link to County Basemap data source](https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html)



<p></p>

### Purpose
<p> The purpose behind the creation of this map was to help visualize the density of EV's in the state of Washington. This visualization helps to see how the density is spread across the state through the hexgrid. </p>

### Mapmaking Process
<p> The map making process begins with importing the two datasets into QGIS. The county basemap is added as a vector layer. The EV Dataset is added as a deliminated text layer. Next both layers are filtered to the state of Washington. This will make the county map just show the State of Washington. For the EV dataset this will remove any vehicles that are still currently registered from Washington but are not currently located within the state. After filtering these layers they are then exported as a Geopackage. They are exported to a Geopackage to change and save the map CRS. For this map the CRS is NAD27 / Washington North- EPSG 32048. Then these geopackages are added back into the map with the project CRS changed as well so all point align project properly. Next the hexgrid will be created. Note that in this CRS the unit is feet. Go to MMQIS/Create/Grid Layer. You will select a hexagon grid layer with the x value = 50,000. Click Run. This will create a hexgrid layer of a 50,000 foot short diagonal across your map. Now that the hex grid is created it is time to join the EV data and this grid. You will go to Vector General/Join Attributes by Location (summary). </p>
Example of in process map ![in process image](filepath)

1. **Example bold**
2. *Example italics*
3. 
4. 

### Map summary
<p>Overall this map visualizes the density of EV's in the State of Washington well through the Hexgrid. This state hosts approximately 150,000 EV's. This map shows several pockets of concentration of these EV's across the state.  </p>
Across the README.md file, please answer the who, what, when, where, why, and how of the map making process

![Intial Map Projection](/Graphics/intialprojection.PNG)   
*Initial Map Projection*

![Final Map Projection](/Graphics/finalprojection.PNG)   
*Final Map Projection*


## Final Project Link

Please view the [final map online](https://github.com/mahannae/mahannaeFinal/blob/main/index.html)