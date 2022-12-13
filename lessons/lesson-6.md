# Metasymbol filtering

Metasymbols, search, LIKE

### Meta %

Any character any number of times

**start**

```sql
SELECT prod_id, prod_name FROM products
WHERE prod_name LIKE 'Fish%'
```

**middle**

```sql
SELECT prod_id, prod_name FROM products
WHERE prod_name LIKE '%bean bag%'
```

**end**

```sql
SELECT prod_id, prod_name FROM products
WHERE prod_name LIKE '%toy%'
```

### Meta \_

Any character one time

```sql
SELECT prod_id, prod_name FROM products
WHERE prod_name LIKE '__ inch%'
```

### Meta []

Set of symbols

```sql
SELECT cust_contact FROM customers
WHERE cust_contact LIKE '[JM]%'
```
