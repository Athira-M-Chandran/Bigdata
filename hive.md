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
> create table complex_data_type<br>
     (<br>
     emp_id int,<br>
     name map<string,string><br>
     ,<br>
     location struct<city:string,pin:int>,<br>
     skill_set array<string><br>
     )<br>
     row format delimited<br>
     fields terminated by ' \t '<br>
     collection items terminated by ' , '<br>
     location '/fsdsnov/';<br><br>
## Partition of the data
    
>create table emp_details_partition<br>
(<br>
    emp_name string,<br>
    age int,<br>
    Exp int<br>
)<br>
Partitioned by (location string)<br>
row format delimited<br>
fields terminated ' , ';<br>

## create a file and put the record there
sunny,25,3,bpl<br>
sudh,30,8,blr<br>
krish,35,12,blr<br>
avinash,22,5,hyd<br>

    
  ## Bucketing
    
>create table emp_detail_partition<br>
(<br>
    emp_name string,<br>
    age int,<br>
    exp int,<br>
    Location string<br>
)<br>
row format delimited<br>
fields terminated ' , ';<br>

<keep your data to this particular table location>

    >insert overwrite table emp_detail_partition partition(location) select * from emp_details;

Load data local inpath ‘home/cloudera/user.txt’ into table user;

>Create table buck_user<br>
(<br>
Id int,<br>
Name string,<br>
Salary int,<br>
Dept string<br>
)<br>
Clustered by (id)<br>
Sorted by (id)<br>
Into 2 buckets;<br>

>Set hive.enforce.bucketing=true;<br>

 >   Select * from buck_user;<br>
Select * from buck_user TABLESAMPLE(bucket 1 out of 2);<br>
Select * from buck_user TABLESAMPLE(bucket 2 out of 2);<br>


Set mapreduce.job.reduces=3<br>
—---------------------------------------------------------------------


## Serde

Csv serde<br> 
Tsv serde<br>
Json serde<br>
Xml serde<br>
Regex serde<br>

## Json serde

>Create table json_table<br>
(<br>
Name string,<br>
Id int,<br>
Skills array<string><br>
)<br>
Row format serde ‘org.apache.hive.hcatalog.data.JsonSerDe’<br>
Stored as textfile;<br>


Hive-hcatalog-core-0.14.0.jar<br>

hive> add jar <jar_file_path><br>

####Create a json file

{"name":"sunny","id":1,"skills":["haddop","python"]}<br>
{"name":"sumit","id":2,"skills":["ml","datascience"]}<br>
{"name":"amit","id":3,"skills":["dl","nlp"]}<br>

####load data from local

>Load data local inpath <json file path from local> into table json_table;<br>
    
    
####hOMEWORK

Regex.txt

host1/ amit @ amit@abc.com<br>
host2/ sumit @ sumit@abc.com<br>
host3/ sunny @ sunny@xyz.com<br>

For creating a table.

Create table userlog<br>
(<br>
Host string,<br>
Username string,<br>
Domain string<br>
)<br>
Row format serde ‘org.apache.hadoop.hive.contrib.serde2.RegexSerDe’<br>
WITH SERDEPROPERTIES(<br>
‘input .regex’=’(.*)/(.*)@(.*)’,<br>
‘output.format.string’=’%1$ %2$ %3$’);<br>

If you will issue with respect to jar file add it inside your hive.

