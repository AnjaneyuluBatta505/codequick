# Commands<br>

mysql login<br>
``` {r, engine='bash', count_lines}
$ mysql -u username -p
```


mysql dump<br>
``` {r, engine='bash', count_lines}
$ mysqldump -u [uname] -p[pass] db_name > db_backup.sql
```

mysql restore<br>
```{r, engine='bash', count_lines}
$ mysql -u <user> -p < db_backup.dump
```

Login to postgres<br>
```{r, engine='bash', count_lines}
$ sudo -u postgres psql postgres 
```

Postgres Restore command localhost<br>
```{r, engine='bash', count_lines}
$ psql -U postgres -h <server-name>  database_name <  db_dump.sql
```
Postgres Database Dump Command<br>
```{r, engine='bash', count_lines}
$ pg_dump -h localhost -U postgres database_name > filename.sql
```

Restore Local database to Heroku <br>
```{r, engine='bash', count_lines}
$ heroku pg:psql --app cinema-wiki < latest.dump
```
