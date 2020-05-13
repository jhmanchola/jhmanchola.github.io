# NOAA Sea Surface Temperature Data Analysis

The National Oceanographic and Atmospheric Association, NOAA, has dedicated scientists and advanced technology to provide reliable information about changes in climate, weather, oceans and coasts. Such information can be found online and it's available to the public. The NOAA dataset 'International Comprehensive Ocean-Atmosphere Data Set ICOADS' was used for this project. The dataset can be found in Google Cloud's [Marketplace](https://console.cloud.google.com/marketplace), and it has the following description:

> "The ICOADS dataset contains global marine data from ships (merchant, navy, research) and buoys, each capturing details according to the current weather or ocean conditions (wave height, sea temperature, wind speed, and so on). Each record contains the exact location of the observation which is great for visualizations. The historical depth of the data is quite comprehensive — there are records going back to 1662.
This public dataset is hosted in Google BigQuery and is included in BigQuery's 1TB/mo of free tier processing. This means that each user receives 1TB of free BigQuery processing every month, which can be used to run queries on this public dataset." 

Google BigQuery allows the database to be explored and manipulated using SQL queries. In this case, we want to explore the average sea surface temperature for the duration of 67 years, extending from the year 1950 to the year 2017. The main objective is to visualize the changes in sea surface temperature as a function of time.

Project Methods:

- Query the database using SQL to extract the data
- Export the results of the query into a readable Python format.
- Visualize important features in the data.
- Use machine learning methods to predict future sea surface temperatures.


```python
#Import the json file with the credentials to the GCP project
import os
os.environ['GOOGLE_APPLICATION_CREDENTIALS'] ='/Users/joman/Google Drive/DATA SCIENCE/PROJECTS/\
NOAA Ocean Data Analysis/GCP Project Credentials/NOAA ICOADS Analysis-cd3116e7e2c7.json'

import numpy as np
import pandas as pd #Useful if you need to view a table as a pandas dataframe
import pylab
import random
from sklearn.metrics import r2_score #Function for coefficient of determination R^2

from google.cloud import bigquery

client = bigquery.Client()

# Construct a reference to the "noaa_icoads" dataset
dataset_ref = client.dataset("noaa_icoads", project="bigquery-public-data")

# API request - fetch the dataset
dataset = client.get_dataset(dataset_ref)

#List the tables in the dataset
[table.table_id for table in list(client.list_tables(dataset))]
```




    ['icoads_core_1662_2000',
     'icoads_core_2001_2004',
     'icoads_core_2005',
     'icoads_core_2006',
     'icoads_core_2007',
     'icoads_core_2008',
     'icoads_core_2009',
     'icoads_core_2010',
     'icoads_core_2011',
     'icoads_core_2012',
     'icoads_core_2013',
     'icoads_core_2014',
     'icoads_core_2015',
     'icoads_core_2016',
     'icoads_core_2017']




```python
# Construct a reference to the "international_education" table
table_ref = dataset_ref.table("icoads_core_2017")

# API request - fetch the table
table = client.get_table(table_ref)

#View all columns of the table using .schema
table.schema
```




    [SchemaField('year', 'INTEGER', 'NULLABLE', 'Year of the actual time of observation at which the barometer is read. It is 4-digit', ()),
     SchemaField('month', 'INTEGER', 'NULLABLE', 'Month of the actual time of observation at which the barometer is read. (1=January, 2=February, …, 12=December)', ()),
     SchemaField('day', 'INTEGER', 'NULLABLE', 'Day of the actual time of observation at which the barometer is read. Days 1-31', ()),
     SchemaField('hour', 'FLOAT', 'NULLABLE', 'Hour of the actual time of observation at which the barometer is read. Hours 0.00 to 23.99', ()),
     SchemaField('latitude', 'FLOAT', 'NULLABLE', 'Position to hundredths of a degree +N or –S (measured north or south of the equator) and +E or −W (measured east or west of the Greenwich Meridian).', ()),
     SchemaField('longitude', 'FLOAT', 'NULLABLE', 'Position to hundredths of a degree +N or –S (measured north or south of the equator) and +E or −W (measured east or west of the Greenwich Meridian).', ()),
     SchemaField('imma_version', 'INTEGER', 'NULLABLE', 'IMMA Version: 0=2010, 1=2016', ()),
     SchemaField('attm_count', 'INTEGER', 'NULLABLE', 'The attm count: 0 – abbreviated record (no attm) 1 – one attm 2 – two attms etc.', ()),
     SchemaField('time_indicator', 'INTEGER', 'NULLABLE', 'Time indicator preserves the incoming precision of time fields: 0 – nearest whole hour 1 – hour to tenths 2 – hour plus minutes 3 – high resolution (e.g., hour to hundredths)', ()),
     SchemaField('latlong_indicator', 'INTEGER', 'NULLABLE', 'Latlong indicator preserves the precision at which LAT and LON were recorded or translated from, or if they were derived later by interpolation between known positions: 0 – degrees and tenths 1 – whole degrees 2 – mixed precision 3 – interpolated 4 – degrees and minutes 5 – high resolution data (e.g., degrees to seconds) 6 – other', ()),
     SchemaField('ship_course', 'INTEGER', 'NULLABLE', 'True direction of resultant displacement of the ship during the three hours preceding the time of observation (i.e., ship’s course (true) made good): 0 – stationary (ship hove to) 5 – SW 1 – NE 6 – W 2 – E 7 – NW 3 – SE 8 – N 4 – S 9 – unknown', ()),
     SchemaField('ship_speed', 'INTEGER', 'NULLABLE', 'Ship’s average speed made good during the three hours preceding the time of observation (beginning 1 January 1968): 0 – 0 knots  1 – 1-5 knots 2 – 6-10 knots 3 – 11-15 knots 4 – 16-20 knots  5 – 21-25 knots 6 – 26-30 knots 7 – 31-35 knots 8 – 36-40 knots 9 – over 40 knots.    Prior to 1 January 1968 a different code for VS, also with range 0-9, applied (Met Office 1948): 0 – 0 knots 1 – 1-3 knots 2 – 4-6 knots 3 – 7-9 knots 4 – 10-12 knots 5 – 13-15 knots  6 – 16-18 knots 7 – 19-21 knots 8 – 22-24 knots 9 – over 24 knots', ()),
     SchemaField('national_source_indicator', 'INTEGER', 'NULLABLE', 'A field available for national use in identifying data subsets.', ()),
     SchemaField('id_indicator', 'INTEGER', 'NULLABLE', 'ID Indicator indicates whether a callsign or some other sort of identification is contained in the ID field (and in R3.0 data, II should always be extant when ID information exists; whereas II should always be missing if ID is missing): 0 – ID present, but unknown type 1 – ship, Ocean Station Vessel (OSV), or ice station callsign 2 – generic ID (e.g., SHIP, BUOY, RIGG, PLAT) 3 – WMO 5-digit buoy number 4 – other buoy number (e.g., Argos or national buoy number) 5 – Coastal-Marine Automated Network (C-MAN) ID (assigned by US NDBC or other organizations) 6 – station name or number 7 – oceanographic platform/cruise number 8 – fishing vessel psuedo-ID 9 – national ship number 10 – composite information from early ship data 11 – 7-digit buoy ID (proposed)', ()),
     SchemaField('callsign', 'STRING', 'NULLABLE', 'Identification/Callsign', ()),
     SchemaField('country_code', 'STRING', 'NULLABLE', 'The country that recruited a ship, which may differ from the country of immediate receipt (C2, field 15) and may also differ from the ship’s registry', ()),
     SchemaField('wind_direction_indicator', 'INTEGER', 'NULLABLE', 'Gives the compass (and approximate precision) used for reporting the wind direction: 0 – 36-point compass 1 – 32-point compass 2 – 16 of 36-point compass 3 – 16 of 32-point compass 4 – 8-point compass 5 – 360-point compass 6 – high resolution data (e.g., tenths of degrees)', ()),
     SchemaField('wind_direction_true', 'INTEGER', 'NULLABLE', 'The direction (true) from which wind is blowing (or will blow), stored in whole degrees (i.e., 360-point compass; range: 1-360°), or special codes: 361 – calm 362 – variable, or all directions', ()),
     SchemaField('wind_speed_indicator', 'INTEGER', 'NULLABLE', 'Wind speed is stored in tenths of a meter per second (to retain adequate precision for winds converted from knots, or high-resolution data). WI shows the units in which and/or the method by which W was originally recorded (0, 1, 3, 4 follow WMO Code 1855): 0 – meter per second, estimated 53 1 – meter per second, obtained from anemometer (measured) 2 – estimated (original units unknown) 3 – knot, estimated 4 – knot, obtained from anemometer (measured) 5 – Beaufort force (based on documentation) 6 – estimated (original units unknown)/unknown method 7 – measured (original units unknown) 8 – high-resolution measurement (e.g., hundredths of a meter per second)', ()),
     SchemaField('wind_speed', 'FLOAT', 'NULLABLE', 'Wind speed which is stored in tenths of a meter per second (to retain adequate precision for winds converted from knots, or high-resolution data)', ()),
     SchemaField('visibility_indicator', 'INTEGER', 'NULLABLE', 'shows whether visibility was: 0 – estimated (or unknown method of observation) 1 – measured 2 – fog present (obsolete)', ()),
     SchemaField('visibility', 'INTEGER', 'NULLABLE', 'Visibility (horizontal visibility at the surface in kilometers) according to WMO Code 4377 from which, in reporting visibility at sea, WMO (2009a; Reg. 12.2.1.3.2) states that the decile 90-99 shall be used (moreover Reg. 12.2.1.3.1: when the horizontal visibility is not the same in different directions, the shortest distance shall be given for VV): 90 – less than 0.05 kilometer 91 – 0.05 92 – 0.2 93 – 0.5 94 – 1 95 – 2 96 – 4 97 – 10 98 – 20 99 – 50 or more', ()),
     SchemaField('present_weather', 'INTEGER', 'NULLABLE', 'WMO Codes 4677 (Table D3) for WW, and 4561 for W1: 0 – Cloud covering 1/2 or less of the sky throughout the appropriate period 1 – Cloud covering more than 1/2 of the sky during part of the appropriate period and covering 1/2 or less during part of the period 2 – Cloud covering more than 1/2 of the sky throughout the appropriate period 54 3 – Sandstorm, duststorm or blowing snow 4 – Fog or ice fog or thick haze 5 – Drizzle 6 – Rain 7 – Snow, or rain and snow mixed 8 – Shower(s) 9 – Thunderstorm(s) with or without precipitation', ()),
     SchemaField('past_weather', 'INTEGER', 'NULLABLE', 'WMO Codes 4677 (Table D3) for WW, and 4561 for W1: 0 – Cloud covering 1/2 or less of the sky throughout the appropriate period 1 – Cloud covering more than 1/2 of the sky during part of the appropriate period and covering 1/2 or less during part of the period 2 – Cloud covering more than 1/2 of the sky throughout the appropriate period 54 3 – Sandstorm, duststorm or blowing snow 4 – Fog or ice fog or thick haze 5 – Drizzle 6 – Rain 7 – Snow, or rain and snow mixed 8 – Shower(s) 9 – Thunderstorm(s) with or without precipitation', ()),
     SchemaField('sea_level_pressure', 'FLOAT', 'NULLABLE', 'Amount of pressure tendency at station level during the three hours preceding the time of observation in tenths of hPa (i.e., millibars)', ()),
     SchemaField('characteristic_of_ppp', 'INTEGER', 'NULLABLE', 'WMO Code 0200 for characteristic of pressure tendency during the three hours preceding the time of observation (A) (after WMO 2015).', ()),
     SchemaField('amt_pressure_tend', 'FLOAT', 'NULLABLE', 'Amount of pressure tendency at station level during the three hours preceding the time of observation in tenths of hPa (i.e., millibars)', ()),
     SchemaField('indicator_for_temp', 'INTEGER', 'NULLABLE', 'Indicator provides information about the precision and/or units that the Core temperature elements were translated from: 0 – tenths °C 1 – half °C 2 – whole °C 3 – whole or tenths °C (mixed precision among temperature fields) 4 – tenths °F 5 – half °F 6 – whole °F 7 – whole or tenths °F (mixed precision among temperature fields) 8 – high resolution data (e.g., hundredths °C) 9 – other', ()),
     SchemaField('air_temperature', 'FLOAT', 'NULLABLE', 'Air temperature, Celsius', ()),
     SchemaField('wbt_indicator', 'INTEGER', 'NULLABLE', 'WBTI and DPTI indicate which of WBT or DPT was measured or computed, and ice bulb conditions: 0 – measured 1 – computed 2 – iced measured 3 – iced computed', ()),
     SchemaField('wetbulb_temperature', 'FLOAT', 'NULLABLE', 'Wet-bulb temperature, Celsius', ()),
     SchemaField('dpt_indicator', 'INTEGER', 'NULLABLE', 'WBTI and DPTI indicate which of WBT or DPT was measured or computed, and ice bulb conditions: 0 – measured 1 – computed 2 – iced measured 3 – iced computed', ()),
     SchemaField('dewpoint_temperature', 'FLOAT', 'NULLABLE', 'Dew-point temperature, Celsius', ()),
     SchemaField('sst_measurement_method', 'INTEGER', 'NULLABLE', 'Shows the method by which SST was taken: 0 – bucket 1 – condenser inlet (intake) 2 – trailing thermistor 3 – hull contact sensor 4 – through hull sensor 5 – radiation thermometer 6 – bait tanks thermometer 7 – others 9 – unknown or non-bucket 10 – “implied” bucket [note: applicable to early ICOADS data] 11 – reversing thermometer or mechanical sensor 12 – electronic sensor', ()),
     SchemaField('sea_surface_temp', 'FLOAT', 'NULLABLE', 'Temperatures are stored in tenths of a degree Celsius.', ()),
     SchemaField('total_cloud_amount', 'INTEGER', 'NULLABLE', 'Codes 0 to 9 (WMO Code 2700) show the total fraction of the celestial dome covered by clouds (irrespective of their genus). 0 – clear 1 – 1 okta or less, but not zero 2-6 – 2-6 oktas 7 – 7 oktas or more, but not 8 oktas 8 – 8 oktas 9 – sky obscured by fog and/or other meteorological phenomena', ()),
     SchemaField('lower_cloud_amount', 'INTEGER', 'NULLABLE', '0 – clear 1 – 1 okta or less, but not zero 2-6 – 2-6 oktas 7 – 7 oktas or more, but not 8 oktas 8 – 8 oktas 9 – sky obscured by fog and/or other meteorological phenomena', ()),
     SchemaField('low_cloud_type', 'STRING', 'NULLABLE', 'Codes 0 to 10 [A in base36 encoding] show characteristics observed of clouds of the genera Stratocumulus, Stratus, Cumulus, and Cumulonimbus (WMO Code 0513', ()),
     SchemaField('cloud_height_indicator', 'INTEGER', 'NULLABLE', 'Shows if cloud height H was: 0 – estimated 1 – measured', ()),
     SchemaField('cloud_height', 'STRING', 'NULLABLE', 'Codes 0 to 9 and “A” (following WMO Code 1600) show the height above surface of the base of the lowest cloud seen (such that a height exactly equal to one of the values at  60 the ends of the ranges shall be coded in the higher range, e.g., a height of 600 m shall be reported by code 5): 0 – 0 to 50 m 1 – 50 to 100 m 2 – 100 to 200 m 3 – 200 to 300 m 4 – 300 to 600 m 5 – 600 to 1000 m 6 – 1000 to 1500 m 7 – 1500 to 2000 m 8 – 2000 to 2500 m 9 – 2500 m or more, or no clouds 10 [A in base36 encoding] – height of base of cloud not known or base of clouds at a level lower and tops at a level higher than that of the station', ()),
     SchemaField('middle_cloud_type', 'STRING', 'NULLABLE', 'Codes 0 to 10 [A in base36 encoding] show characteristics observed of clouds of the genera Altocumulus, Altostratus, and Nimbostratus (WMO Code 0515).', ()),
     SchemaField('high_cloud_type', 'STRING', 'NULLABLE', 'Codes 0 to 10 [A in base36 encoding] show characteristics observed of clouds of the genera Cirrus, Cirrocumulus and Cirrostratus (WMO Code 0509).', ()),
     SchemaField('wave_direction', 'INTEGER', 'NULLABLE', 'Starting in 1968, WD was no longer reported in the SHIP code. Codes 00 to 36 (note: leading zero is omitted in IMMA) show the direction (if any) from which (wind) waves come, in tens of degrees (following WMO Code 0877; ref. Code and Range columns in Table D2). Codes 37 and 38 show: 37 – waves confused, direction indeterminate (WH ≤ 4.75 m) 38 – waves confused, direction indeterminate (WH > 4.75 m; or irrespective of wave height, corresponding to 99 in WMO Code 0877)', ()),
     SchemaField('wave_period', 'INTEGER', 'NULLABLE', 'Period of wind waves, in seconds. Starting in 1968, WP was reported in seconds; prior to 1968 the period was reported as a code, which was converted into whole seconds following Table D5a, with WX (C1, field 13) set accordingly.', ()),
     SchemaField('wave_height', 'FLOAT', 'NULLABLE', 'Height of wind waves, in metres.', ()),
     SchemaField('swell_direction', 'INTEGER', 'NULLABLE', 'Starting in 1968, SD was no longer reported in the SHIP code. Codes 00 to 36 (note: leading zero is omitted in IMMA) show the direction (if any) from which (wind) waves come, in tens of degrees (following WMO Code 0877; ref. Code and Range columns in Table D2). Codes 37 and 38 show: 37 – waves confused, direction indeterminate (SH ≤ 4.75 m) 38 – waves confused, direction indeterminate (SH > 4.75 m; or irrespective of wave height, corresponding to 99 in WMO Code 0877)', ()),
     SchemaField('swell_period', 'INTEGER', 'NULLABLE', 'Period of wind waves, in seconds. Starting in 1968, SP was reported in seconds; prior to 1968 the period was reported as a code, which was converted into whole seconds following Table D5a, with WX (C1, field 13) set accordingly.', ()),
     SchemaField('swell_height', 'FLOAT', 'NULLABLE', 'Height of wind waves, in metres.', ()),
     SchemaField('box_system_indicator', 'STRING', 'NULLABLE', 'The box system indicator is currently unused.', ()),
     SchemaField('ten_degree_box_number', 'INTEGER', 'NULLABLE', '10° box numbers (see Release 1, supp. G; http://icoads.noaa.gov/Release_1/suppG.html) are available e.g., for use in sorting operations', ()),
     SchemaField('one_degree_box_number', 'INTEGER', 'NULLABLE', '1° box numbers (see Release 1, supp. G; http://icoads.noaa.gov/Release_1/suppG.html) are available e.g., for use in sorting operations', ()),
     SchemaField('deck', 'INTEGER', 'NULLABLE', 'Number of the deck from which the report came (Table D6a), with Tables D6b and D6c providing additional information about selected DCK ranges. “Deck” originally referred to a punched card deck, but is now used as the primary field to track ICOADS data collections.', ()),
     SchemaField('source_id', 'INTEGER', 'NULLABLE', 'Number of the source ID from which the report came (Table D7). Each SID may contain a single deck or a mixture of decks, but each SID is generally constrained to a single input format.', ()),
     SchemaField('platform_type', 'INTEGER', 'NULLABLE', 'The type of observing platform: 0 – US Navy or “deck” log, or unknown 1 – merchant ship or foreign military 2 – ocean station vessel—off station or station proximity unknown 3 – ocean station vessel—on station 4 – lightship 5 – ship 6 – moored buoy 7 – drifting buoy 8 – ice buoy [note: currently unused] 9 – ice station (manned, including ships overwintering in ice) 10 – oceanographic station data (bottle and low-resolution CTD/XCTD data) 11 – mechanical/digital/micro bathythermograph (MBT) 12 – expendable bathythermograph (XBT) 13 – Coastal-Marine Automated Network (C-MAN) (NDBC operated) 14 – other coastal/island station 15 – fixed (or mobile) ocean platform (plat, rig) 16 – tide gauge 17 – high-resolution Conductivity-Temp.-Depth (CTD)/Expendable CTD (XCTD) 74 18 – profiling float 19 – undulating oceanographic recorder 20 – autonomous pinneped bathythermograph 21 – glider', ()),
     SchemaField('dup_status', 'INTEGER', 'NULLABLE', 'Indicates duplicate status. 0 unique 1 best duplicate 2 best duplicate with substitution', ()),
     SchemaField('dup_check', 'INTEGER', 'NULLABLE', 'The presence of a duplicate match between a Global Telecommunication System (GTS) and logbook (or other delayed-mode) report may provide some location verification, with greater credibility if SLP and SST match under “allowances.” DUPC indicates whether such matches were detected during duplicate elimination processing (either the GTS or delayed-mode report is retained in the output data mixture), in case users might wish to make use of this information for independent quality control purposes: 0 – GTS and logbook match with SLP and SST match 1 – GTS and logbook match without SLP and SST match 2 – no GTS and logbook match was encountered', ()),
     SchemaField('track_check', 'INTEGER', 'NULLABLE', 'Indicates if a report was: 0 – not track checked 1 – track checked', ()),
     SchemaField('pressure_bias', 'INTEGER', 'NULLABLE', 'Indicates questionable sea level pressure data: 0 – questionable SLP: level 0: individual platform (unused) 1 – questionable SLP: level 1: deck 2 – questionable SLP: level 2: deck', ()),
     SchemaField('wave_period_indicator', 'INTEGER', 'NULLABLE', 'Indicates that the wave and swell periods were converted from code into whole seconds: 1 – period converted from code into whole seconds', ()),
     SchemaField('swell_period_indicator', 'INTEGER', 'NULLABLE', 'Indicates that the wave and swell periods were converted from code into whole seconds: 1 – period converted from code into whole seconds', ()),
     SchemaField('second_country_code', 'INTEGER', 'NULLABLE', 'The country of immediate receipt (C2), which may differ from the recruiting country (C1) and may also differ from the ship’s registry.', ()),
     SchemaField('adaptive_qc_flags', 'STRING', 'NULLABLE', 'SQZ indicates the relationship of SST to “adaptive” QC limits in 0.5σ (standard deviation) increments, and SQZ provides a measure of the reliability of the QC', ()),
     SchemaField('nightday_flag', 'INTEGER', 'NULLABLE', 'The night/day report flag was set to indicate whether the report fell in local nighttime or daytime, as determined according to Slutz et al. 1 = report time is local nighttime 2 = report time is local daytime', ()),
     SchemaField('trimming_flags', 'STRING', 'NULLABLE', 'These flags indicate the relationship of a given observational data value to the legacy trimming limits, or to indicate if those limits, which were calculated separately for three historical periods are unavailable, or other conditions.', ()),
     SchemaField('ncdc_qc_flags', 'STRING', 'NULLABLE', 'Possible NCDC-QC flag values, where “–” indicates an undefined flag value, or letters included in the table indicate a defined flag value. For the letters, lower-case “x” indicates a flag value not utilized, whereas upper-case flag values were utilized, in preparing enhanced or standard trimmed data', ()),
     SchemaField('external', 'INTEGER', 'NULLABLE', 'The single extant value of the external flags is defined as 1 = erroneous (based on external OSD buoy quality control) They range from 0-63', ()),
     SchemaField('landlocked_flag', 'INTEGER', 'NULLABLE', 'The single extant value of the landlocked flag (LZ) is defined as 1 = report over land If LZ is missing, this indicates that the report falls over an ocean or coastal region as defined by a “landlocked” file at 2°×2° resolution', ()),
     SchemaField('source_exclusion_flags', 'INTEGER', 'NULLABLE', 'The single extant value of the source exclusion flags is defined as 1 = data automatically disqualified from statistics They range from 0-31', ()),
     SchemaField('unique_report_id', 'STRING', 'NULLABLE', 'A unique ID for each record in ICOADS represented as a base36 number of length 6.', ()),
     SchemaField('release_no_primary', 'INTEGER', 'NULLABLE', 'First of the three elements that make up the full release number associated with the record. For example, Release 3.0.1 is represented with RN1=3, RN2=0, and RN3=1', ()),
     SchemaField('release_no_secondary', 'INTEGER', 'NULLABLE', 'Second of the three elements that make up the full release number associated with the record. For example, Release 3.0.1 is represented with RN1=3, RN2=0, and RN3=1', ()),
     SchemaField('release_no_tertiary', 'INTEGER', 'NULLABLE', 'Third of the three elements that make up the full release number associated with the record. For example, Release 3.0.1 is represented with RN1=3, RN2=0, and RN3=1', ()),
     SchemaField('release_status_indicator', 'INTEGER', 'NULLABLE', 'An indicator that specifies whether the record is: 0 – Preliminary (Not yet included in an official ICOADS Release) 1 – Auxiliary (Records provided in separate data files in addition to ICOADS official Releases and Preliminary data. This also includes new data sources received, but awaiting blending into an official ICOADS Release) 2 – Full (A record included in an official ICOADS Release)', ()),
     SchemaField('intermediate_reject_flag', 'INTEGER', 'NULLABLE', '0=Retain in Intermediate, Reject from Final dataset;  1=Retain in both Intermediate and Final datasets;  2=Reject from both Intermediate and Final datasets', ()),
     SchemaField('timestamp', 'TIMESTAMP', 'NULLABLE', 'Converted UTC timestamp for the actual time of observation at which the barometer is read', ())]




```python
# Check teh number of rows
print("Number of rows in table'",table.table_id,"' is",f'{table.num_rows :,}'+'.') # use f{number:,} to give k format
```

    Number of rows in table' icoads_core_2017 ' is 31,036,992.
    


```python
# Check number of columns
print("Number of columns in table '",table.table_id,"' is",str(len(table.schema))+'.')
```

    Number of columns in table ' icoads_core_2017 ' is 75.
    


```python
#To load the magic commands from the client library, run the following code
%load_ext google.cloud.bigquery
```


```python
%%bigquery temps_df 
#save result in a pandas dataframe named temps_df

WITH top_temps_pre AS (   
    SELECT year, month, latitude, longitude, AVG(sea_surface_temp) AS sstemp, 
       ROW_NUMBER() OVER (PARTITION BY year ORDER BY AVG(sea_surface_temp) DESC) AS temp_rank
    FROM `bigquery-public-data.noaa_icoads.icoads_core_*`  # Use wildcard * to explore all tables
    WHERE (sea_surface_temp IS NOT NULL) AND (year BETWEEN 1950 AND 2018)
    GROUP BY year, month, longitude, latitude
)


SELECT year, month, latitude, longitude, sstemp, temp_rank
FROM top_temps_pre
WHERE temp_rank <= 200000
ORDER BY sstemp

     
#Rank query
    
# WITH top_temps_pre AS (   
#     SELECT year, latitude, longitude, sea_surface_temp, 
#        RANK() OVER (PARTITION BY year ORDER BY sea_surface_temp DESC) AS temp_rank
#     FROM `bigquery-public-data.noaa_icoads.icoads_core_*` 
#     WHERE (sea_surface_temp IS NOT NULL) AND (year BETWEEN 1950 AND 2018)
#     ORDER BY sea_surface_temp DESC
# )
```


```python
import matplotlib.pyplot as plt
from matplotlib import cm
from matplotlib.colors import ListedColormap, LinearSegmentedColormap
from IPython.display import HTML # import in case you want to display in the jupyter notebook
from matplotlib.animation import FuncAnimation, PillowWriter

# The key 'PROJ_LIB' needs to be imported so Basemap can be imported
import os
os.environ['PROJ_LIB'] = r'C:\Users\joman\Anaconda3\pkgs\proj4-5.2.0-h6538335_1006\Library\share'

from mpl_toolkits.basemap import Basemap
from numpy import max

# Group by year, discard the 'month' column
temps_year = temps_df[['year', 'latitude', 'longitude', 'sstemp']].groupby(['year','longitude',
                                                                            'latitude']).mean()
# Remove the multilevel index by resetting the index                                                                            'longitude', 'latitude']).mean()
temps_year = temps_year.reset_index(level=[0,1,2])


def update(year):
    '''Function to pass to the matplotlib FuncAnimation() function. Each frame of the animation
    will be a different year, so this function will 'update' each frame according to the year.
    Make sure that the list of frames passed to the FuncAnimation is a list of the years.'''
    
    fig.clf()
    
    m = Basemap(llcrnrlat=-80,urcrnrlat=80,llcrnrlon=-180,urcrnrlon=180,
                lat_ts=20, resolution='c', projection='mill', lat_0 = 0, lon_0 = 0)
    m.drawcoastlines(color='#111111')
    m.fillcontinents(color='#111111')
    
    lat  = np.array(temps_year[temps_year['year']==year]['latitude'])
    lon  = np.array(temps_year[temps_year['year']==year]['longitude'])
    temp = np.array(temps_year[temps_year['year']==year]['sstemp'])
    
    x,y = m(lon,lat)
    
    m.hexbin(x, y,C= np.array(temp), reduce_C_function = max, gridsize=100,vmin=5,vmax=39,
             cmap='jet', linewidths=0.1, edgecolors='k'), 
    m.colorbar(location='right').set_label('C°',fontsize=14,rotation='horizontal',position=(0,1),labelpad=15)

    text_x, text_y = m(77, -77)

    plt.text(text_x,text_y, '%d'%year,fontsize=29,fontweight='bold',ha='left',va='bottom',color='white')
    plt.text(text_x-3200000,text_y, 'year',fontsize=19,fontweight='bold',ha='left',va='bottom',color='white')

```

__Map 1.__ Animation showing the change in the top average sea surface temperatures by location by year, from the years 1950 to 2017. As it is expected, the area along the equator has the highest average temperatures. Notice how the year 1950 has more lower temperatures and more locations on the top average temperatures than the year 2017. Each year has the top 200,000 readings averaged by location. With this in mind, the animation is showing an increase in sea surface temperature. The area in the Red Sea and the Persian Gulf stand out as the hotter places across all years.


```python
# fig = plt.figure(figsize=(12, 6.4))
# fig.subplots_adjust(left=0.01, bottom=0, right=0.95, top=1, wspace=None, hspace=None)

# frames = temps_year['year'].value_counts().index.sort_values() #List of frames are integers (the years 1950 - 2017)

# # Call the FuncAnimation() function to create the animation. Use PillowWriter writer to create the .gif file
# ani = FuncAnimation(fig, update, frames=frames,interval=600)
# ani.save('fig.gif', writer=PillowWriter(fps=1))
# plt.close()
```

### Change of the highest averages per year and per location

For the range of 67 years for which the yearly sea surface temperature average was calculated, the following chart shows how the highest averages has changed.


```python
import seaborn as sns
%matplotlib inline

sns.set(style="white", palette="muted", color_codes=True)

sns.relplot(x="year", y="sstemp", color='red', alpha=0.3, data=temps_year,height=6)
sns.despine(left=True)
plt.title('Chart 1. Relation of Sea Surface Temperature and Year',fontsize=14)
plt.show()
```


![png](output_11_0.png)


**Chart 1**. Each point is a map coordinate that had one of the 200'000 top temperature averages for each year. The highest average temperatures in 1950 are more spread and range almost from the low 20s to the mid 30s. As years increase, average temperatures increase and comprise a lower range ending in between the top 20s to the mid 30s. The lowest top averages (bottom points in each year) increase as well. This is why we see more blue colored areas in Map 1 for the year 1950 and a concentration of high temperatures in determined areas for the year 2017. 


```python
fig, axs = plt.subplots(1,2,figsize=(13, 6), sharey=True)
sns.relplot(x="longitude", y="sstemp", data=temps_year, color='orange', alpha=0.3, ax=axs[0])
sns.despine(left=True, ax=axs[0])
sns.relplot(x="latitude", y="sstemp", data=temps_year, color='orange', alpha=0.3, ax=axs[1])
sns.despine(left=True, ax=axs[1])
fig.suptitle('Chart 2. Relation of Sea Surface Temperature with Lon. and Lat.')
plt.close(2)
plt.close(3)
plt.show()
```


![png](output_13_0.png)


**Chart 2.** By changing the longitude there isn't much change for each temperature point. Longitudes, the imaginary lines moving East to West around Earth don't vary a lot. Latitudes (lines going North to South), on the other hand, show different temperatures according to the value. Latitudes on the equator have higher temperatures than those in the Northern and Southern Hemispheres. 

## Methods of data collection for sea surface temperature

The temperature data was collected by different observation platforms using different methods. As an informative addition, here are the most used platforms and methods set appart. 

### Platforms used
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


```python
%%bigquery sources_df
#save result in a pandas dataframe named sources_df
     
WITH sources AS (   
    SELECT year, latitude, longitude, sea_surface_temp, platform_type, sst_measurement_method
    FROM `bigquery-public-data.noaa_icoads.icoads_core_*` 
    WHERE (sea_surface_temp IS NOT NULL) AND (year BETWEEN 1950 AND 2018) AND (platform_type IS NOT NULL)
),

sources_summary AS (
    SELECT year, latitude, longitude, AVG(sea_surface_temp) AS sstemp, platform_type, sst_measurement_method
    FROM sources
    GROUP BY year, longitude, latitude, platform_type, sst_measurement_method
    ORDER BY sstemp DESC
)
    
SELECT CAST(platform_type AS STRING) AS code_name, COUNT(*) AS count, 'platform type' AS column_name
FROM sources_summary
GROUP BY platform_type

UNION ALL

SELECT CAST(sst_measurement_method AS STRING) AS code_name, COUNT(*) AS count, 'method' AS column_name
FROM sources_summary
GROUP BY sst_measurement_method
```


```python
# Plot the data

# Filter only the platforms from the sources_df dataframe, then sort the count.
platforms_count = sources_df[sources_df['column_name']== 'platform type'].sort_values('count',ascending=False) 

# Organize all platform names with their NOAA number in a dictionary
platform_types = {0 : 'US Navy or deck log, or unknown',
    1 : 'merchant ship or foreign military', 
    2 : 'ocean station vessel—off station or station proximity unknown',   
    3 : 'ocean station vessel—on station', 
    4 : 'lightship', 
    5 : 'ship', 
    6 : 'moored buoy', 
    7 : 'drifting buoy', 
    8 : 'ice buoy (note: currently unused)', 
    9 : 'ice station (manned, including ships overwintering in ice)', 
    10 : 'oceanographic station data (bottle and low,resolution CTD/XCTD data)', 
    11 : 'mechanical/digital/micro bathythermograph (MBT)', 
    12 : 'expendable bathythermograph (XBT)', 
    13 : 'Coastal,Marine Automated Network (C,MAN) (NDBC operated)', 
    14 : 'other coastal/island station', 
    15 : 'fixed (or mobile) ocean platform (plat, rig)', 
    16 : 'tide gauge', 
    17 : 'high,resolution Conductivity,Temp.,Depth (CTD)/Expendable CTD (XCTD) 74' , 
    18 : 'profiling float', 
    19 : 'undulating oceanographic recorder', 
    20 : 'autonomous pinneped bathythermograph', 
    21 : 'glider'}

def name_platform(n):
    for p in platform_types:
        if n == str(p):
            return platform_types[p]
    else:
        return 'None'

def percentage(c):
    per = (c/platforms_count['count'].sum())*100
    return per
    

# Apply functions
platforms_count['platform_name'] = platforms_count['code_name'].apply(name_platform)
platforms_count['%'] = platforms_count['count'].apply(percentage)


plt.figure(figsize=(6,8))
platforms_chart = sns.barplot(x="count",
                         y="platform_name",
                         palette='Blues_d',
                         data=platforms_count[:10], dodge=False
                         )

plt.title('Chart 3. Platforms Used for Sea Surface Temperature Observations (count & percentage)\nFrom 1950 to 2017',
          y=1.05, fontsize=14)
# nyc_chart.get_legend().set_visible(False) #In case plot needs legend, this would hide the legend

# Loop to add text to each bar
for index, row in platforms_count[:10].reset_index(drop=True).iterrows():
    label = row['count']
    per = f"  ({row['%']:.2f}%)"
    platforms_chart.text(row['count']+13000000, index, f"{label:,}"+per, color='black', ha="center")

sns.despine(left=True, bottom=True)
```


![png](output_17_0.png)


### Methods used

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
- 10 – “implied” bucket [note: applicable to early ICOADS data] 
- 11 – reversing thermometer or mechanical sensor 
- 12 – electronic sensor


```python
methods_count = sources_df[sources_df['column_name']=='method'].sort_values('count',ascending=False)

methods_key = { 0 : 'bucket', 
     1 : 'condenser inlet (intake)', 
     2 : 'trailing thermistor',
     3 : 'hull contact sensor', 
     4 : 'through hull sensor', 
     5 : 'radiation thermometer', 
     6 : 'bait tanks thermometer', 
     7 : 'others', 
     9 : 'unknown or nonbucket', 
     10 : '“implied” bucket [note: applicable to early ICOADS data]', 
     11 : 'reversing thermometer or mechanical sensor', 
     12 : 'electronic sensor'}

def get_method(x):
    for m in methods_key:
        if x == str(m):
            return methods_key[m]
    else:
        return 'unknown'
    
def percentage(c):
    per = (c/methods_count['count'].sum())*100
    return per
    
methods_count['method_name'] = methods_count['code_name'].apply(get_method)
methods_count['%'] = methods_count['count'].apply(percentage)

plt.figure(figsize=(6,8))
methods_chart = sns.barplot(x="count",
                         y="method_name",
                         palette='YlOrRd_r',
                         data=methods_count[:10], dodge=False
                         )

# Loop to add text to each bar
for index, row in methods_count[:10].reset_index(drop=True).iterrows():
    label = row['count']
    per = f"  ({row['%']:.2f}%)"
    methods_chart.text(row['count']+16000000, index, f"{label:,}"+per, color='black', ha="center")

plt.title('Chart 4. Methods of Observation of Sea Surface Temperature (count & percentage)\nFrom 1950 to 2017',
          y=1.05, fontsize=14)
sns.despine(left=True, bottom=True)
```


![png](output_19_0.png)


**Chart 4.** The 10 top methods used. Most of the data had null values for the method column, so that is why the top value is marked as 'unknown'. NOAA has no explanation yet as to why most of this values are missing, but there had to be a method used or else there could've not been a reading in the temperature value.

## Create a linear regression model to predict future changes

Sea surface temperature (SST) is a fundamental physical variable for understanding, quantifying and predicting complex interactions between the ocean and the atmosphere. Such processes determine how heat from the sun is redistributed across the global oceans, directly impacting large- and small-scale weather and climate patterns.

An important region of the Pacific Ocean, known as the 'Niño 3.4' region, shows how higher sea surface temperatures can affect the climate. Here we create a machine learning model to try to predict the sea surface temperature for the next couple of years after 2017, the last year in the dataset. According to the NASA Earth Observatory [website](https://earthobservatory.nasa.gov/features/ElNino), that region lies in a longitude between 120 West and 170 West. The latitude is between 20 North and 20 South.

Through a long short-term memory recurrent (LSTM) neural network for multi-step time series forecasting.....

###  Time Series Linear Regression model


```python
client = bigquery.Client(project='noaa-icoads-analysis', location="US")
dataset = client.create_dataset('bqml_icoads', exists_ok=True)
```

### Train model with data from 2010 to 2016


```python
%%bigquery

CREATE MODEL IF NOT EXISTS `bqml_icoads.linreg_model`
OPTIONS(model_type='LINEAR_REG') AS 

WITH top_temps_pacific AS (   
    SELECT year, month, latitude, longitude, AVG(sea_surface_temp) AS label, 
       ROW_NUMBER() OVER (PARTITION BY year ORDER BY AVG(sea_surface_temp) DESC) AS temp_rank
    FROM `bigquery-public-data.noaa_icoads.icoads_core_201*`  # Use wildcard * to explore all tables
    WHERE (sea_surface_temp IS NOT NULL) AND (year BETWEEN 2009 AND 2016) AND 
          (latitude BETWEEN -19 AND 19) AND (longitude BETWEEN -119 AND -169)
                                                                             
    GROUP BY year, month, longitude, latitude
)


SELECT year, label
FROM top_temps_pacific
WHERE temp_rank <= 200000
```

    Executing query with job ID: ab58b1e3-fb78-40f7-ba8e-57d945af632a
    Query executing: 2.33s

    
    ERROR:
     403 GET https://bigquery.googleapis.com/bigquery/v2/projects/noaa-icoads-analysis/queries/ab58b1e3-fb78-40f7-ba8e-57d945af632a?maxResults=0&timeoutMs=400&location=US: Quota exceeded: Your project exceeded quota for free create model query bytes scanned. For more information, see https://cloud.google.com/bigquery/troubleshooting-errors
    
    (job ID: ab58b1e3-fb78-40f7-ba8e-57d945af632a)
    
                                         -----Query Job SQL Follows-----                                     
    
        |    .    |    .    |    .    |    .    |    .    |    .    |    .    |    .    |    .    |    .    |
       1:CREATE MODEL IF NOT EXISTS `bqml_icoads.linreg_model`
       2:OPTIONS(model_type='LINEAR_REG') AS 
       3:
       4:WITH top_temps_pacific AS (   
       5:    SELECT year, month, latitude, longitude, AVG(sea_surface_temp) AS label, 
       6:       ROW_NUMBER() OVER (PARTITION BY year ORDER BY AVG(sea_surface_temp) DESC) AS temp_rank
       7:    FROM `bigquery-public-data.noaa_icoads.icoads_core_201*`  # Use wildcard * to explore all tables
       8:    WHERE (sea_surface_temp IS NOT NULL) AND (year BETWEEN 2009 AND 2016) AND 
       9:    (latitude BETWEEN -19 AND 19) AND (longitude BETWEEN -119 AND -169)
      10:                                                                             
      11:    GROUP BY year, month, longitude, latitude
      12:)
      13:
      14:
      15:SELECT year, label
      16:FROM top_temps_pacific
      17:WHERE temp_rank <= 200000
        |    .    |    .    |    .    |    .    |    .    |    .    |    .    |    .    |    .    |    .    |
    

### Evaluate model with data from 2017


```python
%%bigquery

SELECT
  *
FROM ML.EVALUATE(MODEL `bqml_icoads.linreg_model`, (
    WITH top_temps_pre AS (   
        SELECT year, latitude, longitude, AVG(sea_surface_temp) AS label, 
           ROW_NUMBER() OVER (PARTITION BY year ORDER BY AVG(sea_surface_temp) DESC) AS temp_rank
        FROM `bigquery-public-data.noaa_icoads.icoads_core_2017` 
        WHERE (sea_surface_temp IS NOT NULL) AND (latitude BETWEEN -19 AND 19) AND 
              (longitude BETWEEN -119 AND -169)
                                                                             
    GROUP BY year, month, longitude, latitude
)
    
SELECT year, label
FROM top_temps_pacific
WHERE temp_rank <= 200000
```


```python
#Create dataset with avg monthly temperatures in the Pacific Ocean equator (120W - 170W)

pacific_temps_df = temps_df[(temps_df['longitude']<-120) & (temps_df['longitude']>-170) 
                            & (temps_df['latitude']>-20) & (temps_df['latitude']<20)]


#Create final univariate dataset with month temp average
TRAIN_SPLIT = 51
model_df = pacific_temps_df[['year','month','sstemp']].groupby(['year','month']).mean()
model_df = model_df['sstemp'].values

#Standarize all data using the training mean and std
# model_train_mean = model_df[:TRAIN_SPLIT].mean()
# model_train_std = model_df[:TRAIN_SPLIT].std()

# model_df = (model_df-model_train_mean)/model_train_std
```

### Check for any outliers in the data before trying a model


```python
plt.scatter(range(len(model_df)),model_df)
plt.title('Chart 5. Monthly Temperature for 812 months')
plt.ylabel('temperature C')
plt.show()
```


![png](output_31_0.png)


**Chart 5.** This chart counts the highest readings in the Central pacific region for 812 months, starting from January of 1950 until August of 2017. There are no outliers in the data because all points lie between a reasonable range of 25 C° and 31 C°. This chart is also showing an upward trend in temperature readings. 


```python
#Create a training and testing set
train_seq = model_df[:752]
test_seq = model_df[752:]

#Divide the data into historic x and their respective y predictions
def split_sequence(sequence, n_steps_in, n_steps_out):
    X, y = list(), list()
    for i in range(len(sequence)):
        # find the end of this pattern
        end_ix = i + n_steps_in
        out_end_ix = end_ix + n_steps_out
        # check if we are beyond the sequence
        if out_end_ix > len(sequence):
            break
        # gather input and output parts of the pattern
        seq_x, seq_y = sequence[i:end_ix], sequence[end_ix:out_end_ix]
        X.append(seq_x)
        y.append(seq_y)
    return np.array(X), np.array(y)

n_steps_in, n_steps_out = 48, 12
# split into samples
x_train, y_train = split_sequence(train_seq, n_steps_in, n_steps_out)
x_val, y_val = split_sequence(test_seq, n_steps_in, n_steps_out)
```


```python
#Reshape arrays

n_features = 1
x_train = x_train.reshape((x_train.shape[0], x_train.shape[1], n_features))
x_val = x_val.reshape((x_val.shape[0], x_val.shape[1], n_features))
```

### Create and fit the model
Since 12 predictions are being made, then the Dense layer has argument 12. Steps per epoch does not connect to epochs.

Naturally what you want if to 1 epoch your generator pass through all of your training data one time. To achieve this you should provide steps per epoch equal to number of batches like this:

`steps_per_epoch = int( np.ceil(x_train.shape[0] / batch_size) )`

- **steps_per_epoch** the number of batch iterations before a training epoch is considered finished. If you have a training set of fixed size you can ignore it but it may be useful if you have a huge data set or if you are generating random data augmentations on the fly, i.e. if your training set has a (generated) infinite size. If you have the time to go through your whole training data set I recommend to skip this parameter. This value is normally the size of the complete training dataset.
- **validation_steps** similar to steps_per_epoch but on the validation data set instead on the training data. If you have the time to go through your whole validation data set I recommend to skip this parameter.
- **buffer size** TF data is designed to work with possibly infinite sequences, so it doesn't attempt to shuffle the entire sequence in memory. Instead, it maintains a buffer in which it shuffles elements.
- **batch_size** Number of samples per gradient update. Do not specify the `batch_size` in the `.fit()` method if your data is in the form of symbolic tensors, datasets, generators, or keras.utils.Sequence instances (since they generate batches)


```python
import tensorflow as tf
tf.random.set_seed(13)

#shuffle, batch, and cache the dataset when it is too big.

# BATCH_SIZE = 256
# BUFFER_SIZE = 10000

# train_data = tf.data.Dataset.from_tensor_slices((x_train, y_train))
# train_data = train_data.cache().shuffle(BUFFER_SIZE).batch(BATCH_SIZE).repeat()

# val_data = tf.data.Dataset.from_tensor_slices((x_val, y_val))
# val_data = val_data.batch(BATCH_SIZE).repeat()
```


```python
# Create model
multi_step_model = tf.keras.models.Sequential()
multi_step_model.add(tf.keras.layers.LSTM(128,return_sequences=True,
                                          input_shape=x_train.shape[-2:])) #input shape past_history, num of features
multi_step_model.add(tf.keras.layers.LSTM(16, activation='relu'))
multi_step_model.add(tf.keras.layers.Dense(12))

multi_step_model.compile(optimizer=tf.keras.optimizers.Adam(0.001), loss='mse')

multi_step_history = multi_step_model.fit(x_train, y_train, epochs=30,
                                        batch_size=16,
                                        validation_split=0.1,
                                        verbose=2,
                                        shuffle=False)

```

    Train on 623 samples, validate on 70 samples
    Epoch 1/30
    623/623 - 44s - loss: 743.2645 - val_loss: 631.5649
    Epoch 2/30
    623/623 - 19s - loss: 473.3892 - val_loss: 396.5318
    Epoch 3/30
    623/623 - 18s - loss: 323.2871 - val_loss: 365.8038
    Epoch 4/30
    623/623 - 17s - loss: 261.0798 - val_loss: 203.3244
    Epoch 5/30
    623/623 - 18s - loss: 148.0486 - val_loss: 120.5112
    Epoch 6/30
    623/623 - 19s - loss: 70.7203 - val_loss: 52.8588
    Epoch 7/30
    623/623 - 18s - loss: 36.1341 - val_loss: 26.7562
    Epoch 8/30
    623/623 - 19s - loss: 15.6061 - val_loss: 6.3142
    Epoch 9/30
    623/623 - 17s - loss: 3.9004 - val_loss: 0.8214
    Epoch 10/30
    623/623 - 17s - loss: 0.7660 - val_loss: 0.1914
    Epoch 11/30
    623/623 - 18s - loss: 0.7145 - val_loss: 0.1759
    Epoch 12/30
    623/623 - 18s - loss: 0.9867 - val_loss: 0.1610
    Epoch 13/30
    623/623 - 19s - loss: 0.8807 - val_loss: 0.3018
    Epoch 14/30
    623/623 - 18s - loss: 0.5932 - val_loss: 0.3135
    Epoch 15/30
    623/623 - 19s - loss: 0.5836 - val_loss: 0.3260
    Epoch 16/30
    623/623 - 18s - loss: 0.5656 - val_loss: 0.3320
    Epoch 17/30
    623/623 - 18s - loss: 0.5557 - val_loss: 0.3396
    Epoch 18/30
    623/623 - 20s - loss: 0.5485 - val_loss: 0.3445
    Epoch 19/30
    623/623 - 19s - loss: 0.5409 - val_loss: 0.3466
    Epoch 20/30
    623/623 - 21s - loss: 0.5350 - val_loss: 0.3485
    Epoch 21/30
    623/623 - 21s - loss: 0.5300 - val_loss: 0.3500
    Epoch 22/30
    623/623 - 19s - loss: 0.5249 - val_loss: 0.3499
    Epoch 23/30
    623/623 - 19s - loss: 0.5213 - val_loss: 0.3488
    Epoch 24/30
    623/623 - 18s - loss: 0.5188 - val_loss: 0.3458
    Epoch 25/30
    623/623 - 19s - loss: 0.5167 - val_loss: 0.3415
    Epoch 26/30
    623/623 - 17s - loss: 0.5155 - val_loss: 0.3355
    Epoch 27/30
    623/623 - 19s - loss: 0.5144 - val_loss: 0.3285
    Epoch 28/30
    623/623 - 18s - loss: 0.5142 - val_loss: 0.3197
    Epoch 29/30
    623/623 - 18s - loss: 0.5142 - val_loss: 0.3091
    Epoch 30/30
    623/623 - 18s - loss: 0.5157 - val_loss: 0.2969
    

You can plot the training and validation loss across the number of epochs. If the lines continue to go down, it is fitting well. If the lines start going up, it is overfitting.


```python
# Plot the training and validation loss
plt.plot(range(1,31),multi_step_history.history['loss'],label='Training Loss')
plt.plot(range(1,31),multi_step_history.history['val_loss'],label='Validation Loss')
plt.xlabel('Epoch')
plt.ylabel('Loss')
plt.legend()
plt.show()
```


![png](output_39_0.png)


### Make a prediction using the validation set


```python
y_hat = multi_step_model.predict(x_val)
y_hat
```




    array([[29.55667 , 29.312317, 29.425213, 29.529127, 29.337515, 29.41379 ,
            29.44655 , 29.514568, 29.58675 , 29.512802, 29.167267, 29.47086 ]],
          dtype=float32)



### Plot predicted versus true values


```python
plt.plot(range(19),x_val[0][-19:],label='Historic values',marker='o')
plt.plot(range(19,31),y_val[0],label='True values',marker='o')
plt.plot(range(19,31),y_hat[0],label='Predicted values',marker='o')
plt.xticks(ticks=[0,12,24],labels=['Jan 2015','Dec 2015', 'Dec 2016'])
plt.ylim(28,32)
plt.title('Chart 6. Model Fit')
plt.legend()
plt.show()
```


![png](output_43_0.png)


The Chart above did predict a drop in temperature from around 30.5 C° to around 29.5 C°, but it predicted the drop would be in September 2016 instead of December of that year. Thus we have a model that is off for 1 C° in the first 4 months but then it gets a good fit for the next 8 months.

### Predict the next 12 months given the last 48 months

Using a [Tensorflow](https://www.tensorflow.org/) machine learning model, we can try and make a prediction for the average temperature for the next 12 months after the last date in the dataset for the Niño 3.4 Pacific region. The last average value is from August 2017, so the model will predict the next 12 months starting in September 2017.


```python
#Reshape the x values to 3 dimensions so the model can read them
latest_values = np.array([np.reshape(model_df[-48:], (48, 1))])

#Predict
prediction_2017 = multi_step_model.predict(latest_values)
prediction_2017
```




    array([[29.55828 , 29.323019, 29.404554, 29.531096, 29.344824, 29.420351,
            29.439663, 29.534046, 29.607967, 29.484957, 29.115677, 29.495998]],
          dtype=float32)




```python
# Plot
# Import calendar to change month number to month name abbreviation
import calendar

# Get months from pacific_temps dataframe
years_months = pacific_temps_df[['year','month','sstemp']].groupby(['year','month']).mean()[-19:]
years = years_months.index.get_level_values('year')
# Add predicted years to list of years
years = list(years) + [2017]*4 + [2018]*8
months = years_months.index.get_level_values('month')
# Add predicted months to list of months
months = list(months) + [*range(9,13)] + [*range(1,10)]
# Create a list of x labels with all the months
x_labels = []
for i in range(len(months)):
    if i%2==0:
        x_labels.append(calendar.month_abbr[months[i]]+"\n'%s"%str(years[i])[2:]) 

y_history = model_df[-19:]
#Add first value of predicted y values as the last value of x to connect both lines in plot
y_history = np.insert(arr=y_history, obj=19, values=prediction_2017[0][0])




plt.figure(figsize=(10,6))
sns.lineplot(range(20),y_history,label='Latest temps',marker='o')
sns.lineplot(range(19,31),prediction_2017[0],label='Prediction',marker='o')
sns.despine(left=True)
plt.ylabel('temperature C°')
plt.title('Chart 7. Twelve month prediction of Central Pacific Region Average SS Temperatures')
plt.xticks(ticks=[*range(0,31,2)],labels=x_labels)
plt.ylim(28,32)
plt.show()
```


![png](output_46_0.png)


**Chart 4.** Prediction of the next 12 months after August 2017. Only 19 previous months are plotted of the 48 that were used to make the prediction. The year 2017 up until August shows a drop in temperatures compared to previous years. The prediction is indicating a rise  


```python
import plotly.graph_objects as go

fig = go.Figure()
fig.add_trace(go.Scatter(
    x=[*range(20)],
    y=y_history,
    marker=dict(color="blue", size=12),
    mode="lines+markers",
    name="Latest temps",
    hovertemplate='%{y:.2f} C°'
))

fig.add_trace(go.Scatter(
    x=[*range(19,31)],
    y=prediction_2017[0],
    marker=dict(color="orange", size=12),
    mode="lines+markers",
    name="Predictions",
    hovertemplate='%{y:.2f} C°'
))

fig.update_layout(title={'font':{'size':14},
                         'text':"Chart 7. Twelve month prediction of Central Pacific Region Average SS Temperatures"},
                  yaxis_title="temperature C°",
                 autosize=False,
                 width=800,
                 height=450)
fig.update_xaxes(
    ticktext=x_labels,
    tickvals=[*range(0,31,2)]
#    tickangle=90
)

fig.update_yaxes(
    nticks=10
)

fig.show()
```


<div>


            <div id="a8b69ee4-345d-457c-844a-859884d5014a" class="plotly-graph-div" style="height:450px; width:800px;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("a8b69ee4-345d-457c-844a-859884d5014a")) {
                    Plotly.newPlot(
                        'a8b69ee4-345d-457c-844a-859884d5014a',
                        [{"hovertemplate": "%{y:.2f} C\u00b0", "marker": {"color": "blue", "size": 12}, "mode": "lines+markers", "name": "Latest temps", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19], "y": [30.356432636648904, 30.328394815482568, 30.603272423852292, 30.44539410703184, 30.233608877401466, 30.271258083480287, 30.395578512396707, 30.26013440860216, 30.44576923076924, 30.233080808080814, 30.32356506493506, 29.454138004744976, 29.48048039952226, 29.620470440703684, 29.655873227194498, 29.44115987490343, 29.21466213711612, 29.226219741955983, 29.310316820276505, 29.55828094482422]}, {"hovertemplate": "%{y:.2f} C\u00b0", "marker": {"color": "orange", "size": 12}, "mode": "lines+markers", "name": "Predictions", "type": "scatter", "x": [19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30], "y": [29.55828094482422, 29.32301902770996, 29.40455436706543, 29.531095504760742, 29.344823837280273, 29.420351028442383, 29.43966293334961, 29.534046173095703, 29.607967376708984, 29.484956741333008, 29.115676879882812, 29.49599838256836]}],
                        {"autosize": false, "height": 450, "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"font": {"size": 14}, "text": "Chart 7. Twelve month prediction of Central Pacific Region Average SS Temperatures"}, "width": 800, "xaxis": {"ticktext": ["Feb\n'16", "Apr\n'16", "Jun\n'16", "Aug\n'16", "Oct\n'16", "Dec\n'16", "Feb\n'17", "Apr\n'17", "Jun\n'17", "Aug\n'17", "Oct\n'17", "Dec\n'17", "Feb\n'18", "Apr\n'18", "Jun\n'18", "Aug\n'18"], "tickvals": [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30]}, "yaxis": {"nticks": 10, "title": {"text": "temperature C\u00b0"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('a8b69ee4-345d-457c-844a-859884d5014a');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



```python
# Prepare your plotly plot to be embeded
import plotly.io as pio
import chart_studio.tools as tls

#Create HTML of plotly plot
# pio.write_html(fig, file='sstemps.html', auto_open=True) 

#Save the file in the _includes folder of your github page root. Embed using the line {% include sstemps.html %}
```


```python

```
