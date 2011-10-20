# Enabling UTF-8 by default

Create a file /etc/mysql/conf.d/mysqld_charset.cnf:

    [mysqld]
    character_set_server=utf8
    [client]
    default_character_set=utf8
