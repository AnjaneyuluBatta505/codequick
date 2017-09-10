# Commands<br>
Install postgres database ubuntu
```
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib
```

Install python pip on Ubuntu
```
$ sudo apt-get install python-pip python-dev build-essential 
$ sudo pip install --upgrade pip 
$ sudo pip install --upgrade virtualenv
```

Python3 virtualenv<br>
``` {r, engine='bash', count_lines}
$ virtualenv -p python3 env
```



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
$ heroku pg:psql --app appname < latest.dump
```

List All open ports in linux
```{r, engine='bash', count_lines}
$ netstat -tulpn
```
List Process name with given port 
```{r, engine='bash', count_lines}
sudo ss -lptn 'sport = :8080'
```

Find a pattern in a directory recursively
```{r, engine='bash', count_lines}
grep -nr 'pattern to find ' dir_name/
```
