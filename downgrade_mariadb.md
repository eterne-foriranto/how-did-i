Assuming, we've already downgraded `mariadb*` packages.
And we are faced with something like `ERROR: 1347 'mysql.user' is not of type 'BASE TABLE'` when running installation script.
Then one should change the file `/etc/mysql/my.cnf`:

Put the line `skip-grant-tables` to the section `[mysqld]`.
The \[re\]start mysqld and enter the mysql command prompt.

```

mysql> drop database mysql;

```

Remove the line `skip-grant-tables` from the section `[mysqld]`.

Restart mysqld.

Reissue installation script.


Stages may be shuffled.
