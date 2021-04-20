# LabTask-2-SQL

-- CREATE TABLE movies(
-- movie_id integer primary key auto_increment,
-- title varchar(255),
-- year_released integer,
-- director_id integer,
-- foreign key(director_id) references directors(director_id)
-- );

-- CREATE TABLE directors(
-- director_id integer primary key auto_increment,
-- first_name varchar(255),
-- last_name varchar(255),
-- country varchar(255)
-- );

-- Question 1
-- SELECT title
-- FROM movies;

-- Question 2
-- SELECT title, year_released
-- FROM movies
-- ORDER BY year_released DESC;

-- Question 3
-- SELECT *
-- FROM directors
-- ORDER BY country ASC;

-- Question 4
-- SELECT *
-- FROM directors
-- ORDER BY country ASC, last_name ASC;

-- Question 5
-- INSERT INTO directors (first_name, last_name, country)
-- VALUES ("Rob", "Reiner", "USA");

-- Question 6
-- SELECT last_name, director_id
-- FROM directors
-- WHERE first_name = "Rob" AND last_name = "Reiner";

-- Question 7
-- INSERT INTO movies (title, year_released, director_id)
-- VALUES ("The Princess bride", 1987, 11);

-- Question 8
-- SELECT movies.title, movies.year_released, directors.last_name
-- FROM movies
-- INNER JOIN directors
-- ON movies.director_id = directors.director_id;

-- Question 9
-- SELECT movies.title, directors.first_name, directors.last_name
-- FROM movies
-- INNER JOIN directors
-- ON movies.director_id = directors.director_id
-- ORDER BY directors.last_name ASC;

-- Question 10
-- SELECT first_name, last_name
-- FROM directors
-- WHERE director_id = 2;

-- Question 11
-- SELECT directors.last_name, directors.country
-- FROM movies
-- INNER JOIN directors
-- ON movies.director_id = directors.director_id
-- WHERE title = "Roma";

-- Question 12
-- DELETE FROM movies
-- WHERE movie_id = 17;
-- Deleting a row from the the Movies table has no effect on the Directors table

-- Question 13
-- DELETE FROM directors
-- WHERE director_id = 7;
-- If there is no corresding movie row, the movie row gets deleted else it throws an error

-- Question 14
-- SELECT title AS movie_name, year_released AS production_date, director_id AS director
-- FROM movies;

-- Question 15
-- SELECT movies.title
-- FROM movies
-- INNER JOIN directors
-- ON movies.director_id = directors.director_id
-- WHERE first_name = "Peter" AND last_name = "Jackson";

-- Question 16
-- ALTER TABLE movies
-- ADD money_made decimal;
-- a...
-- SET SQL_SAFE_UPDATES=0;
-- UPDATE movies
-- SET money_made = RAND()*10000
-- WHERE money_made IS NULL;
-- SET SQL_SAFE_UPDATES=1;
-- b....
-- SELECT title, money_made
-- FROM movies
-- ORDER BY money_made DESC;
-- c...
SELECT title, money_made
FROM movies
WHERE money_made > 300;
