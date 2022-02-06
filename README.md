# World Weather Analysis

<details><summary>Table of Contents</summary>
<p>

1. [Overview](https://github.com/catsdata/World_Weather_Analysis#overview)
2. [Resources](https://github.com/catsdata/World_Weather_Analysis#resources)
3. [Results](https://github.com/catsdata/World_Weather_Analysis#results)
4. [Summary](https://github.com/catsdata/World_Weather_Analysis#summary)

</p>
</details>

## Overview

This project is to expand on the PlanMyTripp app to allow users to select preferred average temperatures for their vacation destinations.  Users will enter their range, and then have cities with nearest hotels selectable for an itinerary.  From there they will get the data of the hotels, weather, and travel routes between cities.  

## Resources

- Data Sources: [worldcities.csv](https://github.com/catsdata/World_Weather_Analysis/blob/main/worldcities.csv), [Google APIs](https://console.developers.google.com/), [Open Weather APIs](http://api.openweathermap.org)
- Software: 
    - Jupyter Notebook 6.4.6
    - Python 3.7.11 with dependencies: 
        - pandas 1.3.5
        - numpy 1.20.3
        - MatPlotLib 3.5.0
        - citipy 0.0.5
    - Anaconda Command line Client 1.9.0
    - Conda 4.11.0


## Results

- ### World Database:

Using Citipy with a "worldcities" csv file, along with Open Weather APIs, we were able to generate a random list of 699 locations (longitude and latitude's of ideal vacation weather).  Output file includes Max Temps, Hunmidity, Cloudiness, and Wind Speeds.   This output file will be used to generate a vacation search and itinerary.  

Link to the csv file and code: [Weather Database](https://github.com/catsdata/World_Weather_Analysis/tree/main/Weather_Database)
    
- ### Vacation Search:

Parameters were added for preferred weather temps of 70 to 85 degrees.  Importing the list for the World Database above, we cross referenced the list with Google API's to find the nearest hotels to the coordinates.  Hotel information was imported, and then locations without hotels were removed from the database.  The database now included 233 locations with an interactive map for zooming and looking up site weather and hotel details.

Link to the csv file and code:  [Vacation Search](https://github.com/catsdata/World_Weather_Analysis/tree/main/Vacation_Search)
    
![WeatherPy_vacation_map.png](https://github.com/catsdata/World_Weather_Analysis/blob/main/Vacation_Search/WeatherPy_vacation_map.png)
 
- ### Vacation Itinerary

Now that we had selectabe locations, it was time to find four locations within close proixmity for a four stop vacation itinerary.  For this example, we selected four cities within Brazil at our ideal vacation temps.  Maps were generated to show the Driving itinerary between the cities, as well as a marker map with interactive details on each location.

Link to the csv file and code:  [Vacation Itinerary](https://github.com/catsdata/World_Weather_Analysis/tree/main/Vacation_Itinerary)

![WeatherPy_travel_map](https://github.com/catsdata/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map.png)
![WeatherPy_travel_map_markers](https://github.com/catsdata/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map_markers.png)

## Summary

Within writing the code, debugging needed to occur to remove empty strings and replace with NaN before removing locations without matching local hotels.
