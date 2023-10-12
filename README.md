# State of Washington Electric Vehicle Density

## Project Table of Contents

- [Data Source](#data-source)
- [Project Background](#project-background)
- [Purpose](#purpose)
- [Mapmaking Process](#mapmaking-process)
- [Map Summary](#map-summary)
- [Final Project Link](#final-project-link)



***

### Data Source
<p>The data from this map comes from the Electric Vehicle (EV) dataset from Washingtion State Department of Licensing. This is a registry of all electirc vehicles registered in the state of Washington. 
The county basemap comes from the United States Census Bureau's  County 1:500,000 Shapefile.</p>

[Link to Electrice Vehicle dataset source](https://catalog.data.gov/dataset/electric-vehicle-population-data)
[Link to County Basemap data source](https://www.census.gov/geographies/mapping-files
/time-series/geo/cartographic-boundary.html)


### Project Background

<p></p>

### Purpose
<p> The purpose behind the creation of this map was to help visualize the density of EV's in the state of Washington. This visualization helps to see how the density is spread across the state through the hexgrid. </p>

### Mapmaking Process
<p> The map making process begins with importing the two datasets into QGIS. The county basemap is added as a vector layer. The EV Dataset is added as a deliminated text layer. Next both layers are filtered to the state of Washington. This will make the county map just show the State of Washington. For the EV dataset this will remove any vehicles that are still currently registered from Washington but are not currently located within the state. After filtering these layers they are then exported as a Geopackage. They are exported to a Geopackage to change and save the map CRS. For this map the CRS is NAD27 / Washington North- EPSG 32048. Then these geopackages are added back into the map with the project CRS changed as well so all point align project properly. Next the hexgrid will be created. Note that in this CRS the unit is feet</p>
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

Please view the [final map online](www.github...)