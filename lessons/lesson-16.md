# Updating and deleting data

### UPDATE

**one column**

```sql
UPDATE custcopy
SET cust_email = 'newemail@gmail.com'
WHERE cust_id = '1000000002'
```

**many columns**

```sql
UPDATE custcopy
SET cust_email = 'newemail@gmail.com', cust_contact = 'new cust contact'
WHERE cust_id = '1000000002'
```

**delete value**

```sql
UPDATE custcopy
SET cust_email = NULL
WHERE cust_id = '1000000002'
```

### DELETE

**by condition**

```sql
DELETE FROM custcopy
WHERE cust_id = '1000000002'
```

**full**

```sql
TRUNCATE TABLE custcopy
```
