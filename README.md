# Commands

## check version of hadoop 
>hadoop version

## list directories
> ls
## change directory
> cd

jps

## go back from the directory
> cd ..

## Create a folder in hdfs
> hdfs dfs -mkdir /name/<path_of_dir>

## copy data from local to hdfs
>hdfs dfs -put <local-dir-path> <hdfs_path>
<br>eg; hdfs dfs -put /config/workspace/fsds/data.
txt /test

or

>hfds dfs -copyFromLocal <local_dir_path> <hdfs_path>
<br>Eg; hfds dfs -copyFromLocal /config/workspace/trees.csv /

## to see the data
>hfds dfs -cat <file_path>
<br>eg; hfds dfs -cat/trees.csv

>hdfs dfs -ls /test

## for nano terminal
>type nano <filename> in terminal

## accessing the nano editor
> nano <filename><br>
 press insert in keyboard <br>
 <file_name><br>
 ctrl +o<br>
 enter <br>
 ctrl+x<br>

 ## getting a file 

>hdfs to local

>hdfs dfs -get <dir_name>

## For remove the file from the directory use

>hdfs dfs -rm <file or dir_name>

>hdfs dfs -rm -r <dir_path> 

## for file size

>hdfs dfs -du -s <file_path>

##  For checking all the commands and description write

>hdfs dfs -help

## copy something with in hdfs to hdfs so use -cp

>hdfs dfs -cp <hdfs_dir1> <hdfs_dir2>

## move from one directory to other directory

 >hdfs dfs -mv <hdfs_dir1> <hdfs_dir2>

## count 

>hdfs dfs -count <file-dir>

-> for Home directory
 hdfs dfs -count /  

 ## Create a file in hdfs

> hdfs dfs -touchz <file_name>

