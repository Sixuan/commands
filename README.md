

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
* Check top table size, index size in database.
```
SELECT concat(table_schema,'.',table_name) tables, concat(round(table_rows/1000000,2),'M') rows, concat(round(data_length/(1024*1024*1024),2),'G') data_size, concat(round(index_length/(1024*1024*1024),2),'G') index_size, concat(round((data_length+index_length)/(1024*1024*1024),2),'G') total_size, round(index_length/data_length,2) index_data_ratio FROM information_schema.TABLES ORDER BY total_size DESC LIMIT 20;

```
* Show if db's innodb_file_per_table on/off.
```
show variables like 'innodb_file_per_table';
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
