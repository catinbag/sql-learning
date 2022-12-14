# Final computings

Final SQL functions

Ignore NULL values

### AVG

```sql
SELECT AVG(prod_price) AS avg_price FROM products
WHERE vend_id = 'DLL01'
```

### COUNT

```sql
SELECT COUNT(*) AS count FROM products
WHERE vend_id = 'DLL01'
```

```sql
SELECT COUNT(cust_email) AS count_emails FROM customers
```

### MAX

```sql
SELECT MAX(prod_price) AS max_price FROM products
WHERE vend_id = 'DLL01'
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
