# SQL
Structured Query Language

I did the tutorials and read through the lessons

A great simple to quickly navigate through data structures.

It gives you a selector to select the column that you want to search within and then you limit 
it with conditions to determine where in the column you want to search

You can also manipulate the data structure itself with SQL

You can use SQL to update your data as new data is produced.

You can also create empty tables to be filled with data as data arrives

## examples
example selection: SELECT column, another_column, …
                   FROM mytable;
adding constraints: SELECT column, another_column, …
                    FROM mytable
                    WHERE condition
                        AND/OR another_condition
                        AND/OR …;
                    Operator: =, !=, < <=, >, >=
                              BETWEEN … AND …
                              NOT BETWEEN … AND …
                              IN (…)
                              NOT IN (…)
filter: DISTINCT gives you distinct rows and excludes repeats
        ORDER BY lets you choose the order of the rows (ASC/DESC)
        LIMIT tells SQL the limit of the array of objects that will be returned
        OFFSET tells SQL which row to start collecting data from
        
inserting a row: INSERT INTO mytable
                  (column, another_column, …)
                  VALUES (value_or_expr, another_value_or_expr, …),
                         (value_or_expr_2, another_value_or_expr_2, …),
                         …;
updating a table: UPDATE mytable
                  SET column = value_or_expr, 
                      other_column = another_value_or_expr, 
                      …
                  WHERE condition;
                  
deleting rows: DELETE FROM mytable
               WHERE condition;
               
creating tables: CREATE TABLE IF NOT EXISTS mytable (
                  column DataType TableConstraint DEFAULT default_value,
                  another_column DataType TableConstraint DEFAULT default_value,
                  …
              );
              
altering tables, adding columns: ALTER TABLE mytable
                                  ADD column DataType OptionalTableConstraint 
                                  DEFAULT default_value;
                removing columns: ALTER TABLE mytable
                                   DROP column_to_be_deleted;
               renaming table: ALTER TABLE mytable
                                RENAME TO new_table_name;
dropping tables: Drop table statement
                  DROP TABLE IF EXISTS mytable;

                 
