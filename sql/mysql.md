# mysql

## Installation

- using homebrew:

```sh
brew install mysql
```

## Running the server

1. Daemon mode: runs until specifically stopped

```sh
brew services start mysql
```

```sh
brew services stop mysql
```

2. Manual: stop/start mysql server a required, rebooting the machine will stop the server and not restart it


```sh
mysql.server start
```

```sh
mysql.server stop
```

## Connect to the server

```sh
mysql -u root -p
```
