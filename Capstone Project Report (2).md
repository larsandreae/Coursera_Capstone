## Data

### Data sources

* Foursquare
   * [GET Venue Search](https://developer.foursquare.com/docs/api-reference/venues/search/)
      * ll = geolocations of cities
      * intent = browse
      * radius = 500 - 5000 m -> dependent if limit of venue search is reached
      * limit = maximum possible (50?)
   
* German cities
   * [Names and population size (2018 data) from Wikipedia](https://de.wikipedia.org/wiki/Liste_der_Gro%C3%9F-_und_Mittelst%C3%A4dte_in_Deutschland#Gro%C3%9F-_und_Mittelst%C3%A4dte_nach_Einwohnerzahl)
   * Geographic location: [Geopy with OSM Nominatim](https://geopy.readthedocs.io/en/stable/)
