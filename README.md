# Pantheon Tools
Basic shell scripts to make it easier to work with Pantheon.

## References
- https://pantheon.io/blog/importing-large-wordpress-sites-pantheon
- http://stackoverflow.com/questions/3268789/add-mysqldump-to-mamp-mysql-w-apache-php-on-macos-x

## Usage
- for MAMP, add '/Applications/MAMP/bin/php/php5.6.2/bin' to your $PATH

### db-dump
__Usage__
```
db-dump $DATABASE
db-dump example.com
```
__Returns__
```
$DATABASE-$DATETIME.sql
example.com-YYYYMMDD-HHMMSS.sql
```

### db-replace

**Usage**
```
db-replace $FILENAME $ENVIRONMENT $SEARCH $REPLACE
db-replace example.com-YYYYMMDD-HHMMSS.sql dev example.com.local:8888 dev.example.com
```
**Returns**
```
$ENVIRONMENT-$DATABASE-$DATETIME.sql
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
$DATETIME-$DATABASE-$ENVIRONMENT.sql
YYYYMMDD-HHMMSS-example.com-dev.sql
```
