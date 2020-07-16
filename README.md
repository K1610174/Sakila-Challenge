# Sakila-Database Exercises

1. SELECT * FROM actor;
2. SELECT * FROM actor WHERE first_name='John';
3. SELECT * FROM actor WHERE last_name='Neeson';
4. SELECT * FROM actor WHERE (actor_id%10)=0;
5. SELECT description FROM film WHERE film_id=100;
6. SELECT * FROM film WHERE rating='R';
7. SELECT * FROM film WHERE rating!='R';
8. SELECT * FROM film WHERE length=(SELECT MIN(length) FROM film) LIMIT 10;
9. SELECT title FROM film WHERE length=(SELECT MIN(length) FROM film) LIMIT 10;
10.
11. SELECT DISTINCT last_name FROM actor;
12. SELECT last_name, COUNT(last_name) FROM actor GROUP BY last_name HAVING COUNT(last_name) > 1;
13.
14.
15.
16. SELECT AVG(length) FROM film;
17. SELECT AVG(film.length) FROM film JOIN film_category fc ON film.film_id = fc.film_id JOIN category c ON fc.category_id=c.category_id GROUP BY c.name ;
18. 
19. SELECT * FROM film WHERE length=(SELECT MAX(length) FROM film);
20. SELECT COUNT(film_id) FROM film WHERE release_year=2010;
21. SELECT f.title FROM film f JOIN film_category fc ON f.film_id=fc.film_id JOIN category c ON c.category_id=fc.category_id WHERE c.name='Horror';
22. SELECT CONCAT(first_name,' ', last_name) AS full_name FROM staff WHERE staff_id=1;
23. SELECT * FROM film f JOIN film_actor fa ON f.film_id=fa.film_id JOIN actor a ON a.actor_id=fa.actor_id WHERE a.first_name='Fred' AND a.last_name='Costner';
24.
25. SELECT DISTINCT COUNT(country) FROM country;
  1. SELECT name FROM language ORDER BY name;
26. SELECT first_name, last_name FROM actor WHERE last_name LIKE '%son' ORDER BY first_name;
27. SELECT c.name,COUNT(f.film_id) FROM category c JOIN film_category fc ON c.category_id=fc.category_id JOIN film f ON f.film_id=fc.film_id GROUP BY c.name;
28. SELECT a.first_name,a.last_name, COUNT(f.film_id) FROM actor a JOIN film_actor fa ON a.actor_id=fa.actor_id JOIN film f ON f.film_id=fa.film_id GROUP BY a.first_name,a.last_name;
29. SELECT count(film_actor.actor_id), actor.first_name, actor.last_name  FROM actor INNER JOIN film_actor ON actor.actor_id = film_actor.actor_id GROUP BY film_actor.act
or_id ORDER BY count(film_actor.actor_id) DESC LIMIT 1;
