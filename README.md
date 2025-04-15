Link to notebook:  https://github.com/NaglaElb/Projects/blob/40505530888eabbbcee05c58cb984393adb0b329/used_car_features%20analysis.ipynb



Overview:
This notebook contains an analysis of data from a Kaggle data set of used cars. The original data set included 18 columns and about 140000 cars and their features.  The assignment is to assist used car sales owners with an understanding of the features that drive up the prices of cars.

The predictability of this data on car price is low, mostly because the majority of provided features are categorical, rather than numeric.  The first recommendation to the client is that Kelley Blue Book Values will provide a better indication of the car value.  This analysis will provide an indication of the features that increase value to their customers.

Data:
The data had to be updated to address empty values and to derive more meaningful categories for data transformation.

NaN values were first populated, where possible, either by calculating a median value of deriving the data from other columns. For columns with over 30% NaN values, the entire column was dropped in order to save the important data from the other columns.  

The following columns were dropped:
'id', 'VIN','region', 'state', 'type', 'drive', 'model','manufacturer','odometer', 'title_status', 'paint_color'

The following columns were added with the definitions included:
luxury: uses model, manufacturer to categorize car as antique, luxury, other
odometer_category: converts odometer readings into high medium and low 
color_type: combines common colors of black, white, silver, grey, red, blue into a standard color, continues to use the custom color category and puts everyting else into a rare category
age: 2025 less the year of the car, numeric value
gregion: states grouped into 4 regions, northwest = 'ca', 'co', 'ak', southwest = 'az', 'ar', southeast = 'fl', 'dc', 'al', northeast = 'de', 'ct'


Observations about used car features
The number one characteristic was transmission type, with manual transmissions resulting in higher prices versus manual or other transmission types.
Following transmission was fuel type with diesel resulting in higher prices than gas or hybrid cars. 
Geographic region can impact a car price, so this is a good area to provide as follow on work for clients who want more focused analyses for their region.


Next Steps:
For an additional low price, this analysis can be customized for specific used car dealerships by focusing on a specific region or type of car, maybe specific manufacturers.
