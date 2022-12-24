# Insert data

### Complete row

**only values**

```sql
INSERT INTO customers
VALUES ('1000000006', 'Toy Land', '123 Any Street', 'New York', 'NY', ' 11111', 'USA', NULL, NULL)
```

**with columns**

```sql
INSERT INTO customers(cust_id,
                      cust_name,
                      cust_address,
                      cust_city,
                      cust_state,
                      cust_zip,
                      cust_country,
                      cust_contact,
                      cust_email)
VALUES ('1000000006', 'Toy Land', '123 Any Street', 'New York', 'NY', ' 11111', 'USA', NULL, NULL)
```

### Part of row

```sql
INSERT INTO customers(cust_id,
                      cust_name,
                      cust_address,
                      cust_city,
                      cust_state,
                      cust_zip,
                      cust_country)
VALUES ('1000000006', 'Toy Land', '123 Any Street', 'New York', 'NY', ' 11111', 'USA')
```

### Results

```sql
INSERT INTO Customers(cust_id,
                      cust_contact,
                      cust_email,
                      cust_name,
                      cust_address,
                      cust_city,
                      cust_state,
                      cust_zip,
                      cust_country)
SELECT cust_id,
       cust_contact,
       cust_email,
       cust_name,
       cust_address,
       cust_city,
       cust_state,
       cust_zip,
       cust_country
FROM custsnew;
```

### Copy

```sql
SELECT *
INTO custcopy
FROM customers
```
