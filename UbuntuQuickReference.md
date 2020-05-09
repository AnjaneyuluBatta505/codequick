# Ubuntu Quick Reference
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
# or 

create backup
pg_dump -i -h localhost -p 5432 -U postgres -F c -b -v -f 
"/usr/local/backup/10.70.0.61.backup" old_db
restore from backup

pg_restore -i -h localhost -p 5432 -U postgres -d old_db -v 
"/usr/local/backup/10.70.0.61.backup"
important to set -h localhost - option

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
sudo ss -ltpn 'sport = :8080'
```

Find a pattern in a directory recursively
```{r, engine='bash', count_lines}
grep -nr 'pattern to find ' dir_name/
```
kill a process on a port on ubuntu port 9001
```{r, engine='bash', count_lines}
sudo kill -9 $(sudo lsof -t -i:9001)
# or
sudo fuser -n tcp -k 9001 

```
Kill all process of uwsgi
```{r, engine='bash', count_lines}
kill `pidof uwsgi`
```
restart supervisor
```{r, engine='bash', count_lines}
service supervisor restart
# or
systemctl restart supervisor
```
supervisor uwsgi: ERROR (spawn error)
```{r, engine='bash', count_lines}
sudo supervisorctl reload
sudo supervisorctl update
supervisorctl start all
```
usage of `rsync`</br>
copy file from local machine to server
```{r, engine='bash', count_lines}
rsync -avz -e "ssh -i /path/to/key.pem" /path/to/file.txt  <username>@<ip/domain>:/path/to/directory/
```
copy file from server to local machine
```{r, engine='bash', count_lines}
rsync -avz -e "ssh -i /path/to/key.pem" <username>@<ip/domain>:/path/to/directory/file.txt  /path/to/directory/
```
rsync flags
```{r, engine='bash', count_lines}
--ignore-existing  # skips the files if file with the name already exists
--update           # updates files based on modification date
--dry-run          # to see the test changes
```


## ubuntu screen recording and audio, video editing softwares

```
sudo apt-get install kazam audacity avidmux
sudo apt-get install pulseaudio-equalizer
```
