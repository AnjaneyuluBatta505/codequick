# PostgreSQL Quick Reference
## set auto increment value of a table column
```sql
SELECT setval('<table_name>_<auto_inc_column_name>', (SELECT max(id) FROM <table_name>));
# example
SELECT setval('committees_id_seq', (SELECT max(id) FROM committees));
```
## restore a single table from a database dump
```sql
pg_restore -h <hostname> -U <user_name> -d <database_name> -t <table_name>  <database_dump_file>
```
## dump database from postgres server

```sql
pg_dump -v -U <username> -h <host> <db name> > <file_name.dump>
```

## copy data from table1 to table2
```sql
INSERT INTO table2(col1, col2) select col1, col2 from table1;
```
## rename database

```
ALTER DATABASE <db name> RENAME TO <new db name>;
```

## find size of the database

```sql
SELECT pg_size_pretty(pg_database_size('{database name}'));
```

## postgres version

```sql
select version();
```

## find table size
```sql
SELECT pg_size_pretty( pg_total_relation_size('tablename') );
```

## list all tables in a specific schema

```sql
select tablename from pg_tables where schemaname='public';
```

## drop not null of a column
```sql
ALTER TABLE django_content_type ALTER COLUMN name DROP NOT NULL;
```

### type casting
```sql
ALTER TABLE table ALTER COLUMN "mycolumn" TYPE numeric using value::numeric;
```

## create user and give all previliges on the database
```sql
create user myuser with encrypted password 'secret';
grant all privileges on database mydatabase to myuser;
```
