[<<< Previous](1basic.md)  | [Next >>>](3layer1.md)  

# Phase 2: Import, Geocode and Visualize data

## Steps

#### 1.	Open ArcGIS Online: https://www.arcgis.com/home/index.html , and Sign in. If you don’t have an account, you can get one using your Google account or even Facebook.

#### 2.	Select “Map” on the main toolbar

#### 3.	Now, let’s add our shapefile “ManhattanMedHHI”
* Select: Add-->Add layer from file
* Navigate to the zip file “ManhattanMedHHI.zip and upload it.
* Select the option “Keep original features”. The Generalized version simplifies the boundaries of the shapes.

#### 4.	Style the map by following the directions on the left side toolbar:
* You can quickly visualize the data by selecting an attribute (variable) from the drop-down list, then selecting one of the proposed visualizations.
* For this exercise, let’s select MdHHInc as the attribute, then select “Counts and Amounts (color)”. You will see that the map changes into colors representing the values of the median income in each NTA.
* Be sure to click “Done” otherwise it wont save the changes
  * *Note: You can click on “Classify” if you want to change how the data is visualized and how many categories are created. “Natural breaks” is a good option because it increases variability between classes while decreasing it within classes. Additionally, you can change the colors and the color scale.*
* Once you’re done checking the Options, click on OK, then on Done.

#### 5. Now, let’s add our 10 NYC Sites
* Select: Add-->Add layer from file
* Navigate to the file “NYCSites.csv” and upload it

#### 6. You will be prompted by an option to geocode your sites. This means using the address to find the latitude and longitude so you can add the points to your map.
* Check to see if the variables for “Address” “City” “State” and “Zip” are matching. If they are then click the “Add Layer” button

 *Note: ArcGIS will only geocode up to 100 entries. If you have more than 100 then you can use the Census Geocoder, which geocodes up to 1000 entries*

#### 7. Check make sure that the geocode was successful and your sites showed up in the right place
* You’ll notice that the Statue of Liberty is being plotted in Lower Manhattan. Let’s fix that!
  * Although it is not “best practices”, we are going to move the point manually.
  * Click on “Edit” on the top menu. Hover your mouse over the Statue of Liberty point and click on it. A description should pop up.
  * While this description is open, click and hold on the point itself and you will be able to drag it to its appropriate location. Again, this is NOT best practices, but ESRI ArcGIS online limits the capabilities to fix this type of issues.
  * A good solution could be finding the appropriate latitude and longitude for the points (even Google Maps can be helpful for this), then creating two columns for lat and long on your spreadsheet. Any GIS software is able to read these columns and identify the position of the points.
  * Once you’re done, turn off the edit option and go back to the Details panel by clicking on “Details” on the top menu.

#### 8.	Let’s configure a pop-up based on the information that we have in the NYC Sites layer. 
* Select: More options (the three-dot icon under the layer name)-->Configure pop-up
* Go to “Configure attribute” and select the variables that you want to be displayed in the pop-up. Let’s make sure all of the variables related to the photos are not selected. We will add those separately. I would select the “name” “year built” and “context”.
* To add the photos:
  * Scroll down to the “Media pop-up” section and select: Add-->image 
  * Recommended Selections
    * Title: Then
    * Caption: {OldPhotoYear}
    * URL: {OldPhoto}
* You might also have noticed that years are shown as “1,911” instead of “1911” in the popup, and this really annoys us. Let’s fix it in the “Configure Attribute” box; select the attributes that involve years and deselect the box to the right that says “Use 1000 separator”. 
* Remember you will have to click on “OK” below before the changes are reflected on the pop-ups.

#### 9.	Let’s configure another pop-up based on the information that we have in the base layer. 	Try to create a pop-up that only shows the value for the median household income and the name of the neighborhood.
* You can change the name of the variable if you simply double click on it

#### 10.	Let’s add labels for the sites
* For the New York City Sites layer click “Manage labels” and add the “Name”

#### 11.	Save your map


[<<< Previous](1basic.md)  | [Next >>>](3layer1.md)  
