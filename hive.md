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

## create a external table in hive
>eg; create external table ineuron
    > (emp_id int,
    > location string,
    > email_id string)
    > row format delimited
    > fields terminated by ' , '
    > location '/fsdsnov/';

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

## Show database
> show databases;

>Create database <databasename>;

>Describe database <databasename>;

>Create database <database name> location “anyhdfslocation”;

>Drop database <databasename>;

## create complex table
> create table complex_data_type
    > (
    > emp_id int,
    > name map<string,string>
    > ,
    > location struct<city:string,pin:int>,
    > skill_set array<string>
    > )
    > row format delimited
    > fields terminated by ' \t '
    > collection items terminated by ' , '
    > location '/fsdsnov/';

>create table emp_details_partition
>(
    emp_name string,
    age int,
    Exp int
)
>Partitioned by (location string)
>row format delimited
>fields terminated ' , ';

## create a file and put the record there
sunny,25,3,bpl
sudh,30,8,blr
krish,35,12,blr
avinash,22,5,hyd

>create table emp_detail_partition
(
    emp_name string,
    age int,
    exp int,
    Location string
)
row format delimited
fields terminated ' , ';

<keep your data to this particular table location>
insert overwrite table emp_detail_partition partition(location) select * from emp_details;


