# Create advanced joins

### Old syntax

```sql
SELECT RTRIM(vend_name) || ' (' || RTRIM(vend_country) || ')' AS vend_title
FROM vendors
ORDER BY vend_name
```

### FROM aliases

```sql
SELECT cust_name, cust_contact
FROM customers AS c, orders AS o, orderitems AS oi
WHERE c.cust_id = o.cust_id AND oi.order_num = o.order_num AND prod_id = 'RGAN01'
```

### SELF JOIN

**subquery**

```sql
SELECT cust_id, cust_name, cust_contact
FROM customers
WHERE cust_name = (
    SELECT cust_name
    FROM customers
    WHERE cust_contact = 'Jim Jones'
)
```

**aliases**

```sql
SELECT c1.cust_id, c1.cust_name, c1.cust_contact
FROM customers AS c1, customers AS c2
WHERE c1.cust_name = c2.cust_name AND c2.cust_contact = 'Jim Jones'
```

### NATURAL JOIN

```sql
SELECT c.*, o.order_num, order_date, oi.prod_id, oi.quantity, oi.item_price
FROM customers AS c, orders AS o, orderitems AS oi
WHERE c.cust_id = o.cust_id AND oi.order_num = o.order_num AND prod_id = 'RGAN01'
```

### OUTER JOIN

**inner**

```sql
SELECT customers.cust_id, orders.order_num
FROM customers INNER JOIN orders ON customers.cust_id = orders.cust_id
```

**left outer**

```sql
SELECT customers.cust_id, orders.order_num
FROM customers LEFT OUTER JOIN orders ON customers.cust_id = orders.cust_id
```

**right outer**

```sql
SELECT customers.cust_id, orders.order_num
FROM customers RIGHT OUTER JOIN orders ON orders.cust_id = customers.cust_id
```

**full**

```sql
SELECT customers.cust_id, orders.order_num
FROM orders FULL OUTER JOIN customers ON orders.cust_id = customers.cust_id
```

### Use with total functions

```sql
SELECT customers.cust_id, COUNT(orders.order_num) AS num_ord
FROM customers INNER JOIN orders ON customers.cust_id = orders.cust_id
GROUP BY customers.cust_id
```

```sql
SELECT customers.cust_id, COUNT(orders.order_num) AS num_ord
FROM customers LEFT OUTER JOIN orders ON customers.cust_id = orders.cust_id
GROUP BY customers.cust_id
```
