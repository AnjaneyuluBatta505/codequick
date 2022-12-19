
# MySQL - Database

## safe updates

```sql
SET SQL_SAFE_UPDATES = 0;
SET SQL_SAFE_UPDATES = 1;
```

## set table auto-increment value

```sql
ALTER TABLE <table name> AUTO_INCREMENT = <number>
-- ALTER TABLE db.table AUTO_INCREMENT = 4
```

## select current auto increment value of a table

```sql
SELECT IDENT_CURRENT('table_name');
```
