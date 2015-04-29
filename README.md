# Pantheon Tools
Basic shell scripts to make it easier to work with Pantheon.

## Configuration
Create a .cnf file for each environment
- test.cnf
- dev.cnf
- local.cnf
```
[client]
user='root'
password='root'
host='localhost'
port='3306'
verbose
```

## Usage

### db-dump

**Usage**
```
db-dump $DATABASE
db-dump example.com
```
**Returns**
```
$DATABASE-$DATETIME.sql
example.com-YYYYMMDD-HHMMSS.sql
```

### db-replace

**Usage**
```
db-replace $ENVIRONMENT $SEARCH $REPLACE $FILE
db-replace dev example.com.local:8888 dev.example.com example.com-YYYYMMDD-HHMMSS.sql
```
**Returns**
```
$ENVIRONMENT-$FILE
dev-example.com-YYYYMMDD-HHMMSS.sql
```

### db-dump-replace

**Usage**
```
db-dump-replace $DATABASE $ENVIRONMENT $SEARCH $REPLACE
db-dump-replace example.com dev example.com.local:8888 dev.example.com
```
**Returns**
```
$DATABASE-$DATETIME.sql
example.com-YYYYMMDD-HHMMSS.sql

$ENVIRONMENT-$DATABASE-$DATETIME.sql
dev-example.com-YYYYMMDD-HHMMSS.sql
```

### db-pull

**Usage**
```
db-push $ENVIRONMENT $FILENAME
db-push dev dev-example.com
```
**Returns**
```
$ENVIRONMENT-$FILENAME-$DATETIME.sql
dev-example.com-YYYYMMDD-HHMMSS.sql
```

### db-pull-replace

**Usage**
```
db-pull-replace $ENVIRONMENT $FILENAME $SEARCH $REPLACE
db-pull-replace dev example.com dev.example.com example.com.local:8888
```
**Returns**
```
$ENVIRONMENT-$FILENAME-$DATETIME.sql
dev-example.com-YYYYMMDD-HHMMSS.sql

$FILENAME-$DATETIME.sql
example.com-YYYYMMDD-HHMMSS.sql
```

### db-push

**Usage**
```
db-push $ENVIRONMENT $FILE
db-push dev dev-example.com-YYYYMMDD-HHMMSS.sql
```
**Returns**
```
Success/Failure
```

### uploads-rsync

**Usage**
```
uploads-rsync $ENVIRONMENT $DIRECTION $UUID
uploads-rsync dev upload 00000000-0000-0000-0000-000000000000
```
**Returns**
```
Success/Failure
```

## MAMP
Make sure MAMP is in your $PATH - '/Applications/MAMP/bin/php/php5.6.2/bin'

## References
- https://pantheon.io/blog/importing-large-wordpress-sites-pantheon
- http://stackoverflow.com/questions/3268789/add-mysqldump-to-mamp-mysql-w-apache-php-on-macos-x
