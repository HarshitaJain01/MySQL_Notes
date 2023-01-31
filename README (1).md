
# COUNT/DISTINCT/LIMIT



## COUNT
### Retrieve the number of locations of the films which are directed by Woody Allen.
SELECT COUNT(Locations) FROM FilmLocations WHERE Director="Woody Allen";

### Retrieve the number of films shot at Russian Hill. 
SELECT Count(Title) FROM FilmLocations WHERE Locations="Russian Hill";

### Retrieve the number of rows having a release year older than 1950 from the “FilmLocations” table.
SELECT Count(*) FROM FilmLocations WHERE ReleaseYear<1950;

## DISTINCT
### Retrieve the name of all films without any repeated titles.
SELECT DISTINCT Title FROM FilmLocations;

### Retrieve the number of release years of the films distinctly, produced by Warner Bros. Pictures.
SELECT COUNT(DISTINCT ReleaseYear) FROM FilmLocations WHERE ProductionCompany="Warner Bros. Pictures";

### Retrieve the name of all unique films released in the 21st century and onwards, along with their release years.
SELECT DISTINCT Title, ReleaseYear FROM FilmLocations WHERE ReleaseYear>=2001;

### Retrieve the names of all the directors and their distinct films shot at City Hall.
SELECT DISTINCT Title, Director FROM FilmLocations WHERE Locations="City Hall";

### Retrieve the number of distributors distinctly who distributed films acted by Clint Eastwood as 1st actor.
SELECT COUNT(DISTINCT Distributor) FROM FilmLocations WHERE Actor1="Clint Eastwood";

## LIMIT
### Retrieve the first 15 rows from the “FilmLocations” table starting from row 11.
SELECT * FROM FilmLocations LIMIT 15 OFFSET 10;

### Retrieve the name of first 50 films distinctly.
SELECT DISTINCT Title FROM FilmLocations LIMIT 50;

### Retrieve first 10 film names distinctly released in 2015.
SELECT DISTINCT Title FROM FilmLocations WHERE ReleaseYear=2015 LIMIT 10;

### Retrieve the next 3 film names distinctly after first 5 films released in 2015.
SELECT DISTINCT Title FROM FilmLocations WHERE ReleaseYear=2015 LIMIT 3 OFFSET 5;

When using the UPDATE statement, if you do not specify the WHERE clause, all the rows in the table are updated.
COUNT, DISTINCT, and LIMIT are expressions that are used with SELECT statements. 
INSERT, UPDATE, and DELETE are DML statements for populating and changing tables. 

# INSERT/UPDATE/DELETE

## INSERT statement
INSERT INTO table_name (column1, column2, ... )
VALUES (value1, value2, ... )
;

### Insert a new instructor record with id 7 for Antonio Cangiano who lives in Vancouver, CA into the “Instructor” table.
INSERT INTO Instructor(ins_id, lastname, firstname, city, country)
VALUES(7, 'Cangiano', 'Antonio', 'Vancouver', 'CA');

SELECT * FROM Instructor;

### Insert two new instructor records into the “Instructor” table. First record with id 8 for Steve Ryan who lives in Barlby, GB. Second record with id 9 for Ramesh Sannareddy who lives in Hyderabad, IN.
INSERT INTO Instructor(ins_id, lastname, firstname, city, country)
VALUES(8, 'Ryan', 'Steve', 'Barlby', 'GB'), (9, 'Sannareddy', 'Ramesh', 'Hyderabad', 'IN');

SELECT * FROM Instructor;

## UPDATE statement
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition
;

### Update the city for Sandip to Toronto.
UPDATE Instructor 
SET city='Toronto' 
WHERE firstname="Sandip";

### Update the city of the instructor record to Markham whose id is 1.
UPDATE Instructor 
SET city='Markham' 
WHERE ins_id=1;

SELECT * FROM Instructor;

### Update the city and country for Sandip with id 4 to Dhaka and BD respectively.
UPDATE Instructor 
SET city='Dhaka', country='BD' 
WHERE ins_id=4;

SELECT * FROM Instructor;


## DELETE statement
DELETE FROM table_name
WHERE condition
;

