# Grouping data

### GROUP_BY

```sql
SELECT vend_id, COUNT(*) AS counts FROM products
GROUP BY vend_id
```

### HAVING

```sql
SELECT cust_id, COUNT(*) AS orders FROM orders
GROUP BY cust_id
HAVING COUNT(*) >= 2
```

```sql
SELECT vend_id, COUNT(*) AS num_prodcuts FROM products
WHERE prod_price >= 4
GROUP BY vend_id
HAVING COUNT(*) >= 2
```

### ORDER_BY

```sql
SELECT order_num, COUNT(*) AS num_items FROM orderitems
GROUP BY order_num
HAVING COUNT(*) >= 2
ORDER BY num_items, order_num
```

### MIN

```sql
SELECT MIN(prod_price) AS max_price FROM products
```

### SUM

```sql
SELECT SUM(prod_price) AS sum_price FROM products
```

### DISTINCT

Don't use with COUNT(\*)

```sql
SELECT AVG(DISTINCT prod_price) AS avg_uniq_price FROM products
```

### Combine

```sql
SELECT MIN(prod_price) AS min_price, AVG(prod_price) AS max_price FROM products
```
