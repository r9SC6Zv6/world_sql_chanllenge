# Sakila SQL Challenge Solutions

1. List all actors.
```sql
SELECT first_name, last_name FROM actor;
```
2. Find the surname of the actor with the forename 'John'.
```sql
SELECT last_name FROM actor WHERE first_name = 'John';
```
3. Find all actors with surname 'Neeson'.
```sql
SELECT first_name, last_name FROM actor WHERE last_name = 'Neeson';
```
4. Find all actors with ID numbers divisible by 10.
```sql
SELECT first_name, last_name FROM actor WHERE (actor_id % 10) = 0;
```
5. What is the description of the movie with an ID of 100?
```sql
SELECT description FROM film WHERE film_id = 100;
```
6. Find every R-rated movie.
```sql
SELECT title FROM film WHERE rating = 'R';
```
7. Find every non-R-rated movie.
```sql
SELECT title FROM film WHERE rating != 'R';
```
8. Find the ten shortest movies.
```sql
SELECT title FROM film ORDER BY length ASC LIMIT 10;
```
9. Find the movies with the longest runtime, without using `LIMIT`.
```sql
SELECT title FROM film WHERE length = (SELECT MAX(length) FROM film);
```
10. Find all movies that have deleted scenes.
```sql
SELECT title FROM film WHERE special_features = 'Deleted\ Scenes';
```
11. Using `HAVING`, reverse-alphabetically list the last names that are not repeated.
```sql
SELECT last_name FROM actor GROUP BY last_name HAVING COUNT(last_name) <= 1 ORDER BY last_name DESC;
```
12. Using `HAVING`, list the last names that appear more than once, from highest to lowest frequency.
```sql
SELECT last_name FROM actor GROUP BY last_name HAVING COUNT(last_name) > 1 ORDER BY COUNT(last_name) DESC;
```
13. Which actor has appeared in the most films?
```sql

```
14. When is 'Academy Dinosaur' due?
```sql

```
15. What is the average runtime of all films?
```sql
SELECT AVG(length) FROM film;
```
16. List the average runtime for every film category.
```sql

```
17. List all movies featuring a robot.
```sql

```
18. How many movies were released in 2010?
```sql
SELECT COUNT(film_id) FROM film WHERE release_year = '2010';
```
19. Find the titles of all the horror movies.
```sql
SELECT film.title FROM ((film_category JOIN film ON film_category.film_id = film.film_id) JOIN category ON film_category.category_id = category.category_id) WHERE category.name = 'Horror';
```
20. List the full name of the staff member with the ID of 2.
```sql
SELECT first_name, last_name FROM staff WHERE staff_id = 2;
```
21. List all the movies that Fred Costner has appeared in.
```sql

```
22. How many distinct countries are there?
```sql
SELECT DISTINCT COUNT(country) FROM country;
```
23. List the name of every language in reverse-alphabetical order.
```sql
SELECT name FROM language ORDER BY name DESC;
```
24. List the full names of every actor whose surname ends with '-son' in alphabetical order by their forename.
```sql
SELECT first_name, last_name FROM actor WHERE last_name LIKE '%son' ORDER BY first_name ASC;
```
25. Which category contains the most films?
```sql
SELECT name FROM category WHERE category_id = (SELECT category_id FROM film_category GROUP BY category_id ORDER BY COUNT(category_id) DESC LIMIT 1);
```
