[<<< Previous](../README.md)  | [Next >>>](2setup.md)  

# Phase 1: Find, Clean and Manipulate data

## Datafiles

10 Popular NYC Sites
* http://bit.ly/DRIMapping2020 
* File is called “NYCSites.csv”

Median Household Income by Neighborhood
* Data Source: https://data.cityofnewyork.us/City-Government/Demographic-Profiles-of-ACS-5-Year-Estimates-at-th/8cwr-7pqn 

Shapefile of NYC neighborhoods (called Neighborhood Tabulation Areas or NTAs)
* Data Source: https://data.cityofnewyork.us/City-Government/Neighborhood-Tabulation-Areas/cpf4-rkhq


## Steps

#### 1.	Let’s open each of the files in order.


#### 2.	You will see the the “NYCSite.csv” file has already been cleaned for you, so that it only includes the information that we want. Let’s ignore that file for now and work on the ones that need to be cleaned.


#### 3. Let’s get the data on the Median Household Income by Neighborhood
* Download the Excel Spreadsheet on this site: https://data.cityofnewyork.us/City-Government/Demographic-Profiles-of-ACS-5-Year-Estimates-at-th/8cwr-7pqn 
* Unzip the file ACS5yrNTA.zip, then open the file called “econ_2016acs5yr_nta.xlsx” using Excel or any similar spreadsheet editor. 


#### 4.	Let’s clean the data on the Median Household Income by Neighborhood
* The first step is to do a “save as” so you can keep the original document as a reference before you start cleaning the data. Let’s name the file “MedianIncome.xslx”. 
* Now let’s find the data that we want and remove the data that we don’t need. 
* We want the median household income, so let’s find that in the Dictionary tab.
  * We are going to keep “MdHHIncE,” the “Pop16plE” and the variables that are keys or identifiers, such as the GEOID, GeoGName, Borough, and we are going to delete the rest of the variables.
  * Make sure that “MdHHIncE” and “Pop16pIE” are formatted as numbers. To do this, you can select the whole columns from row 2 to the last one, then right-click on the selection, click on “Format cells…”, then select “Number” from the category list. Also, specify decimals to “0”. The reason for this is that sometimes converting Excel files to comma-separated-value files (CSV) can bring about some formatting conflicts, so this will hopefully get rid of some of it.
  * Save the file as a CSV. I called mine “JoinClean”
  * *Note: Another useful way to define column formats is creating a csvt file that specifies the format of each column in a csv file of the same name in the same folder. The csvt is just a txt file which contains text in the form of: "String","Real", "Integer", "String". In this example, column one will be interpreted as a string (text), column 2 as a real number (number with decimals), column 3 as an integer, and so on. We will not do this in this exercise.
* Be sure to save your changes.


#### 5.	Let’s get the shapefile of NYC neighborhoods (called Neighborhood Tabulation Areas or NTAs)
* Download the shapefile on this site (click on Export, then “shapefile”): https://data.cityofnewyork.us/City-Government/Neighborhood-Tabulation-Areas/cpf4-rkhq
* Save the zip file somewhere that you can easily navigate to.
* *Note: Shapefiles are generally shared in Zip files, because shapefiles are not self contained in a single file, but a composite of several files of different formats that must be all together in the same folder and all have to share the same file name (similar to csv files and their csvt type references). GIS software knows how to read zip files that contain a single shapefile. ESRI ArcGIS online is one of these, and can only read shapefiles when uploaded as Zip files.*


#### 6.	Perform a spatial join between the shapefile of NYC neighborhoods and the spreadsheet “Median Household Income by Neighborhood”
*Note: ESRI ArcGIS online free version does not allow to do spatial joins, so you will need another software such as QGIS to perform the spatial join.* 
* Open QGIS
* Import the shapefile
  * Click the “Open data source” button and navigate to the “Vector” tab. 
  * Upload the zip file “Neighborhood Tabulation Areas (NTA)”
* Import the CVS file
  * Click the “Open data source” button and navigate to the “Delimited Text” tab. 
  * Upload the csv. file “JoinClean”
* Check to make sure that both of the keys are the same field type
  * Double click on the layer, navigate to the “Fields” tab.
  * If the field types are different, the easiest solution is to change the field type of the key in the csv file to match the field type of the shape file. This needs to be done in your spreadsheet manager. 
* Perform a spatial join
  * Double-click on the shapefile and navigate to the “Join” tab
  * Click the plus sign 
  * Select “JoinClean” as your join later
  * Select “GeoID” as your join field
  * Select “ntacode” as your target field
  * Check all of the join fields
  * Check “Custom Field Name Prefix” and leave it blank
  * Click both “Ok” buttons to execute the join
* Check to make sure the join was successful
  * Open the attribute table for the neighborhood shapefile
  * If the fields from the cvs file have been added, the join was successful!


#### 7.	Check the field types to make sure they are correct
* If they are not you have to change them. We are particularly interested in making sure that the MdHHIncE and the Pop16Ple are integers. If they aren’t then follow the following steps.
* Open the attribute table for the shapefile
* Click on the “open field calculator button”
* Name the field 
  * for MdHHIncE I renamed it to Hhinc
  * for Pop16Ple I renamed it to Pop
* Enter the field that you are converting it from
* Click ok
* Check to make sure the new field type has been updated


#### 8. Delete the other boroughs and only keep Manhattan
* Select “Select features by value”
* For “boro_name” select “Equal to” and input “Manhattan.” 
* Click “Select features” and “Close”
* Right-click on the neighborhood shapefile and select “Export” -> “Save selected features as” 
* Navigate to the folder that you want to save the file. I would create a new folder called “ManhattanMedHHI” and save the shapefile as the same name.
* In your finder window, navigate to the “ManhattanMedHHI” folder and compress it to create a zip file. 

  

[<<< Previous](../README.md)  | [Next >>>](2setup.md)  
