# Administrative Queries

## How to list all Tables in the database and their attributes
```
SELECT
   table_name,
   column_name,
   data_type
FROM
   information_schema.columns
WHERE
   table_name IN (
        SELECT table_name
        FROM information_schema.tables
        WHERE table_schema = 'public'
          AND table_type = 'BASE TABLE'
)
ORDER BY table_name, column_name;
```
