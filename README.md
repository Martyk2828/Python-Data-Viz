#Python-Data-Viz

This dataset contains yearly data across 5 categories - electricity generation, capacity, emissions, import and demand data for over 200 geographies from the years 2000 through 2021

#Source

Data is collected from multi-country datasets (EIA, Eurostat, BP, UN) as well as national sources (e.g China data from the National Bureau of Statistics). Link to source: https://ember-climate.org/data-catalogue/yearly-electricity-data/

#Cleaning

The country specific columns like 'EU', 'OCED', 'G20' and 'G7' have 2 values (0 or 1) indicationg whether a country is part of these groups or not. For the Area Type as 'Region', the country specific columns have been marked as -1(denoting 'not applicable')

Country Code represents are 3-letter abbreviations for denoting the countries. For Area Type as 'Regions', these country codes are not applicable, and hence are filled by 'NA'.

Ember Regions are defined in by the source of the dataset: https://ember-climate.org/countries-and-regions/ The value of the ember_region column denotes whether the country is a part of the region or not. For Area Type as Region, this column will also not have a value and therefore is filled as 'NA'

The values for Continent are filled with the appropriate values wherever possible. Else the values are filled with 'NA' for regions which are not part of a particular continent

For the first data year (2000), yoy_abs_change is undefined since there is no data for previous year, therefore setting it as 0 SPECIAL CASES - countries established after data start period (Montenegro, South Sudan and Timor-Leste), yoy_abs_change values for their start year will be zero

Since granular data for an entire category (Capacity) is missing for all the years for only these countries, and the missing data is very specific - for e.g. the Capacity of Bioenergy Fuel for generation of eletricity in 2001 for Bahrain, it would be better to fill in these specific missing values with zeroes instead of any aggregate measure like mean so as to avoid introducing any distortions in the data.
Also, since there is no value, the column yoy_abs_change should also be made 0 for such rows.

Similarly, granular factual data points in other categories such Power Sector Emissions, Electricity Generation data from multiple small countries is also missing for the entire data collection period - for e.g., 
   1)emissions in Bermuda caused by Gas & other fossil fuels for the year 2005 
   2)% of electricity generated in Gibraltar by using Hydro electrictiy in 2001
To avoid any distortions to the data set, such values have also been filled as 0

For percentage data, i.e. when unit column equals %, the column for absoloute change yoy_abs_change is irrelevant since values are in percentages, thus assigning the values for column yoy_abs_change as 0

#Visualization

Visualizations have been done using the column - 'value'. Values from other columns such as 'category' and 'subcategoy' have been chosen and each visualizations describes the rows and columns used.

#1 Bar Graph of Electricity Generation data (Fossil fuels vs Clean fuels) for Asia region

Electricity Generation Data for sub-category Aggregate fuel has been visualized for the continent Asia in a stacked bar graph as shown below:

#2 Pie Chart showing comparsion of Electricity Generated using various sources

In the Pie Charts, we have compared detailed breakdowns of Electricity Generation data for for 2 countries - India, which is considered to have a developing economy and USA, which is considered to be a developed economy, for the years 2000 and 2021.
This helps us understand the changes in choice of Fuels used to generated electricity made by those 2 countries over 20 years and also how those 2 countries compared to each other in 2000 and 2021.

#3 Line Graph for Electricity Demand and Demand per capita across all continents over 20 years

The line graphs show Electricity Demand and Demand per capita from 2000 to 2021 for all 6 continents - Asia, Africa, North America, Latin America, Oceania and Europe.

#4 Scatter Plot showing Total Emissions and Emissions Intensity for the 4 highest GDP countries 

The 2 scatter plots show Total Emissions from the generation of electricity (in metric tons of CO2) and the Emissions Intensity (in grams of CO2 per kiloWatt-hour of electricity generated) for the 4 countries with the highest GDP in 2022.

#5 Histogram showing trend of Emissions across all countries for 2000 and 2021

The histograms show the number of countires grouped as per their Total Emissions in metric tons of CO2 for 2 years 2000 and 2021.
The linear scale histograms clearly show that the data is skewed and thus, to further enhance the visualization, we have plotted the same histograms using logarithmic scale on the X-axis. 

#6 Box Plot showing regional emissions distribution as per hemispheres (Northern and Southern)

The box plots show region-wise emissions data for the 3 major regions in each hemisphere - 
1. Asia, Europe and North America for the Northern Hemisphere
2. Africa, Latin America and Oceanis for the Southern Hemisphere

#7 Heat Map showing Emissions Intensity (in grams of CO2 per kiloWatt-hour of Electricity generated)

The heat map shows the emissions intensity in each of the six continents in the world - Asia, Africa, North America, South America, Oceania and Europe plotted for each year between 2000 and 2021.

#Conclusion

As per the 7 visualization, since developing regions such as Asia and Africa show higher emissions than developed regions like North America and Europe and also have greater intensity of CO2 emissions per kWh of electricity consumed. we can conclude that the transition towards using cleaner forms of energy such as Wind, Solar, Hydro and Nuclear in developing regions still has a long way to go, and currently these regions appear to be amongst the bigger drivers of climate change. However, like we saw in the line graphs of Electricity Demand and Demand per Capita, additional data such as Power Emissions per capita for each of the countries could show a different picture as these developing regions have large populations
