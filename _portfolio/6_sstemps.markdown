---
layout: post
title: Sea Surface Temperatures
description: NOAA ICOADS dataset
img: /img/4.jpg
---
<br>
#### NOAA Sea Surface Temperature Data Analysis
<br>

The National Oceanographic and Atmospheric Association, NOAA, has dedicated scientists and advanced technology to provide reliable information about changes in climate, weather, oceans and coasts. Such information can be found online and it's available to the public. The NOAA dataset 'International Comprehensive Ocean-Atmosphere Data Set ICOADS' was used for this project. The dataset can be found in Google Cloud's [Marketplace](https://console.cloud.google.com/marketplace), and it has the following description:

> "The ICOADS dataset contains global marine data from ships (merchant, navy, research) and buoys, each capturing details according to the current weather or ocean conditions (wave height, sea temperature, wind speed, and so on). Each record contains the exact location of the observation which is great for visualizations. The historical depth of the data is quite comprehensive — there are records going back to 1662.
This public dataset is hosted in Google BigQuery and is included in BigQuery's 1TB/mo of free tier processing. This means that each user receives 1TB of free BigQuery processing every month, which can be used to run queries on this public dataset." 

Google BigQuery allows the database to be explored and manipulated using SQL queries. In this case, we want to explore the average sea surface temperature for the duration of 67 years, extending from the year 1950 to the year 2017. The main objective is to visualize the changes in sea surface temperature as a function of time.

Project Methods:

- Query the database using SQL to extract the data
- Export the results of the query into a readable Python format.
- Visualize important features in the data.
- Use machine learning methods to predict future sea surface temperatures.

The code for the project can be found in this [Github repository](https://github.com/jhmanchola/My_Projects/blob/master/NOAA_Ocean_Data_Analysis/NOAA%20Ocean%20Data%20Analysis-Copy1.ipynb).

<img src="../6_img/map_1.gif" class="center">

<strong>Map 1.</strong> Animation showing the change in the top average sea surface temperatures by year, from the years 1950 to 2017. As it is expected, the area along the equator has the highest average temperatures. Notice how the year 1950 has more lower temperatures and more locations on the top average temperatures than the year 2017. Each year has the top 200,000 readings averaged by location. The animation is showing an increase in sea surface temperature. The area in the Red Sea and the Persian Gulf stand out as the hotter places across all years.

<br>
#### Change of the highest averages per year and per location
<br>
For the range of 67 years for which the yearly sea surface temperature average was calculated, the following chart shows how the highest averages has changed.

<img src="../6_img/chart_1.png" class="center">

<strong>Chart 1.</strong> Each point is a map coordinate that had one of the 200'000 top temperature averages for each year. The highest average temperatures in 1950 are more spread and range almost from the low 20s to the mid 30s. As years increase, average temperatures increase and comprise a lower range ending in between the top 20s to the mid 30s. The lowest top averages (bottom points in each year) increase as well. This is why we see more blue colored areas in Map 1 for the year 1950 and a concentration of high temperatures in determined areas for the year 2017. 

The following visualization shows how temperature behaves as a function of location using longitude and latitude values:

<img src="../6_img/chart_2.png" class="center">

<strong>Chart 2.</strong> By changing the longitude there isn't much change for each temperature point. Longitudes, the imaginary lines moving East to West around Earth don't vary a lot. Latitudes (lines going North to South), on the other hand, show different temperatures according to the value. Latitudes on the equator have higher temperatures than those in the Northern and Southern Hemispheres. 

<br>
#### Methods of data collection for sea surface temperature
<br>

The temperature data was collected by different observation platforms using different methods. Here are the most used platforms and methods set appart. 

<strong>Platforms used</strong>
<br>
Each platform is numbered in the NOAA database from 0 to 21 with the following legend:

- 0 : US Navy or “deck” log, or unknown
- 1 : merchant ship or foreign military
- 2 : ocean station vessel—off station or station proximity unknown
- 3 : ocean station vessel—on station
- 4 : lightship
- 5 : ship
- 6 : moored buoy
- 7 : drifting buoy
- 8 : ice buoy (note: currently unused)
- 9 : ice station (manned, including ships overwintering in ice)
- 10 : oceanographic station data (bottle and low-resolution CTD/XCTD data)
- 11 : mechanical/digital/micro bathythermograph (MBT)
- 12 : expendable bathythermograph (XBT)
- 13 : Coastal-Marine Automated Network (C-MAN) (NDBC operated)
- 14 : other coastal/island station
- 15 : fixed (or mobile) ocean platform (plat, rig)
- 16 : tide gauge
- 17 : high-resolution Conductivity-Temp.-Depth (CTD)/Expendable CTD (XCTD) 74 
- 18 : profiling float
- 19 : undulating oceanographic recorder
- 20 : autonomous pinneped bathythermograph
- 21 : glider

With this information, we can examine which platforms were used for the collection of data for the sea surface temperature from the years 1950 to 2017. 

<img src="../6_img/chart_3.png" class="center">

<strong>Chart 3.</strong> Top 10 platforms used ordered by count and percentage.

<strong>Methods used</strong>
<br>

The methods used for data gathering are classified by NOAA as follows:

- 0 – bucket 
- 1 – condenser inlet (intake) 
- 2 – trailing thermistor 
- 3 – hull contact sensor 
- 4 – through hull sensor 
- 5 – radiation thermometer 
- 6 – bait tanks thermometer 
- 7 – others 
- 9 – unknown or non-bucket 
- 10 – “implied” bucket (note: applicable to early ICOADS data)
- 11 – reversing thermometer or mechanical sensor 
- 12 – electronic sensor

<img src="../6_img/chart_4.png" class="center">

<strong>Chart 4.</strong> The 10 top methods used. Most of the data had null values for the method column, so that is why the top value is marked as 'unknown'. NOAA has no explanation yet as to why most of this values are missing, but there had to be a method used or else there could've not been a reading in the temperature value.

<br>
#### Use a machine learning model to predict future changes in Central Pacific region
<br>

An important region of the Pacific Ocean, known as the 'Niño 3.4' region, shows how higher sea surface temperatures can affect the climate. Here we create a machine learning model to try to predict the sea surface temperature for the next couple of years after 2017, the last year in the dataset. According to the NASA Earth Observatory [website](https://earthobservatory.nasa.gov/features/ElNino), that region lies in a longitude between 120 West and 170 West. The latitude is between 20 North and 20 South.

Before modeling, it is important to check if there are any outliers.

<img src="../6_img/chart_5.png" class="center">

<strong>Chart 5.</strong> This chart counts the highest average readings in the Central pacific region for 812 months, starting from January of 1950 until August of 2017. There are no outliers in the data because all points lie between a reasonable range of 25 C° and 31 C°. This chart is also showing an upward trend in temperature readings. 


<br>
<strong>Predict the next 12 months given the last 48 months</strong>
<br>

Using a [Tensorflow](https://www.tensorflow.org/) machine learning model, we can try and make a prediction for the average temperature for the next 12 months after the last date in the dataset for the Niño 3.4 Pacific region. The last average value is from August 2017, so the model will predict the next 12 months starting in September 2017.


{% include sstemps.html %}

**Chart 7.** Prediction of the next 12 months after August 2017. Only 19 previous months are plotted of the 48 that were used to make the prediction. The year 2017 up until August shows a drop in temperatures compared to previous years. The prediction is indicating a rise of 0.2 C° in September 2017 and a highest temperature of 29.61 C° reached in March 2018. A drop of 0.1 C° is predicted for July 2018 as compared with July of 2017. The prediction also shows that temperatures would not rise to the levels of the year 2016 through most of 2018. 

To compare the prediction with reality, below is a visualization from NASA that shows the behavior of sea surface temperatures in the El Niño 3.4 region from 2009 up to 2018. For the 2018 part, we can see a similar line from the prediction, except in the July drop, which in reality did'nt happen.

<img src="../6_img/map_2.png" class="center">

Image: NASA [Scientific Visualization Studio](https://svs.gsfc.nasa.gov/4785)

References:

<br>
ICOADS:[https://icoads.noaa.gov/](https://icoads.noaa.gov/)
<br>
<br>
El Niño: [https://earthobservatory.nasa.gov/features/ElNino](https://earthobservatory.nasa.gov/features/ElNino)
<br>
<br>
Observational Needs of Sea Surface Temperature: [https://www.frontiersin.org/articles/10.3389/fmars.2019.00420/full](https://www.frontiersin.org/articles/10.3389/fmars.2019.00420/full)
<br>
<br>
Sea Surface Temperature anomalies and patterns of Global Disease Outbreaks: 2009-2018 (4K version): [https://svs.gsfc.nasa.gov/4785](https://svs.gsfc.nasa.gov/4785)
<br>




