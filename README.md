

Mysql
-----


* Dump database schema
```
mysqldump --no-data databaseName > /tmp/
```
* Import database schema
```
use DATABASE_NAME;
source path/to/file.sql;
```

Command line
------------

* Download file from remote server
```
scp sliu@expample.com:/tmp/file.txt /home/sliu/
```
* Upload file to remote server by ssh

```
sudo scp -i ~/.ssh/sshKeyFile /home/sliu/Downloads/mysql-connector-java-5.1.38.jar ubuntu@api.exaple.com:/tmp
```
