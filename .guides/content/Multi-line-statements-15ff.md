In the previous section, we entered this code: 

```
CREATE DATABASE IF NOT EXISTS guitars_collection;

CREATE TABLE catalog ( 
	id INT(8) UNSIGNED NOT NULL auto_increment,
	name VARCHAR(255) default NULL,
	manufacture_year YEAR(4) default NULL,
	brand VARCHAR(255) default NULL,
	PRIMARY KEY (id)
) AUTO_INCREMENT=1;
```

Into the `guitars-catalog.sql` file and `source`_d_ it for efficiency reasons.

However, it is possible to write the same code directly in the command line using __multi-line statements__.

|||info
### Using multi-line statements

Whenever you press the _return key_ in the `mysql>` command line __without a trailing semicolon `;`__, a new `->` prompt is created. 

This `->` prompt indicates that you can keep entering SQL keywords until you end the statement with a `;`. 

Let's illustrate multi-line statements usage by exemplifying the `CREATE TABLE` example above as you would write it in the command line:

```
mysql> CREATE TABLE catalog (
    -> id INT(8) UNSIGNED NOT NULL auto_increment,
    -> name VARCHAR(255) default NULL,
    -> manufacture_year YEAR(4) default NULL,
    -> brand VARCHAR(255) default NULL,
    -> PRIMARY KEY (id)
    -> ) AUTO_INCREMENT=1;
```
While you can do this, it makes a million times more sense to edit a file, source it, and if you made a mistake, fix the file.  If you type in long statements and queries into the mysql command line, and you make a mistake, you have to type everything again.  Except for simple queries, get in the habit of putting your queries into a file that you source.

|||

---
Let's expose the `catalog` table column names and dataypes in the next section.