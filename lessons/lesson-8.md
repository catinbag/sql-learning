# Functions

DBMS oriented functions

### String

```sql
SELECT vend_name, UPPER(vend_name) AS vend_name_upper FROM vendors
```

### Datetime

```sql
SELECT RTRIM(vend_name) || ' (' || RTRIM(vend_country) || ')' FROM vendors
ORDER BY vend_name
```

### Numbers

```sql
SELECT SQRT(quantity) AS sqrt_quantity FROM orderitems
```
