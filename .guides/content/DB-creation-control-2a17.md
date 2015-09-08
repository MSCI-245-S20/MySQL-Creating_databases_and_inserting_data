The `CREATE DATABASE db_name;` statement can be extended with some control keywords to check for databases that exist with the same name:

```
mysql> CREATE DATABASE IF NOT EXISTS db_name;
```

### Understading `IF NOT EXISTS`

If you try executing the above command replacing `db_name` with the `db_guitars_collection` name, the command will completely override your existing database: 

```
mysql> CREATE DATABASE IF NOT EXISTS db_guitars_collection;
# Query OK, 1 row affected, 1 warning (0.00 sec)
```

Where __the warning is that the database already existed__ but it still overrode it.

However, try executing the `CREATE DATABASE db_guitars_collection;` command without the `IF NOT EXISTS` control and you'll get an error:

```
mysql> CREATE DATABASE db_guitars_collection;
# ERROR 1007 (HY000): Can't create database 'db_guitars_collection'; database exists
```

---
SQL datatypes correspond to specific _character sets_ assigned when creating a SQL database. Learn more in the next section.