# table(s) found without primary keys

## Description
Checks if there is any InnoDB table without a Primary Key. More information about InnoDB Primary Keys: https://www.percona.com/blog/2018/07/26/tuning-innodb-primary-keys/

## Rule
```
tables.table_schema, tables.table_name, tables.table_rows
            FROM information_schema.tables
            LEFT JOIN (
              SELECT table_schema, table_name
              FROM information_schema.statistics
              GROUP BY table_schema, table_name, index_name
              HAVING
                SUM(
                  CASE WHEN non_unique = 0 AND nullable != 'YES' THEN 1 ELSE 0 END
                ) = COUNT(*)
            ) puks
            ON tables.table_schema = puks.table_schema AND tables.table_name = puks.table_name
            WHERE puks.table_name IS NULL
              AND tables.table_schema NOT IN ('mysql', 'information_schema', 'performance_schema', 'sys')
              AND tables.table_type = 'BASE TABLE' AND engine='InnoDB'
```

## Resolution
Please consider adding a sequential Primary Key to your tables.
