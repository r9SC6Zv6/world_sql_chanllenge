## World SQL Challenge Solutions

1. Using `COUNT`, get the number of cities in the USA.
```sql
SELECT COUNT(ID) FROM city WHERE CountryCode='USA';
```
2. Find out the population and life expectancy for people in Argentina.
```sql
SELECT Population, LifeExpectancy FROM country WHERE Name='Argentina';
```
3. Using IS NOT NULL, ORDER BY, and LIMIT, which country has the highest life expectancy?
```sql
SELECT Name FROM country WHERE LifeExpectancy IS NOT NULL ORDER BY LifeExpectancy DESC LIMIT 1;
```
4. Using JOIN ... ON, find the capital city of Spain.
```sql
SELECT city.Name FROM city JOIN country ON city.ID=country.Capital WHERE country.Name='Spain';
```
5. Using JOIN ... ON, list all the languages spoken in the Southeast Asia region.
```sql

```
6. Using a single query, list 25 cities around the world that start with the letter F.
```sql

```
7. Using COUNT and JOIN ... ON, get the number of cities in China.
```sql

```
8. Using IS NOT NULL, ORDER BY, and LIMIT, which country has the lowest population? Discard non-zero populations.
```sql

```
9. Using aggregate functions, return the number of countries the database contains.
```sql

```
10. What are the top ten largest countries by area?
```sql

```
11. List the five largest cities by population in Japan.
```sql

```
12. List the names and country codes of every country with Elizabeth II as its Head of State. You will need to fix the mistake first!
```sql

```
13. List the top ten countries with the smallest population-to-area ratio. Discard any countries with a ratio of 0.
```sql

```
14. List every unique world language.
```sql

```
15. List the names and GNP of the world's top 10 richest countries.
```sql

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
