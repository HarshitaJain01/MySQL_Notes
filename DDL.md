# Data Defination Language
# ALTER/DROP/TRUNCATE

## Create table 
CREATE TABLE name (
  column name datatype,
    id char(2) PRIMARY KEY NOT NULL,
    name char(24)
  );
### Alter table 
ALTER TABLE table_name
ADD COLUMN column_name data_type column_constraint;

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE table_name
ALTER COLUMN column_name SET DATA TYPE data_type;

ALTER TABLE table_name
RENAME COLUMN current_column_name TO new_column_name;

### Drop Table 
DROP TABLE table_name;

### Truncate Table 
TRUNCATE TABLE table_name
IMMIDIATE;
 
