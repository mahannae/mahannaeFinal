# State of Washington Electric Vehicle Density

## Project Table of Contents

- [Introduction](#introduction)
- [Data Source](#data-source)
- [Purpose](#purpose)
- [Mapmaking Process](#mapmaking-process)
- [Map Summary](#map-summary)
- [Final Project Link](#final-project-link)



***
### Introduction 
<p>This mapping project found its start through the curoisty of going through the United States Data.gov website. This website has over a quarter million data sets to filter through. From registered electric vehicles (EV), average fruit and vegetable prices, and even bird strikes on aircraft this catalog of data is very diverese and deep. While trying to decide what to map for this project I ran across the State of Washington's registered EV dataset that was compiled by their State Department of Licensing. 

This caught my eye because Washington is a state that is commonly associated with environmentalism and being "green". I thought it would interesting to see the the distribution of EV's for the state. This dataset set showed that there are over 150,000 registered EV's for the state which was surprising but allowed for just that many more data points to pull from. While I could have overlayed this over a county map for the state and visualized the density by county I decided to use a hexgrid to better visualize this data. This breaks down the counties into much smaller areas to better visualize their distribution across the state. </p>

### Data Source
<p>The data from this map comes from the Electric Vehicle Dataset from Washingtion State Department of Licensing. This is a registry of all electirc vehicles registered in the state of Washington. This registry contains approximately 150,000 vehicles including their lat/long coordinate location. For any vehicle registered in the state but not currently located in the state it was filtered out. 

The county basemap comes from the United States Census Bureau's County 1:500,000 Shapefile. The county basemap was filtered to just show the State of Washington. </p>

[Link to Electric Vehicle dataset source](https://catalog.data.gov/dataset/electric-vehicle-population-data)

[Link to County Basemap data source](https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html)

### Purpose

<p> The purpose behind the creation of this map was to help visualize the density of EV's in the state of Washington. This visualization to show the density across the state is through a hexgrid. </p>

### Mapmaking Process

<p> The map making process begins with importing the two datasets into QGIS. For this map the CRS is NAD27 / Washington North- EPSG 32048. The county basemap is added as a vector layer. The EV Dataset is added as a deliminated text layer. 

![Base Layers](/Graphics/Rawdatalayers.PNG)

*Intial Projection*

Next both layers are filtered to the state of Washington. This will make the county map just show the State of Washington. For the EV dataset this will remove any vehicles that are still currently registered from Washington but are not currently located within the state. The original dataset has 150,482 vehicles. After filtering there are 150,141 vehicles mapped. 

![EV Data Filter](/Graphics/EV%20data%20filter.PNG)

*EV Data Filter*

![County Filter](/Graphics/County%20Filter.PNG)

*County Basemap Filter*

After filtering you map should look similar to this. 

![Intial Map Projection](/Graphics/intialprojection.PNG)  

*Filtered Map Projection*

 After filtering these layers they are then exported as a Geopackage. They are exported to a Geopackage to save all changes and make sure the CRS is correct (this is helpful for further functions ease of operation). 

 ![Geopackage](/Graphics/Geopackage%20export.PNG)

 *Geopackage Export*
 
 Then these geopackages are added back into the map. 
 Next the hexgrid will be created. *Note that in this CRS the unit is feet. Go to MMQIS/Create/Grid Layer. You will select a hexagon grid layer with the x value = 50,000. Click Run. This will create a hexgrid layer of a 50,000 foot short diagonal (x) across your map. 

 ![Hexgrid tool](/Graphics/Hexgrid%20tool.PNG)

*Grid Layer settings(add applicable file name and path to save it)*

![HexGridLayer](/Graphics/Hexgridlayer.PNG)

*HexGrid layered across map*

 Now that the hex grid is created it is time to join the EV data and this grid. You will go to Processing/ Toolbox/ Vector General/ Join Attributes by Location (summary). 

 ![JoinToolpath](/Graphics/Jointoolpath.PNG)

 *Where to find the join attributes by location (summary) tool*

 The settings for this tool should be as follows. 

 ![Join Settings](/Graphics/Joinsettings.PNG)

 You will fill in the drop down menus as shown. The fields to summarize are the FID for this data. The summaries to calculate is the count. Click on the box that says discard records which could not be joined. Then click run. You should receive a hexgrid that looks like this. 
 
 ![Basejoinhexgrid](/Graphics/basejoinedhexgrid.PNG)

 Next you need to edit the symbology of the joined layer. You can change the color scheme ase neccessary along with the background. Using the Natural Breaks helps to better visualize the data accurately. Turn the opcaity down to around 70 to still be able to see your county boundaries. 
 
 ![Mapeditedsymbology](/Graphics/Mapeditedsymbology.PNG)

 *Symbology Settings*

Once all edits are finalized you should see a projection similar to the one below. 

 ![Final Map Projection](/Graphics/finalprojection.PNG)   
*Final Map Projection*
</p>

### Map summary
<p>Overall this map visualizes the density of EV's in the State of Washington well through the Hexgrid. This state hosts approximately 150,000 EV's. This map shows several pockets of concentration of these EV's across the state. I believe that this map turned out very well for visualizing the density of EV's across the state. While creating this map I also made a density by county map and it was suprising how much that larger area really changes the focus of the viewer where the high numbers of EV's actually are. While there are areas in a county that have a high density there are areas with a very low density or no EV's at all. This is why I believe that a hexgrid makes this visualization better for correct interpretation.  </p>

<p></p>

### Final Project Link

Please view the [final map online](https://mahannae.github.io/mahannaeFinal/) 