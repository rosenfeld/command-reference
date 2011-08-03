# Finding duplicate records with same column(s) value

Sometimes, this is useful if you have an inconsistent database and are unable to create a unique index in 2 fields:

    SELECT * FROM table_name a WHERE 1 < (SELECT count(*) FROM table_name b WHERE a.column1 = b.column1 AND a.column2 = b.column2)
