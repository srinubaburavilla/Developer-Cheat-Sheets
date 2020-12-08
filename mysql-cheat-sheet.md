
## Database

|Query|Details|
|--|--|
|Create Database|CREATE DATABASE IF NOT EXISTS database_name;|
|Drop Database|DROP DATABASE IF EXISTS database_name;|
|Use Databse|USE database_name; |
|Show all databases|SHOW DATABASES;|

## Tables
|Query|Details|
|--|--|
|Create table|Create table table-name(<br/>&nbsp;&nbsp;&nbsp;&nbsp;id int,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col2 tinyint,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col3 bigint,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col4 smallint,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col5 varchar(20),<br/>&nbsp;&nbsp;&nbsp;&nbsp;col6 text,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col7 date,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col8 datetime,<br/>&nbsp;&nbsp;&nbsp;&nbsp;col9 longtext,<br/>&nbsp;&nbsp;&nbsp;&nbsp;primary key(id) -- Primary key<br/>&nbsp;&nbsp;&nbsp;&nbsp;unique key table-name_col1 (col1) -- unique key on one column<br/>&nbsp;&nbsp;&nbsp;&nbsp;unique key table-name_col2_col3_col4 (col2,col3,col4,col4) -- unique column on mutiple columns);|
|Add new column with unique key, auto-increment|alter table table-name add column column-name int not null auto_increment primary key;|
|Add new column to table|alter table table-name<br/>add column column_name;|
|Drop column from table-name| alter table table_name<br/>drop column column_name|
|Modify column data type|alter table table-name modify column column-name int;|
|Show all tables in the selected/active database|show tables;|
|Show/display sql query to create the table|show create table tablename;|
|List all indexes on a table|show index from table-name|
|Describe table|describe table-name;|
|Rename table name|alter table current-table-name rename to new-table-name;|
|Duplicate a table schema|create table new-table-name like existing-table;|
|Duplicate a table|create table new-table select * from existing-table;|
|Aggregation- sum|select sum\(col-name\) from table-name group by col-name;|
|Aggregation- avg|select avg\(col-name\) from col-name group by col-name;|
|Aggregation- count|select col-name, count(col-name) from table-name group by col-name;|
|Aggregation- max|select max\(col-name\) from table-name group by col-name;|
|Aggregation- min|select min\(col-name\) from table-name group by col-name;|

### Convert string to DATETIME
```sql
SELECT CONVERT('2020-10-30 20:05:46', DATETIME)
```

### Querying information_schema.key_column_usage
```sql
select * from information_schema.key_column_usage

-- Get all foreign keys
select 
    concat(table_name, '.', column_name) as 'foreign key',  
    concat(referenced_table_name, '.', referenced_column_name) as 'references'
from
    information_schema.key_column_usage
where
    referenced_table_name is not null;

-- Get all foreign key references of table
select 
    concat(table_name, '.', column_name) as 'foreign key',  
    concat(referenced_table_name, '.', referenced_column_name) as 'references'
from
    information_schema.key_column_usage
where
    referenced_table_name ='table_name_to_check'

-- Get all foreign keys of particular database
select 
    concat(table_name, '.', column_name) as 'foreign key',  
    concat(referenced_table_name, '.', referenced_column_name) as 'references'
from
    information_schema.key_column_usage
where
    referenced_table_name is not null
    and table_schema = 'database_name'
```

### Get all columns schema of tables
```sql
select * from information_schema.columns
where table_schema = 'database'
and table_name in ('table1','table2')
```

### Enable or Disable FOREIGN_KEY_CHECKS, UNIQUE_CHECKS
```sql
-- Beginning of script, Disable UNIQUE_CHECKS and FOREIGN_KEY_CHECKS
SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0; 
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0; 


-- Ending of script, Enable UNIQUE_CHECKS and FOREIGN_KEY_CHECKS
SET SQL_MODE=@OLD_SQL_MODE; 
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS; 


SELECT @@FOREIGN_KEY_CHECKS
-- Manually update FOREIGN_KEY_CHECKS
set @@FOREIGN_KEY_CHECKS=1

-- Get local and global foreign_key_checks
SELECT @@GLOBAL.foreign_key_checks, @@SESSION.foreign_key_checks;

```

### Useful links can refer
#### [Cheat Sheet](https://www.mysqltutorial.org/mysql-cheat-sheet.aspx)
#### [Cheat Sheet pdf](https://websitesetup.org/wp-content/uploads/2020/04/MySQL-Cheat-Sheet-websitesetup.org_.pdf)
#### [An Intermediate MySQL Tutorial](https://www3.ntu.edu.sg/home/ehchua/programming/sql/MySQL_Intermediate.html)
#### [mysql workbench](https://docs.oracle.com/cd/E19078-01/mysql/mysql-workbench/)
#### [MySQL 8.0 Reference Manual - Go for search](https://dev.mysql.com/doc/refman/8.0/en)
#### [SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)
#### [Querying INFORMATION_SCHEMA table](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

