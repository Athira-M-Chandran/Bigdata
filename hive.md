# HIVE

## to activate
> **hive** in terminal; it will redirect to the the hive shell.
## show the available databases in the hive

> show databases;

## create database
> create database <database_name>;

## Use the current database in the hive
> use <database_name>;

## describe your database in the hive
>describe database <database_name>;

## create a table in hive

> create table <table_name><br>
(column_name datatype) <br>
row format delimited <br>
fields terminated by ',';

>eg; create table ineuron
    > (emp_id int,
    > location string,
    > email_id string)
    > row format delimited
    > fields terminated by ' , ';


## describe the table
> describe formatted ineuron;

## check the location of the table.
>pwd

## create a .csv file in your system and write data to csv file.

>101,hyd,sunny@ineuron.ai<br>
102,blr,sudh@ineuron.ai<br>
103,bpl,krish@ineuron.ai<br>
keep your .csv file in the give table location

## fetch the data from the table
>select * from ineuron;<br>

## alter the table in hive
> alter table table_name to new_table_table;