1. set auto increment value of a table column
```sql
SELECT setval('<table_name>_<auto_inc_column_name>', (SELECT max(id) FROM <table_name>));
```
