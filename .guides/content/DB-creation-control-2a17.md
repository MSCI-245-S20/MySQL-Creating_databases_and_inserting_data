The `CREATE DATABASE db_name;` statement can be extended with some control keywords to check for databases that exist with the same name:

```
mysql> CREATE DATABASE IF NOT EXISTS db_name;
```
If you try executing the above command replacing `db_name` with the `guitars_collection` name:
```
mysql> CREATE DATABASE IF NOT EXISTS guitars_collection;
```
You should see this: 
```
Query OK, 0 rows affected, 1 warning (0.000 sec)
```
Which tells you that everything is fine with your query, it worked, but there is a warning for you to read.  To read the warning, do:
```
mysql> SHOW warnings ;
```
and you should see:
```
+-------+------+-------------------------------------------------------------+
| Level | Code | Message                                                     |
+-------+------+-------------------------------------------------------------+
| Note  | 1007 | Can't create database 'guitars_collection'; database exists |
+-------+------+-------------------------------------------------------------+
1 row in set (0.000 sec)
```
If instead you executed `CREATE DATABASE guitars_collection;` without the `IF NOT EXISTS`, you'll get an error:
```
ERROR 1007 (HY000): Can't create database 'guitars_collection'; database exists
```
When you write SQL scripts or place SQL code in a file to be sourced, and you want to make sure a database exists, but you are fine if it already exists, then use `IF NOT EXISTS` for this will allow your code to run with only a warning.

On the other hand, if you want to make sure that the database doesn't already exist when you attempt to create it, do not use the `IF NOT EXISTS` so that you get an error.  

---
Complete a challenge in the next section.