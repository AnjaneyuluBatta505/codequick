# Commands

mysql login<br>
$ mysql -u username -p

mysql dump
$ mysqldump -u [uname] -p[pass] db_name > db_backup.sql

mysql restore
$ mysql -u <user> -p < db_backup.dump

Postgres Restore command localhost

$ psql -U postgres -h <server-name>  database_name <  db_dump.sql

Postgres Database Dump Command

$ pg_dump -U postgres database_name > filename.sql

