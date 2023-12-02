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
