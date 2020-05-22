## Data

### Data sources

* Geolocations and population size of German cities
   * [Names and population size (2018 data) from Wikipedia table](https://de.wikipedia.org/wiki/Liste_der_Gro%C3%9F-_und_Mittelst%C3%A4dte_in_Deutschland#Gro%C3%9F-_und_Mittelst%C3%A4dte_nach_Einwohnerzahl)
   * Geographic location, by city name from Wikipedia table: [Geopy with OSM Nominatim](https://geopy.readthedocs.io/en/stable/)

* Foursquare
   * [GET Venue Search](https://developer.foursquare.com/docs/api-reference/venues/search/)
      * Parameters to use:
         * ll = geolocations of cities
         * intent = browse
         * radius = 500 - 5000 m -> dependent if limit of venue search is reached
         * limit = maximum possible
 
 #### [Example Notebook](https://nbviewer.jupyter.org/github/larsandreae/Coursera_Capstone/blob/master/PGA_Cap_wk1_Data.ipynb)
 
 ### Data wrangling
 
 * Creating a city dataframe with
    * Name
    * Location (Lat, Long)
    * Population
 
 * Reducing the Foursquare dataset to
    * id of venue
    * location of venue: city, lat, lng
    * primary category of venue
    * number of venues per city
    
 * Merging both datasets
 
 ### Data visualisation
 
 * Using Matplotlib to create
    * Histograms
    * Scatterplots
    * ...
 
 * Using Folium to create maps
