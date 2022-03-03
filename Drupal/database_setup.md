# Drupal Database Setup

**Docs: [https://www.drupal.org/docs/installing-drupal/step-3-create-a-database](https://www.drupal.org/docs/installing-drupal/step-3-create-a-database)**

## MySQL

**See also [MySQL guide](../sql/mysql.md)**

### Create database

1. change 'username' and 'databasename'

```sh
mysql -u username -p -e "CREATE DATABASE databasename CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci";
```

2.log in

```sh
mysql -u username -p
```

3.create user and set permissions

```sql
CREATE USER username@localhost IDENTIFIED BY 'password';
```

- replace username and databasename with values set earlier

```sql
GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES ON databasename.* TO 'username'@'localhost' IDENTIFIED BY 'password';
```

4.flush privileges

```sql
FLUSH PRIVILEGES
```
