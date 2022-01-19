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
