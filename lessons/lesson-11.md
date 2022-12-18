# Subqueries

### Separate sequential quieries

```sql
SELECT order_num FROM orderitems
WHERE prod_id = 'RGAN01'
```

```sql
SELECT cust_id FROM orders
WHERE order_num IN (20007,20008)
```

```sql
SELECT cust_name FROM customers
WHERE cust_id IN ('1000000004','1000000005')
```

### Subquiery

Only ONE column

```sql
SELECT cust_id FROM orders
WHERE order_num IN (
    SELECT order_num FROM orderitems
    WHERE prod_id = 'RGAN01'
)
```

```sql
SELECT cust_name FROM customers
WHERE cust_id IN (
    SELECT cust_id FROM orders
    WHERE order_num IN (SELECT order_num FROM orderitems
        WHERE prod_id = 'RGAN01'
    )
)
```

### Subquiery as computed field

```sql
SELECT cust_name, cust_state, (
    SELECT COUNT(*) FROM orders
    WHERE orders.cust_id  = customers.cust_id
) AS orders
FROM customers
ORDER BY cust_name
```
