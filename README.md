# SQL Exercises 
Training on SQL. Performed on https://sqlbolt.com between 1 Dec, 2017 and 2 Dec, 2017.

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


