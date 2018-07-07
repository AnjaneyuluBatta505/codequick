* set auto increment value of a table column
```sql
SELECT setval('<table_name>_<auto_inc_column_name>', (SELECT max(id) FROM <table_name>));
```
* restore a single table from a database dump
```sql
pg_restore -h <hostname> -U <user_name> -d <database_name> -t <table_name>  <database_dump_file>
```
