# Advanced data filtering

Combined WHERE

### AND

```sql
SELECT prod_id, prod_name, prod_price FROM products
WHERE vend_id = 'BRS01' AND prod_price > 4
```

### OR

```sql
SELECT prod_id, prod_name, prod_price FROM products
WHERE vend_id = 'BRS01' OR prod_price > 4
```

### AND + OR

```sql
SELECT prod_id, prod_name, prod_price FROM products
WHERE (vend_id = 'DLL01' OR vend_id = 'BRS01') AND prod_price >= 10
```

### IN

```sql
SELECT vend_id, prod_name, prod_price FROM products
WHERE vend_id IN ('DLL01', 'BRS01')
ORDER BY prod_name
```

### NOT

```sql
SELECT prod_name FROM products
WHERE NOT vend_id = 'DLL01'
ORDER BY prod_name
```
