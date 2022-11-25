[Hadoop record codes.txt](https://github.com/Pavithra0022/Hadoop_codes/files/10094418/Hadoop.record.codes.txt)
# Hadoop_codes# 
20BCAB22
PAVITHRA A



BASIC COMMANDS IN HADOOP

    hadoop fs -ls
    hadoop fs -mkdir sjc2022
    hadoop fs -cd sjc2022
    hadoop fs -ls /user/pavithra
    ls
   mkdir 2022
  ls
    2022
   vi sample.txt
   ls
    cd Desktop/
    ls
    hadoop fs -mkdir pavithra
    hadoop fs -ls
   hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv pavithra/emp.csv
   hadoop fs -ls pavithra
    man hadoop
    ls
   cd Desktop/
    hadoop fs -ls pavithra
    hadoop fs -ls pavithra
    pig
   hadoop fs -ls
    hadoop fs -pwd
    cd
    cd sjc2022
    hadoop fs -cp src Desktop
    hadoop fs -put/home/cloudera/2022/sample.txt /user/cloudera/sjc2022/
    cd sjc2022
    hadoop fs -ls
    ls
    cd Desktop/
    hadoop fs -ls
    ls -lrt
    ls -lrt Desktop
    hadoop fs -ls
    hadoop fs -rm -r pavithra
    hadoop fs -mkdir pavithra
   hadoop fs -ls
    hadoop fs -ls pavithra
    pwd
    cd Desktop

word count :

vi wordcount
ls
vi text 
ls
pwd
hadoop fs -copyFromLocal/homecloudera/Desktop/text pavithra/wordcount
hadoop fs -ls pavithra
pig
pwd
cd pavithra
ls
A = load 'wordcount' as (line: chararray);
dump A;
token = foreach A generate TOKENIZE (line);
dump token;
flat = foreach token generate FLATTEN($0);
dump flat;
groups = group flat by $0;
dump groups;
wc = foreach groups generate $0 as word, COUNT ($1) as freq;
dump wc;
A = load 'emp.csv' using PigStorage(',') as (eid: int, ename: chararray, epos: chararray, esal:int, ecom: int, edpno:int);
grunt> B = filter A by epos=='ANALYST';
grunt> dump B;
grunt> C = filter A by esal>=1500;
grunt> dump C;

[cloudera@quickstart ~]$ pwd
/home/cloudera
[cloudera@quickstart ~]$ hadoop fs -copyFromLocal /home/cloudera/Desktop/dept.csv pavithra/dept.csv


[cloudera@quickstart ~]$ hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv pavithra/emp.csv
[cloudera@quickstart ~]$ hadoop fs -ls pavithra


hive> create table dept (edpno int, epos string, ecity string) row format delimited fields terminated by ','; 
OK
Time taken: 0.706 seconds
hive> load data local inpath '/home/cloudera/Desktop/dept.csv' into table dept;
 select * from dept;


Hive

[cloudera@quickstart ~]$ hive
hive> show databases;
hive> create database pavithra;
hive> create table emp(eid int, ename string, epos string, esal int, ecom int, edpno int) row format delimited fields terminated by ',';
hive> load data local inpath '/home/cloudera/Desktop/emp.csv' into table emp;
hive> select * from emp;

[cloudera@quickstart ~]$ hadoop fs -ls
[cloudera@quickstart ~]$ hadoop fs -mkdir Pavithra
[cloudera@quickstart ~]$ hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv/Pavithra/emp.csv

PIG

[cloudera@quickstart ~]$ hadoop fs -mkdir pavithra
[cloudera@quickstart ~]$ hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv pavithra/emp.csv
[cloudera@quickstart ~]$ pig
grunt> cd pavithra
grunt> A = load 'emp.csv' using PigStorage(',') as (eid: int, ename: chararray, epos:chararray, esal:int,ecom:int, edpno: int);
grunt> D = limit A 5;
grunt> dump D;
grunt> E = order A by esal;
grunt> dump E;
grunt> F = order A by esal desc;
grunt> dump F;
grunt> store F into '/user/cloudera/pavithra/pigout/' using PigStorage(',');
grunt> G = foreach A generate eid;
grunt> dump G;
grunt> H = foreach A generate * , ecom * 3 as bonus, esal * 5 as incentive;
grunt> dump H;
grunt> I = foreach A generate SUBSTRING(ename,0,3);
grunt> dump I;
grunt> J = foreach A generate $0,$1;
grunt> dump J;
grunt> K = group A  by edpno;  
grunt> dump K;
grunt> M = group A by (edpno, epos);
grunt> dump M;
grunt> SPLIT A into B if edpno==10, C if edpno==20, D if epos=='Manager';

Joining
[cloudera@quickstart ~]$ hadoop fs -copyFromLocal /home/cloudera/Desktop/dept.csv pavithra/dept.csv

grunt> A = load 'emp.csv' using PigStorage(',') as (eid: int, ename: chararray, epos:chararray, esal:int,ecom:int, edpno: int);
grunt> B = load 'dept.csv' using PigStorage(',') as (edpno: int, epos:chararray,ecity: chararray);
grunt> C = JOIN A by edpno, B by edpno;
grunt> dump C;
grunt> D = foreach C generate A::eid,B::epos;
grunt> dump D;
grunt> E = JOIN A by edpno RIGHT OUTER, B by edpno;

Word Count
(in another terminal)
[cloudera@quickstart ~]$ hadoop fs -mkdir Pavithra
[cloudera@quickstart ~]$ hadoop fs -copyFromLocal /home/cloudera/Desktop/v.txt Pavithra/v.txt

(pig)
grunt> cat Pavithra/v.txt
hi
hi
i

grunt> lines = load '/user/cloudera/pavithra/v.txt' as (line:chararray);
grunt> dump lines;
grunt> token = foreach lines generate TOKENIZE(line);
grunt> dump token;
grunt> flats = foreach token generate FLATTEN($0);   
grunt> dump flats;
grunt> group_words = group flats by $0;
grunt> dump group_words;
grunt> count_words = foreach group_words generate group as word, COUNT($1) as word_occurence;
grunt> dump count_words;

   pwd
    hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv pavithra/emp.csv
    hadoop fs -ls pavithra
    pig
    vi text
    ls
    hadoop fs -copyFromLocal /home/cloudera/Desktop/text pavithra/wordcount
  hadoop fs -ls 
    pig
    hive
   hadoop fs -ls pavithra
   hadoop fs -cat /pavithra/external_table
   pig
    hadoop fs -pavithra
    hadoop fs -mkdir pavithra
   ls
    cd ..
    ls
   ls Desktop
    cd Documents
    ls
   hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv user/cloudera/pavithra/emp.csv
    hadoop fs -copyFromLocal /home/cloudera/Desktop/emp.csv pavithra/emp.csv
    
  pig
  ls
 quit
  Quit
   pig
    history

