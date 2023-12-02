# How-To-Reset-MariaDB-Mysql-root-Password
How To Reset My MariaDB / Mysql root password

## Step 1 — Identifying the Database Version and Stopping the Server

```
mysql --version
```
Output Should Like Below
```
mysql  Ver 15.1 Distrib 10.3.25-MariaDB, for debian-linux-gnu (x86_64) using readline 5.2
```
then stop mariadb services
```
sudo systemctl stop mariadb
```
Run Below command to run mysql /mariadb in safe mode
```
mysqld_safe --skip-grant-tables --skip-networking
```
Reload the systemd configuration to apply these changes:
```
sudo systemctl daemon-reload
```
Now start the MySQL server:
```
sudo systemctl start mysql
```

Connect to the database as the root user:
```
sudo mysql -u root
```
Tell the database server to reload the grant tables by issuing the FLUSH PRIVILEGES command:

```
FLUSH PRIVILEGES;
```
If you are using MariaDB, execute the following statement to set the password for the root account, making sure to replace new_password with a strong new password that you’ll remember:

```
ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password';
```
You’ll see this output indicating that the password changed:

```
Output
Query OK, 0 rows affected (0.001 sec)
```

exit mysql and kill the process of mysqld_safe

the start mariadb/mysql

```
sudo systemctl start mysql
```
