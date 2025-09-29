<a id="mysql-optimization"></a>

# MySQL Optimization

This article contains descriptions of some known issues and recipes that might help to get the best application performance.

<a id="mysql-hdd-sdd"></a>

## How To Avoid Performance Issues When MySQL Data is Stored on HDD

It is recommended to use SSD to store the data in the MySQL 8.X database. However, if you do need to use the HDD, follow
the steps described in the <a href="https://dev.mysql.com/doc/refman/5.7/en/optimizing-innodb-diskio.html" target="_blank">optimizing InnoDB Disk I/O</a> article to avoid
performance issues and set the following configuration parameters in the **/etc/my.cnf** file:

```none
[mysqld]
innodb_file_per_table = 0
wait_timeout = 28800
```

<a id="mysql-optimizer"></a>

## How To Avoid Performance Issues with MySQL optimizer

To minimize the risk of long compilations of SQL queries (which sometimes may take hours or even days;
for details, see [MySQL documentation](https://dev.mysql.com/doc/refman/5.6/en/controlling-query-plan-evaluation.html)),
set optimizer_search_depth to 0:

```none
[mysqld]
optimizer_search_depth = 0
```

<a id="utf8mb4-mysql"></a>

## Usage of The utf8mb4 Character Set (The Full 4-Byte UTF-8 Unicode Encoding) in MySQL

To store supplementary characters (such as 4-byte emojis), configure the options file to use the utf8mb4
character set. Put the following configuration settings in your options file **/etc/my.cnf**:

```none
[client]
default-character-set = utf8mb4

[mysql]
default-character-set = utf8mb4

[mysqld]
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci
```

MySQL also can load default options from another file (not  */etc/my.cnf*). In such cases, you have to put the
configuration settings in this file. To find out which configuration files your MySQL server uses, run the
following command:

```none
$ mysqld --help --verbose 2> /dev/null | grep -A1 'Default options'
```

You will get the output with MySQL config files names similar to this:

```none
Default options are read from the following files in the given order:
/etc/my.cnf /etc/mysql/my.cnf /usr/local/etc/my.cnf ~/.my.cnf
```

#### NOTE
You also can set up the character set and the collation on <a href="https://dev.mysql.com/doc/refman/5.5/en/charset-syntax.html" target="_blank">the other levels</a> as well.

You can find more information on MySQL configuration in the <a href="https://dev.mysql.com/doc/refman/5.7/en/charset-unicode.html" target="_blank">Unicode Support</a> and <a href="https://dev.mysql.com/doc/refman/5.7/en/innodb-file-format.html" target="_blank">InnoDB File-Format Management</a> articles.

You can also change the defaults for Doctrine so that the generated SQL uses the correct character set. To achieve this,
put the following configuration into the **config/config.yml** file:

```none
doctrine:
    dbal:
        charset: utf8mb4
        default_table_options:
            charset: utf8mb4
            collate: utf8mb4_unicode_ci
```

#### NOTE
If you use a version of MySQL that is older than 5.7, also add the row_format: DYNAMIC option to the
default_table_options section.

Please see the <a href="https://symfony.com/doc/5.4/doctrine.html#configuring-the-database" target="_blank">Setting up the Database to be UTF8</a> article for more details.

## Block Nested Loop (BNL) in MySQL 5.6 and later

MySQL 5.6 has a lot of improvements in the query optimizer, but unfortunately, some queries work significantly
slower than in MySQL 5.5. In case of large amounts of data in the database, it is possible to encounter performance issues
related to the new query optimizer. One of the possible solutions might be disabling the `block_nested_loop` option.
This can be achieved in two ways:

> - If a modification of the MySQL configuration file is granted, add the following under the `mysqld` section
>   ```cfg
>   [mysqld]
>   optimizer_switch=block_nested_loop=off
>   ```
> - Another way is to add the following configuration to the `config/config.yml` file
>   ```yaml
>   doctrine:
>       dbal:
>           connections:
>               default:
>                   options:
>                       # PDO::MYSQL_ATTR_INIT_COMMAND
>                       1002: 'SET @@SESSION.optimizer_switch="block_nested_loop=off";'
>   ```

#### BUSINESS TIP
## Business Tip

B2B marketplaces are the future of eCommerce. Discover how to use a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B eCommerce marketplace</a> to your advantage and digitally revolutionize your company.

<!-- Frontend -->
