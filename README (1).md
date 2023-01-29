
# COUNT/DISTINCT/LIMIT




## Retrieve the number of locations of the films which are directed by Woody Allen.
SELECT COUNT(Locations) FROM FilmLocations WHERE Director="Woody Allen";

## Retrieve the number of films shot at Russian Hill. 

SELECT Count(Title) FROM FilmLocations WHERE Locations="Russian Hill";
## Retrieve the number of rows having a release year older than 1950 from the “FilmLocations” table.
SELECT Count(*) FROM FilmLocations WHERE ReleaseYear<1950;
## Retrieve the number of rows having a release year older than 1950 from the “FilmLocations” table.
## Retrieve the name of all films without any repeated titles.
SELECT DISTINCT Title FROM FilmLocations;