# SQL Exercises 
Training on SQL. Received at https://sqlbolt.com on 1 Dec, 2017.


## SQL Lesson 1: SELECT queries 101 at https://sqlbolt.com/lesson/select_queries_introduction

ANSWERS:

SELECT Title FROM movies;

SELECT Director FROM movies;

SELECT Title, Director FROM movies;

SELECT Title, Year FROM movies;

SELECT * FROM movies;


## SQL Lesson 2: Queries with constraints (Pt. 1) at https://sqlbolt.com/lesson/select_queries_with_constraints

ANSWERS:

SELECT * FROM movies WHERE Id = 6;

SELECT * FROM movies WHERE Year BETWEEN 2000 AND 2010;

SELECT * FROM movies WHERE Year NOT BETWEEN 2000 AND 2010;

SELECT Title, Year FROM movies LIMIT 5;


## SQL Lesson 3: Queries with constraints (Pt. 2) at https://sqlbolt.com/lesson/select_queries_with_constraints_pt_2

ANSWERS:

SELECT * FROM movies WHERE Title LIKE "%Toy%";

SELECT * FROM movies WHERE Director = "John Lasseter";

SELECT * FROM movies WHERE Director != "John Lasseter";

SELECT * FROM movies WHERE Title LIKE "WALL_%";


## SQL Lesson 4: Filtering and sorting Query results at https://sqlbolt.com/lesson/filtering_sorting_query_results

ANSWERS:

SELECT DISTINCT Director FROM movies ORDER BY Director ASC;

SELECT * FROM movies ORDER BY Year DESC LIMIT 4;

SELECT * FROM movies ORDER BY Title ASC LIMIT 5;

SELECT * FROM movies ORDER BY Title ASC LIMIT 5 OFFSET 5;


## SQL Review: Simple SELECT Queries at https://sqlbolt.com/lesson/select_queries_review

SELECT City, Population FROM north_american_cities WHERE Country = "Canada";

SELECT City FROM north_american_cities WHERE Country = "United States" ORDER BY Latitude DESC;

SELECT City FROM north_american_cities WHERE Longitude < (SELECT Longitude FROM north_american_cities WHERE City = "Chicago") ORDER BY Longitude ASC;

SELECT City FROM north_american_cities WHERE Country = "Mexico" ORDER BY Population DESC LIMIT 2;

SELECT City, Population FROM north_american_cities WHERE Country = "United States" ORDER BY Population DESC LIMIT 2 OFFSET 2;


## SQL Lesson 6: Multi-table queries with JOINs

ANSWERS:

SELECT Title, Domestic_sales, International_sales FROM movies INNER JOIN Boxoffice ON movies.Id = Boxoffice.Movie_id;

SELECT Title, Domestic_sales, International_sales FROM movies INNER JOIN Boxoffice ON movies.Id = Boxoffice.Movie_id WHERE International_sales > Domestic_sales;

SELECT Title, Rating FROM movies INNER JOIN Boxoffice ON movies.Id = Boxoffice.Movie_id ORDER BY Rating DESC;


## SQL Lesson 7: OUTER JOINs at https://sqlbolt.com/lesson/select_queries_with_outer_joins

ANSWERS:

SELECT DISTINCT Building_name FROM Buildings LEFT JOIN Employees ON Buildings.Building_name = Employees.Building WHERE Building IS NOT NULL;

SELECT * FROM Buildings;

SELECT DISTINCT Building_name, Role FROM Buildings LEFT JOIN Employees ON Buildings.Building_name = Employees.Building;


## SQL Lesson 8: A short note on NULLs at https://sqlbolt.com/lesson/select_queries_with_nulls

ANSWERS:

SELECT Name, Role, Building FROM Employees LEFT JOIN Buildings ON Employees.Building = Buildings.Building_name WHERE Building_name IS NULL;

SELECT Building_name FROM Buildings LEFT JOIN Employees ON Buildings.Building_name = Employees.Building WHERE Building IS NULL;


## SQL Lesson 9: Queries with expressions at https://sqlbolt.com/lesson/select_queries_with_expressions

ANSWERS:

SELECT Title, (International_sales + Domestic_sales)/1000000 AS Sales FROM Movies INNER JOIN Boxoffice ON Movies.Id = Boxoffice.Movie_id;

SELECT Title, Rating*10 AS Raing_Percentage FROM Movies INNER JOIN Boxoffice ON Movies.Id = Boxoffice.Movie_Id;

SELECT Title, Year FROM Movies INNER JOIN Boxoffice ON Movies.Id = Boxoffice.Movie_Id WHERE Year % 2 = 0;


## SQL Lesson 10: Queries with aggregates (Pt. 1) at https://sqlbolt.com/lesson/select_queries_with_aggregates

ANSWERS:

SELECT Name, MAX(Years_employed) FROM employees;

SELECT Role, AVG(Years_employed) AS Average_Years_Employed FROM Employees GROUP BY Role;

SELECT Building, SUM(Years_employed) AS Total__of_Years_Employed FROM Employees GROUP BY Building;


## SQL Lesson 11: Queries with aggregates (Pt. 2) at https://sqlbolt.com/lesson/select_queries_with_aggregates_pt_2

ANSWERS:

SELECT COUNT(*) FROM Employees WHERE Role IS NOT NULL AND Role = 'Artist";

SELECT DISTINCT Role, COUNT(*) AS Count FROM Employees WHERE Name IS NOT NULL GROUP BY Role;

SELECT Role, SUM(Years_employed) AS Total_Years_Employed FROM Employees WHERE Role = 'Engineer';


## SQL Lesson 12: Order of execution of a Query at https://sqlbolt.com/lesson/select_queries_order_of_execution

ANSWERS:

SELECT Director, COUNT(*) AS Number_of_Movies FROM Movies INNER JOIN Boxoffice ON Movies.Id = Boxoffice.Movie_id WHERE TITLE IS NOT NULL GROUP BY Director;

SELECT Director, SUM(Domestic_sales + International_sales) AS Total_Sales FROM Movies INNER JOIN Boxoffice ON Movies.Id = Boxoffice.Movie_id GROUP BY Director;


## SQL Lesson 13: Inserting rows at https://sqlbolt.com/lesson/inserting_rows

ANSWERS:

INSERT INTO Movies (Title, Director, Year, Length_minutes) VALUES ('Toy Story 4', 'John Lasseter', 1995, 81);

INSERT INTO Boxoffice (Movie_id, Rating, Domestic_sales, International_sales) VALUES (16, 8.7, 340000000, 270000000);


## SQL Lesson 14: Updating rows at https://sqlbolt.com/lesson/updating_rows

ANSWERS:

UPDATE Movies SET Director = 'John Lasseter' WHERE Id = 2;

UPDATE Movies SET Year = 1999 WHERE Id = 3;

UPDATE Movies SET Title = 'Toy Story 3', Director = 'Lee Unkrich' WHERE Id = 11;


## SQL Lesson 15: Deleting rows at https://sqlbolt.com/lesson/deleting_rows

ANSWERS:

DELETE FROM Movies WHERE Year < 2005;

DELETE FROM Movies WHERE Director = 'Andrew Stanton';


## SQL Lesson 16: Creating tables at https://sqlbolt.com/lesson/creating_tables

ANSWERS:

CREATE TABLE IF NOT EXISTS Database (Name STRING, Version FLOAT, Download_count INTEGER);


## SQL Lesson 17: Altering tables at https://sqlbolt.com/lesson/altering_tables

ANSWERS:

ALTER TABLE Movies ADD Aspect_ratio FLOAT;

ALTER TABLE Movies ADD Language TEXT DEFAULT "English";


## SQL Lesson 18: Dropping tables at https://sqlbolt.com/lesson/dropping_tables

ANSWERS:

DROP TABLE IF EXISTS Movies;

DROP TABLE IF EXISTS Boxoffice;
