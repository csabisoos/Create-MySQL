
# Create Xampp MySQL databases and tables 

Create MySQL databases and tables in Xampp using Command Prompt.




## Run server locally
```
C:\xampp\mysql\bin\mysql.exe -h 127.0.0.1 -P 3306 -u root -p
```
After this press Enter at the password, because it leaves the password empty.

## Create database(s)
```
CREATE database my_database;
```
After this, if you want to use this database, that you just created, you have to use it first:
```
use my_database;
```

## Create table(s)
```
CREATE TABLE cats
(
  id              INT unsigned NOT NULL AUTO_INCREMENT, # unique ID
  name            VARCHAR(150) NOT NULL,                
  owner           VARCHAR(150) NOT NULL,                
  birth           DATE NOT NULL,                        
  PRIMARY KEY     (id)                                  
);
```

Auto-increment: Allows a unique number to be generated automatically when a new record is inserted into a table.

Unsigned: An unsigned type can be used to permit only nonnegative numbers in a column or when you need a larger upper numeric range for the column.

Not null: Enforces a column to NOT accept NULL values.

## Insert data into table
```
INSERT INTO cats ( name, owner, birth) VALUES
  ( 'Sandy', 'Lennon', '2015-01-03' ),
  ( 'Cookie', 'Casey', '2013-11-13' ),
  ( 'Charlie', 'River', '2016-05-21' );
```
If your input does not look like this you can change it in VSC, using RegEx:
### If it's divided by semicolon(;):
```
^(.*);(.*);(.*);(.*);(.*);(.*);(.*);(.*)$
```
```
('$1','$2','$3','$4','$5','$6','$7','$8'),
```
### If it's divided by tabs:
```
^(.*)\t(.*)$
```
```
('$1', '$2'),
```
Than, if the full input is selected, click replace all.

You can also mix the two if you have other input types. 

Here is an example:
```
(.*)\t(.*)\t(.*)\.(.*)\.(.*)\t(.*)\.(.*)\.(.*)
```
```
( '$1', '$2', '$3-$4-$5', '$6-$7-$8'), 
```

## Check what you've created
```
DESCRIBE my_table;
```
```
SELECT * FROM my_table;
```
## Deleting databases and tables
It drops the existing database "my_database".
```
DROP DATABASE my_database;
```
It drops the existing table "my_table".
```
DROP TABLE my_table;
```

