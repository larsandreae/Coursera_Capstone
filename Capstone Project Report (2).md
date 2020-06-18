## Data

### Data sources

* [List of German cities defined as "Großstadt" from Wikipedia](https://de.wikipedia.org/wiki/Liste_der_Gro%C3%9Fst%C3%A4dte_in_Deutschland#Tabelle)
   * Name of City
   * Population (latest data from 2018)
   * Area of city (2016 data)

The list from Wikipedia is the basis for the analysis. It includes all German cities with a population of > 100,000 (definition of "Großstadt").
I will use the city name, the population data from 2018 and the area (sqkm).


* [OpenStreetMap with Geopy (OSM Nominatim), using the city name](https://geopy.readthedocs.io/en/stable/)
   * Latitude
   * Longitude

Using the city's name I can retrieve the geographic location with the help of Geopy / OpenStreetMap.
The location data will be used to show the cities on a map (Folium) and, of course, to retrieve the venues using the Foursquare API.


[Foursquare GET Venue Search](https://developer.foursquare.com/docs/api-reference/venues/search/)
   * parameters:
         * geolocation of city (longitude, latitude)
         * radius = tbd
         * limit = (as many as possible)
   * data: 
      * venue name
      * primary category of venue

I will retrieve the venues for each city from Foursquare using their geolocations, which I got via Geopy in the step before.

**The Foursquare search parameters and restrictions will likely be limiting my data I can use later on.**

First of all, I will have to choose one search radius for all the different German cities.

* A large radius will likely cover the smaller cities completely, which means the resulting data will be a good representation of the total number of venues for this city.
* But for cities with a lot of Foursquare data or a large area, the maximum number of venues I can retrieve from the Foursquare API will likely be reached. This 'cut-off' will make a comparison between these cities difficult (they will all have the same total number of venues).

The start radius will be calculated from the median of the cities area data.

### Jupyter Notebook: [PGA_Cap_wk1_Data_v2](https://nbviewer.jupyter.org/github/larsandreae/Coursera_Capstone/blob/master/PGA_Cap_wk1_Data_v2.ipynb)

### Data wrangling
 
* Creating a city dataframe with
   * Name
   * Population
   * Location (Latitude, Longitude)

* Creating a Foursquare dataframe with
   * venue name
   * venue category
 
* One-hot encoded dataframe
   * summarizing the venues per venue category per city

* Adding to the city dataframe
   * the number of venues per city derived from the Foursquare dataframe
   * deriving a "venue density"
      * per population and/or
      * per city area and/or
      * per Foursquare search area (radius)
 
### Data visualisation
 
* Using Matplotlib to create
   * Histograms
   * Scatterplots
 
* Using Folium to create maps with the location of the cities
 
## Data summary
 
**The final dataframe I will use for the comparison / data science consists of 54 cities.
In the end, I have limited myself to cities with a population size less than 250,000.
Even then, I still have several cities left that reach the venue count limit of 100.
I will keep these cities for now. But I may discard them later on if they distort my data science methods.**
