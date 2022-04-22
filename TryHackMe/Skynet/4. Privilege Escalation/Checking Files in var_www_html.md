## Checking Files in var/www/html

```
<ra24zxs28v3yd/administrator$ cat Configuration.php           
<?php 
        class Configuration{
                public $host = "localhost";
                public $db = "cuppa";
                public $user = "root";
                public $password = "password123";
                public $table_prefix = "cu_";
                public $administrator_template = "default";
                public $list_limit = 25;
                public $token = "OBqIPqlFWf3X";
                public $allowed_extensions = "*.bmp; *.csv; *.doc; *.gif; *.ico; *.jpg; *.jpeg; *.odg; *.odp; *.ods; *.odt; *.pdf; *.png; *.ppt; *.swf; *.txt; *.xcf; *.xls; *.docx; *.xlsx";
                public $upload_default_path = "media/uploadsFiles";
                public $maximum_file_size = "5242880";
                public $secure_login = 0;
                public $secure_login_value = "";
                public $secure_login_redirect = "";
        }
``` 

* looks like we have a DB username and password - `root:password123`
* logging into mysql with credentials

```
<ml/45kra24zxs28v3yd/administrator$ mysql -u root -p                          -
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 12
Server version: 5.7.27-0ubuntu0.16.04.1 (Ubuntu)

Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
``` 

## Enumerating MySQL
* checking databases
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| cuppa              |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.01 sec)

mysql> use cuppa
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
```

* checking tables
mysql> show tables;
```
+--------------------------+
| Tables_in_cuppa          |
+--------------------------+
| cu_articles              |
| cu_categories            |
| cu_menu_item_type        |
| cu_menu_items            |
| cu_menu_items_extra_data |
| cu_menus                 |
| cu_permissions           |
| cu_tables                |
| cu_user_groups           |
| cu_users                 |
+--------------------------+
10 rows in set (0.00 sec)
```

* let's check cu_users

```
mysql> select * from cu_users;
+----+---------------+----------------------+----------+----------------------------------+---------+---------------+
| id | name          | email                | username | password                         | enabled | user_group_id |
+----+---------------+----------------------+----------+----------------------------------+---------+---------------+
|  1 | Administrator | skynet@tryhackme.com | admin    | b686468aec2c71e1783375763dca9b7e |       1 |             1 |
+----+---------------+----------------------+----------+----------------------------------+---------+---------------+
1 row in set (0.00 sec)
```

* we have an email and a password hash
* let's run this through `john`
* run into deadend here
