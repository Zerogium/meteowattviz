# meteowattviz
The idea is to cross open data delivered by Meteo France and Enedis to check the commonly accepted assertion that the weather influences our heat consumption.

# The data
- from Enedis we could download for free either annual average electricity consumption per Région/city/quartier or daily french electricity consumption
- from Meteo France we could download for free only measures from 41 stations located in France taken every 3 hours for 1 month.

Based on that, we decided to take the measures from the station of Nantes (France, 44000) in June 2017 and to compare it to the national french electricity consumption.

# Temperature Graph
We used SQL Plugin for Firefox to process the data from the Meteo France station of Nantes (France, 44000).
We wished to retain only the average temperature of each day, so we used the following query:

'''sql 
SELECT substr(date_col_ID,0,9) as jour, date_col_ID, avg(temperature_col_ID)-273.15 FROM tablename WHERE num_station_col_ID=<num_station_ID> GROUP BY substr(date_col_ID,0,9);
'''

num_station_col_ID for Nantes (France, 440000) is 07222, in the World Meteo Organization classification.

The resulting graph is available in this repo as "GraphTemp.png".

# Rain Graph

# Electricity consumption Graph

# Limits
Our starting point is that the electricity consumption *is* representative of the heat consumption.
