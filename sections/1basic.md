[<<< Previous](../README.md)  | [Next >>>](2setup.md)  

# Phase 1: Find, Clean and Manipulate data

## Datafiles

10 Popular NYC Sites
* http://bit.ly/DRIMapping2020 
* File is called “NYCSites.csv”

Median Household Income by Neighborhood
* Data Source: https://data.cityofnewyork.us/City-Government/Demographic-Profiles-of-ACS-5-Year-Estimates-at-th/8cwr-7pqn 
* File is called “MedHouseInc.csv”

Shapefile of NYC neighborhoods (called Neighborhood Tabulation Areas or NTAs)
* Data Source: https://data.cityofnewyork.us/City-Government/Neighborhood-Tabulation-Areas/cpf4-rkhq

Shapefile and Median Household Income CSV combined
* http://bit.ly/DRIMapping2020 
* File is called “manhattanmhinc”


## Steps

1.	Let’s open each of the files in order.

2.	You will see the the “NYCSite.csv” file has already been cleaned for you, so that it only includes the information that we want. Let’s ignore that file for now and work on the ones that need to be cleaned.

3.	Let’s get the data on the Median Household Income by Neighborhood
* Download the Excel Spreadsheet on this site: https://data.cityofnewyork.us/City-Government/Demographic-Profiles-of-ACS-5-Year-Estimates-at-th/8cwr-7pqn 
* Unzip the file ACS5yrNTA.zip, then open the file called “econ_2016acs5yr_nta.xlsx” using Excel or any similar spreadsheet editor. 

4.	Let’s clean the data on the Median Household Income by Neighborhood
* The first step is to do a “save as” so you can keep the original document as a reference before you start cleaning the data. Let’s name the file “MedianIncome.xslx”. 
* Now let’s find the data that we want and remove the data that we don’t need. 
* We want the median household income, so let’s find that in the Dictionary tab.
* We are going to keep “MdHHIncE,” the “Pop16plE” and the variables that are keys or identifiers, such as the GEOID, GeoGName, Borough, and we are going to delete the rest of the variables.
* Make sure that “MdHHIncE” and “Pop16pIE” are formatted as numbers. To do this, you can select the whole columns from row 2 to the last one, then right-click on the selection, click on “Format cells…”, then select “Number” from the category list. Also, specify decimals to “0”. The reason for this is that sometimes converting Excel files to comma-separated-value files (CSV) can bring about some formatting conflicts, so this will hopefully get rid of some of it.
* Save the file as a CSV. I called mine “JoinClean”
* *Note: Another useful way to define column formats is creating a csvt file that specifies the format of each column in a csv file of the same name in the same folder. The csvt is just a txt file which contains text in the form of: “String”,”Real”,”Integer”,”String”. In this example, column one will be interpreted as a string (text), column 2 as a real number (number with decimals), column 3 as an integer, and so on. We will not do this in this exercise.
* Be sure to save your changes.




[<<< Previous](../README.md)  | [Next >>>](2setup.md)  
