# qa_sql_exercises
qa_sql_exercises

![image](https://user-images.githubusercontent.com/48223215/150165149-01903fab-5900-477a-825a-2b9bc8da293e.png)


update 1 users:

update users
set address = 'harry hill'
where customer_id = 1

update2: users

update users
set last_name = 'Cena'
where first_name = 'John'


update 1 orders:

update orders
set order_date = '2021-01-11 14:23:11'
where order_id = 6

update 2 orders:

update orders
set shipped_date = '2021-01-14 10:54:43'
where order_id = 6

update products 1:

update products
set price = 10
where product_name = 'remote control car'

update products 2:

update products
set product_name = 'pan'
where product_id = 4

update orderline 1:

update orderline
set fk_order_id = 10
where fk_product_id = 2

update orderline 2:

update orderline
set fk_order_id = 9
where fk_product_id = 3

10 querys

1.SELECT * FROM products WHERE product_name = 'tv'

2.SELECT * FROM products WHERE price > 50

3.SELECT * FROM products order by price DESC

4.SELECT * FROM products order by price ASC limit 3

5.
SELECT *
from orderline ol
join products p on ol.fk_product_id=p.product_id

6.
SELECT *
from orderline ol
join products p on ol.fk_product_id=p.product_id
join orders o on ol.fk_order_id=o.order_id

7.
SELECT product_name, category, order_date, shipped_date, order_status
from orderline ol
join products p on ol.fk_product_id=p.product_id
join orders o on ol.fk_order_id=o.order_id

8.
SELECT product_name, category, order_date, shipped_date, order_status
from orderline ol
join products p on ol.fk_product_id=p.product_id
join orders o on ol.fk_order_id=o.order_id
WHERE o.order_status = 'delivered'

9.
SELECT product_name, category, price
from orderline ol
join products p on ol.fk_product_id=p.product_id
join orders o on ol.fk_order_id=o.order_id
WHERE p.category = 'tv & computers' and o.order_status = 'delivered'
order by p.price DESC

10.
SELECT category, COUNT(category) as numOfProductsInCat 
FROM products
group by products.category
order by numOfProductsInCat DESC

deleting entries from table:

orderline table:
SELECT * FROM orderline;

product table:
DELETE FROM products WHERE product_name = 'pan'

orders table:
DELETE FROM orders WHERE order_id = 8

users table:
DELETE FROM users WHERE email = 'gretaboogie@email.com'



SAKILA CHALLENGE
1. SELECT first_name, last_name FROM actor

2. SELECT * FROM actor WHERE first_name = 'John'

3. SELECT * FROM actor WHERE last_name = 'Neeson'

4. SELECT first_name, last_name, actor_id FROM actor WHERE actor_id/10 = floor(actor_id/10)

5. SELECT description FROM film WHERE film_id = 100;

6. SELECT * FROM film WHERE rating = 'R';

7. SELECT * FROM film WHERE rating != 'R';

8. SELECT * FROM film order by length ASC limit 10;

9. SELECT * FROM film order by length DESC

10. SELECT * FROM film WHERE special_features LIKE '%Deleted Scenes%';

11. SELECT distinct(last_name) FROM actor ORDER BY last_name DESC;

12. 
SELECT last_name, count(last_name) as numOfActorsLastName
FROM actor 
group by last_name
having numOfActorsLastName > 1
order by numOfActorsLastName desc

13. 
SELECT first_name, last_name, count(a.actor_id) as numOfFilms
FROM actor a
join film_actor fa on a.actor_id=fa.actor_id
group by fa.actor_id
order by numOfFilms desc limit 1

14.

15.SELECT avg(length) FROM film

16.
SELECT c.name, avg(f.length) as avgRuntime
FROM film_category fc
join film f on fc.film_id=f.film_id
join category c on fc.category_id=c.category_id  
group by name

17. SELECT * FROM film WHERE description LIKE '%ROBOT%';

18. SELECT count(release_year) FROM film WHERE release_year = 2010;

19. 
SELECT f.title, c.name
FROM film_category fc
join film f on fc.film_id=f.film_id
join category c on fc.category_id=c.category_id  
where c.name = 'Horror'

20. SELECT first_name, last_name FROM staff where staff_id = 2

21. 
SELECT first_name, last_name, title
FROM actor a
join film_actor fa on a.actor_id=fa.actor_id
join film f on fa.film_id=f.film_id
where first_name = 'Fred' and last_name = 'Costner';

22.SELECT count(DISTINCT(COUNTRY)) as uniqueCountries FROM country

23. SELECT name FROM language order by name DESC

24. SELECT first_name, last_name FROM actor where last_name like '%son' order by first_name ASC

25. 
SELECT name, count(name) as categoryCount
FROM film_category fc
join category c on fc.category_id=c.category_id
group by name 
order by categoryCount DESC

