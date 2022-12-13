# Computed fields

Computed fields, links to fields

### Formatting

```sql
SELECT vend_name || ' (' || vend_country || ')', vend_name FROM vendors
ORDER BY vend_name
```

```sql
SELECT RTRIM(vend_name) || ' (' || RTRIM(vend_country) || ')' FROM vendors
ORDER BY vend_name
```

### Pseudonyms

```sql
SELECT vend_name || ' (' || vend_country || ')' AS vend_title FROM vendors
ORDER BY vend_name
```

```sql
SELECT vend_name AS vend_custom_name FROM vendors
ORDER BY vend_name
```

### Math

```sql
SELECT prod_id, quantity, item_price, quantity * item_price AS full_price FROM orderitems
WHERE order_num = 20008
```
