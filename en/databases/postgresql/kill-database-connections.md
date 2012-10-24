# Killing PG database connections

Assuming PGHOST and PGUSER are set and that PGUSER has admin privileges on the PG server:

    psql -c "select pg_terminate_backend(procpid) from pg_stat_activity where procpid <> pg_backend_pid() and datname='database_name'" postgres

Or create a script like kill_pg_connections.sh

    #!/bin/sh
    psql -c "select pg_terminate_backend(procpid) from pg_stat_activity where procpid <> pg_backend_pid() and datname='$1'" postgres

Then call it like:

    PGHOST=localhost PGPORT=5432 PGUSER=postgres kill_pg_connections.sh database_name
