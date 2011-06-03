# Storing passwords for databases in PostgreSQL

Create a ~/.pgpass file with permission 0600 and the following format:

    localhost:5432:database_name:username:secret
    localhost:5432:*:username:secret

It also helps to add something like this in ~/.bashrc

    export PGHOST=localhost
    export PGUSER=username
    export PGDATABASE=database_name
    export PGPORT=5432
