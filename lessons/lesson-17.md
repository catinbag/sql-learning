# Tables actions

### Create

```sql
CREATE TABLE Users
(
    user_id    CHAR(10)      NOT NULL,
    user_name  CHAR(10)      NOT NULL,
    user_age   DECIMAL(254)  NOT NULL,
    user_color CHAR(10)      NOT NULL DEFAULT 'black',
    user_desc  VARCHAR(1000) NULL
);
```

### Update

**add column**

```sql
ALTER TABLE users
ADD user_phone CHAR(20)
```

**remove column**

```sql
ALTER TABLE users
DROP COLUMN user_phone
```

### Delete

```sql
DROP TABLE users
```
