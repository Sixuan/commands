

Mysql
-----


* Dump database schema
```
mysqldump -u root -ptmppassword --no-data databaseName > /tmp/databaseName.sql
```
* Import database schema
```
use databaseName;
source /tmp/databaseName.sql;
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
* Count string occurances. -o will only output the matches, ignoring lines; wc can count them:
```
grep -o 'needle' file | wc -l
```

Elastic Search
--------------

* Check if an index exist
```
curl -XHEAD -i "ElasticSearch-host:9200/{index_name}"
```

* Create an index
```
curl -XPUT "ElasticSearch-host:9200/{index_name}"
```

* Check if a document is indexed
```
curl -XGET "ElasticSearch-host:9200/{index_name}/{type}/{id}"
```
