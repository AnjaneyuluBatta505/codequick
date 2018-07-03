1. set auto increment value of a table column
```sql
SELECT setval('your_sequence_name', (SELECT max(id) FROM your_table));
```
