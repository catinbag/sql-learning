# Views

### Create

```sql
CREATE VIEW ProductCustomers AS
SELECT cust_name, cust_contact, prod_id
FROM customers,
     orders,
     orderitems
WHERE customers.cust_id = orders.cust_id
  AND orderitems.order_num = orders.order_num
```

```sql
CREATE VIEW VendorLocations AS
SELECT vend_name || ' (' || vendors.vend_country || ')' AS vend_title
FROM vendors
```

```sql
CREATE VIEW CustomerEmailList AS
SELECT cust_id, cust_name, cust_email
FROM Customers
WHERE cust_email IS NOT NULL;
```

```sql
CREATE VIEW OrderItemsExpanded AS
SELECT order_num, prod_id, quantity, item_price, quantity * item_price AS expanded_price
FROM orderitems
```

### Use

```sql
SELECT cust_name, cust_contact
FROM productcustomers
WHERE prod_id = 'RGAN01'
```

```sql
SELECT *
FROM vendorlocations
```

```sql
SELECT *
FROM customeremaillist
```

```sql
SELECT *
FROM orderitemsexpanded
WHERE order_num = 20008;
```

### Delete
