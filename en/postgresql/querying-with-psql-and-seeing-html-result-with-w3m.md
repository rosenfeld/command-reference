# Querying with psql and seeing the result in w3m like a spreadsheet

If you are working in a terminal and you have [w3m](http://w3m.sourceforge.net) (a text based Web browser and pager) available you can see results of a query in a html table right in the terminal.
The idea is to tell [psql](http://www.postgresql.org/docs/8.3/static/app-psql.html) to have its output in html format (-html switch) and to have w3m displaying it:

    psql database_name -c 'select * from table_name' --html | w3m -T 'text/html'
    
You can even write a shell script to do that for you. Something like:

    #!/bin/bash
    
    DB="$1"
    QUERY="$2"
    psql "$DB" -c "$QUERY" --html | w3m -T 'text/html'
