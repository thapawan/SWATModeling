# SWATModeling
Provide an introduction of Soil Water Assessment and Tool Modeling

# CrossSectionsExtractionVisualization (CSEV)
The cross-section extraction visualization tool automates extracting cross-sections with their horizontal distance and elevation. The repository contains notebooks and ArcGIS Pro Tool for cross-section extraction and visualization.

## Installation of required packages
For jupyter and ArcGIS Pro notebook use this command: install required libraries if not installed by uncommenting it:

#!pip install geopandas

#!pip install numpy

#!pip install pandas

#!pip install rasterio

#!pip install matplotlib

Other options, installing it by using the package manager in ArcGIS Pro, to add necessary packages to operate this program such as rasterio, geopandas, numpy, pandas, and matplotlib.

## Usage Guide
The easiest and quickest way to use the cross-section extraction visualization tool is to run it from ArcPro Toolboxes, where the functions can be directly loaded without setup. The tutorial for using the tool is shared on my YouTube channel (learnsomethingtoday): https://youtu.be/J0KKxBf-vLI

### Resources
#Video: https://www.youtube.com/watch?v=ml9sndHv-J8
#Blog: https://sites.google.com/view/learnswat/home/swatex?authuser=0&fbclid=IwAR2LfXRTvskfv9yNR8PxK16uE60e8RxdfAqKzoNP-wfGXpzBET97p5R2QJo

### Explanation
The code is an ArcGIS Python Toolbox that is designed to be used within ArcGIS Pro. It is a custom geoprocessing tool that performs the following tasks:

1. Takes input parameters:
   - Cross Sections Shapefile (a shapefile containing cross-sectional lines)
   - Digital Elevation Model (DEM) Raster (a raster dataset representing elevation data)
   - Number of points
   - CSV Output Directory (a directory for saving CSV files)
   - PNG Output Directory (a directory for saving PNG images)

2. Loads the cross-sectional lines from the provided shapefile as a GeoDataFrame using the `geopandas` library.

3. Iterates through each cross-sectional line in the GeoDataFrame and performs the following operations for each:

   a. Extracts the starting and ending coordinates of the line.

   b. Divide the line into a specified number of points (default: 5) and calculate the latitude and longitude of these points.

   c. Create a Pandas DataFrame containing latitude and longitude data.

   d. Converts the DataFrame to a GeoDataFrame, specifying the coordinate reference system (CRS).

   e. Calculates the horizontal distance (h_distance) for each point from the starting point of the line.

   f. Extract elevation data for each point from the DEM raster using `rasterio`.

   g. Extracts h_distance and elevation columns from the GeoDataFrame and stores them in a Pandas DataFrame.

   h. Saves the extracted data as a CSV file in the specified CSV output directory.

   i. Generates a plot of the cross-sectional profile, with h_distance on the x-axis and elevation on the y-axis, and saves it as a PNG image in the specified PNG output directory.

4. If any errors occur during the execution of the tool, it reports the error message.

5. The `postExecute` method is called after the tool has been executed, but in this case, it does not perform any additional actions.


## Acknowledgement
I acknowledge the YouTube video made by the GeoDev Tools channel for the video of the crosssection extractor and the valuable feedback by the GY539 GIS Programming  advisor (Dr. Hongxing Liu) and (Dr. Dan Tian), also for other direct and indirect contributions to build and implement this tool.

Dong, P., Zhong, R., Xia, J., & Tan, S. (2020). A semi-automated method for extracting channels and channel profiles from lidar-derived digital elevation models. Geosphere, 16(3), 806-816.

## Contact
Open for collaboration and welcome any valuable feedback or suggestions for improvement. If you have any queries about the algorithm, open for discussion and contact:
pthapa2@crimson.ua.edu.

## Future work
Currently, it provides CSVs and PNG files further extension is available in the GitHub repository with the folder name of CrossSectionsExtractionVisualizationExtension which tool tries to convert point to line which has shapefile (.shp), raster (.tif) and save it in the ArcGIS Pro content.

