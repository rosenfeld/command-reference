# Storing passwords for databases in PostgreSQL

Create a ~/.pgpass file with the following format:

    localhost:5432:database_name:username:secret
    localhost:5432:*:username:secret
