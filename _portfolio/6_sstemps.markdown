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

<img src="../6_img/map_1.gif" class="center">

<strong><br>Map 1.</strong> Animation showing the change in the top average sea surface temperatures by location by year, from the years 1950 to 2017. As it is expected, the area along the equator has the highest average temperatures. Notice how the year 1950 has more lower temperatures and more locations on the top average temperatures than the year 2017. Each year has the top 200,000 readings averaged by location. With this in mind, the animation is showing an increase in sea surface temperature. The area in the Red Sea and the Persian Gulf stand out as the hotter places across all years.

#### Change of the highest averages per year and per location

For the range of 67 years for which the yearly sea surface temperature average was calculated, the following chart shows how the highest averages has changed.

<img src="../6_img/chart_1.png" class="center">

**Chart 1**. Each point is a map coordinate that had one of the 200'000 top temperature averages for each year. The highest average temperatures in 1950 are more spread and range almost from the low 20s to the mid 30s. As years increase, average temperatures increase and comprise a lower range ending in between the top 20s to the mid 30s. The lowest top averages (bottom points in each year) increase as well. This is why we see more blue colored areas in Map 1 for the year 1950 and a concentration of high temperatures in determined areas for the year 2017. 

The following visualization shows how temperature behaves as a function of location using longitude and latitude values:

<img src="../6_img/chart_2.png" class="center">

{% include sstemps.html %}


