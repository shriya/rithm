# Weds May 17

## Warm Up

* [Hex class](https://www.codewars.com/kata/hex-class/train/javascript)

## SQL 

* [Aggregates exercise](https://github.com/rithmschool/sql_curriculum_exercises/blob/master/03-aggregates.md)

* calories > 250 && < 1000, price < 2.50, id < 10
`SELECT name as snack FROM snacks WHERE calories < 1000 and calories > 250 `

## psql commands

* `psql` enter psql
* `\q` quit psql

* `\du` list users
* `\dt` list tables
* `\d+ table_name` list details about table name
* `\l` list databases
* `\c NAME_OF_DB` connect to a database

* create db in psql: `CREATE DATABASE name_of_db;`

* `" "` name of a table
* `' '` string 
* **put all text in single quotes**

* `CREATE TABLE name_of_table (id SERIAL PRIMARY KEY, attribute TEXT);` create a table with two columns, one of data type SERIAL with the constraint PRIMARY KEY called id, other of data type TEXT called attribute

* `ALTER TABLE users ADD COLUMN favorite_number INTEGER; ` add column to table

* `ALTER TABLE users DROP COLUMN favorite_number;` remove column

* `INSERT INTO users(first_name, last_name) VALUES ('Elie', 'Schoppik');` add data

## psycopg2

* review - see everything running `ps aux` 
* see if specific thing is running `ps aux | grep python` (check if multiple running at once)
* SQL Injection - top security vulnerability - totally preventable!! Can add strings for values which are *themselves* SQL code. **Always** use provided libraries to do string interpolation of variables.

## SQL Alchemy

* ORM - provides a mapping between objects (in a language like Python) and rows in a relational DB table

## Outco

* Interview will be in Repl.it 
* 2 problems - 1 hr
* ~20 mins first one, ~40 mins second one

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this today

* SQL Practice
* Modus
* 
* SQL Alchemy

