## World SQL Challenge Solutions

1. Using `COUNT`, get the number of cities in the USA.
```sql
SELECT COUNT(ID) FROM city WHERE CountryCode='USA';
```
2. Find out the population and life expectancy for people in Argentina.
```sql
SELECT Population, LifeExpectancy FROM country WHERE Name='Argentina';
```
3. Using `IS NOT NULL`, `ORDER BY`, and `LIMIT`, which country has the highest life expectancy?
```sql
SELECT Name FROM country WHERE LifeExpectancy IS NOT NULL ORDER BY LifeExpectancy DESC LIMIT 1;
```
4. Using `JOIN ... ON`, find the capital city of Spain.
```sql
SELECT city.Name FROM city JOIN country ON city.ID=country.Capital WHERE country.Name='Spain';
```
5. Using `JOIN ... ON`, list all the languages spoken in the Southeast Asia region.
```sql
SELECT DISTINCT countrylanguage.Language FROM countrylanguage JOIN country ON countrylanguage.CountryCode=country.Code WHERE Region='Southeast\ Asia';
```
6. Using a single query, list 25 cities around the world that start with the letter F.
```sql
SELECT Name FROM city WHERE Name LIKE 'F%' LIMIT 25;
```
7. Using `COUNT` and `JOIN ... ON`, get the number of cities in China.
```sql
SELECT COUNT(city.ID) FROM city JOIN country ON city.CountryCode=country.Code WHERE country.Name='China';
```
8. Using `IS NOT NULL`, `ORDER BY`, and `LIMIT`, which country has the lowest population? Discard non-zero populations.
```sql
SELECT Name FROM country WHERE Population IS NOT NULL ORDER BY Population ASC LIMIT 1;
```
9. Using aggregate functions, return the number of countries the database contains.
```sql
SELECT COUNT(Code) FROM country;
```
10. What are the top ten largest countries by area?
```sql
SELECT Name FROM country ORDER BY SurfaceArea DESC LIMIT 10;
```
11. List the five largest cities by population in Japan.
```sql
SELECT city.Name FROM city JOIN country ON city.CountryCode=country.Code WHERE country.Name='Japan' ORDER BY city.Population DESC LIMIT 5;
```
12. List the names and country codes of every country with Elizabeth II as its Head of State. You will need to fix the mistake first!
```sql
UPDATE country SET HeadOfState = 'Elizabeth II' WHERE HeadOfState = 'Elisabeth II';
```
```sql
SELECT Name, Code FROM country WHERE HeadOfState = 'Elizabeth II';
```
13. List the top ten countries with the smallest population-to-area ratio. Discard any countries with a ratio of 0.
```sql
SELECT Name FROM country WHERE (Population/SurfaceArea) IS NOT NULL ORDER BY (Population/SurfaceArea) ASC LIMIT 10;
```
14. List every unique world language.
```sql
SELECT DISTINCT Language FROM countrylanguage;
```
15. List the names and GNP of the world's top 10 richest countries.
```sql
SELECT Name, GNP FROM country ORDER BY GNP DESC LIMIT 10;
```
16. List the names of, and number of languages spoken by, the top ten most multilingual countries.
```sql

```
17. List every country where over 50% of its population can speak German.
```sql

```
18. Which country has the worst life expectancy? Discard zero or null values.
```sql

```
19. List the top three most common government forms.
```sql

```
20. How many countries have gained independence since records began?
```sql

```
