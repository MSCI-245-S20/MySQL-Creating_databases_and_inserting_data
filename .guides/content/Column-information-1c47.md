Now that our `catalog` table is created, let's follow some steps in order to confirm that the table exists with the datatype configuration we determined: 

First, use the `guitars_collection` database:

```
mysql> USE guitars_collection;
```

Second, display the `guitars_collection` tables: 

```
mysql> SHOW TABLES;
```

Third, show the `catalog` table columns' information: 

```
mysql> SHOW COLUMNS FROM catalog;
```

And you should see this:

```
+------------------+--------------+------+-----+---------+----------------+
| Field            | Type         | Null | Key | Default | Extra          |
+------------------+--------------+------+-----+---------+----------------+
| id               | int(8)       | NO   | PRI | NULL    | auto_increment |
| name             | varchar(255) | YES  |     | NULL    |                |
| manufacture_year | year(4)      | YES  |     | NULL    |                |
| brand            | varchar(255) | YES  |     | NULL    |                |
+------------------+--------------+------+-----+---------+----------------+
4 rows in set (0.02 sec)
```
An alternative is to ask the database to describe the table:
```
mysql> DESCRIBE catalog ;
```
Note: even if you are not currently `USE`ing a database, you can directly refer to tables inside of a database.  For example:
```
mysql> SHOW COLUMNS FROM guitars_collection.catalog;
```
