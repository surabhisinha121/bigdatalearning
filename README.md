
+# surabhi_notes ON BIG DATA



Big Data which is too big to be hold 

5 v's

1.volume
2.variety - structured ,semi structured ,unstructured
3.velocity- speed which data is cominh
4.veracity- correctness or validity of data
5.value- value data is bringing

resources

1.computing- cpu
2.storage- Ram
3.memory-terabyte

monolithic- one big system holding lot of power,vertical scaling,(vertical scaling can limit hit , result in downtime)
distributed - horizontal scaling, 2 times resource 2 times performance HERE machine is known as node cluster
why we need bigdata
all good bigdata based on top of distributed processing

1.distributed storage
2.didtributed processing
3.scalablity

Hadoop is a framework to solve big data problems
three major core component

1.HDFS- Hadoop dISTRIBUTED FILE SYSTEM for storage
2.Map Reduce for processing computing(writing a map reduce is hard written in java).we ll learn apache spark
3.YARN is a Resource Manager (resource negotiator)

bunch of sorrounding technology 
pig
hbase
scoop
hive
oozie

 *suppose we have MySQL table we need to bring data from MySQL to hdfs that is called ingestion . we use scoop.now a days we are using cloud to bring data to hdfs and vice versa. we call scoop import and scoop export -- we ll use use Azure datafactory(provide thousand of connector)
*pig - scripting language to clean the data
*hive - gives you sql kind of interface for query
* oozie - workflow scheduler- Azure data factory- how to create pipeline
*hbase - no sql database .we ll learn cosmo db which is part of Azure

challenge of Hadoop

1.Map reduce job is slow 
2. for single we need to write 500 line of code
3.hadoop is on premise


cloud and its advantages

1.onpremise versus cloud

50 node Hadoop cluster 
buy 50 node
space 
cooling equipment
admin
running updates and software

starting startup

plugin office - when using pay its like taking on rent

advantage of cloud
==========================
1.scalable- suppose amazon is running sale on click of button ad resourece
2. on Premise capex is more in cloud  Opex is less - based on monthly rent
3.Agility - to setup it ll take month in cloud it ll be in minutes
4.Geodistribution
5.disaster recovery
6.cost effective

three types of cloud
============================
1.public- amazon Aws,microsoft azure,google cloud gcp
2.private- jp morgan ,safety compliance issue . more like onpremise ll hold data for ur company. not every one can use
3.Hybrid - public +private

cloud service model
=========================
saas - gmail,slack,office 365 ,end user
paas          ,application developrt
iaas -azure,aws,vmware  network archiect


haddop is loosing - Hadoop is dead Apache is spark  replacement
mapreduce 

Apache Spark replacement of Map reduce.its general purpose in memory compute engine .but its not bound to HDFS OR YARN
 
=============
Apache for computation

sorage- HDFS,AMAZON S3, Azure ADLS GEN2,GCS,Even ur local storage
Resource Manager-YARN,kUBERENETE,Mesos
10 to 100 time faster as it hold in memory


which language Apache spark--its written in scala . but we can  write in Python ,scala,java 

spark with python - pyspark


Database versus Datawarehouse versus Datalake
=======================================

Transactional data
OLTP-Online  Transiction processing
structured data
Recent data
schema on write

datawarehouse

lots of historical data to get insight .we get data from various sources.its structured and mostly schema on write

cannot keep so much data on database as its expensive
if we write complex queries to get insight day to day transaction ll be slow on database
ex of datawarehouse Teradata- storage cost is high but lesser than Database.its OLAP(ONLINE Analytical processing)
it follows

extract the data ,transform it and load it to datawarehouse


Datalake
================
ETL
to get insight from huge amount of data
data stored in raw format (may be structured,unstructured)
it follows ElT PROCESS
SCHEMA ON rEAD
DATA IS SEPERATE,SCHEMA IS SEPERATE

EXAMPLE hdfs,Amazon S3
IT Gives u enough flexibility


Big data big picture

s1
s2
  (SOURCE OF DATA) WE PASS DATA AS INJESTION         ================== > STORAGE Datalake=>dataprocessing(data cleaning,null,join,Aggregation)=========>serving layer=====>power bi or TABLEAU
s3
s4

SERVING LAYER DATABASE OR dATAWARE HOUSEN  WHEN you have to use reporting OR CONNECTED WITH some visualization
SERVING LAYER CAN BE HIVE OR HBASE ASWELL WHEN WE HAVE to built custom UI

incase  of aZURE cloud
MULTIPLE SOURCES ===>bringing Azure Datafactory(SCOOP ALTERNATIVE) ==.> where we ll bring ADLS GEN 2=======>AZURE sYNAPSE/AZURE DATABRICKS=>AZURE SQL/COSMODB

INCASE OF AWS

MULTIPLE SOURCE-> AWS GLUE->AMAZON s3->AWS DATABRICKS/ATHENA/REDSHIFT->AWS RDS/DYNAMO DB


