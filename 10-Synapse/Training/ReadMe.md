# AZURE SYNAPSE ANALYTICS
![image](https://user-images.githubusercontent.com/68102477/141208007-ca2bfeb2-5691-4dcd-adbd-543c4de08cfa.png)

## 1. SYNPASE COMPONENTS
![image](https://user-images.githubusercontent.com/68102477/141208258-fc42c30e-1c87-463d-aa41-6836e58356ca.png)

![image](https://user-images.githubusercontent.com/68102477/141208508-46c441cf-d109-40cc-99dc-986819671841.png)

![image](https://user-images.githubusercontent.com/68102477/141208922-2159cd2d-0a2b-40e1-a11e-4c9d5bb1038d.png)

## 2. DEMO - SYNPASE STUDIO

![image](https://user-images.githubusercontent.com/68102477/141209399-b943d24c-ba6f-4ec9-a17c-52306fa6532a.png)
### [SAMPLE DATASETS, SAMPLE NOTEBOOKS AND SAMPLE SQL SCRIPTS AND TEMPLATE PIPELINES](https://azure.microsoft.com/en-au/blog/quickly-get-started-with-samples-in-azure-synapse-analytics/)
![image](https://user-images.githubusercontent.com/68102477/141209461-36a2b441-95c4-4bf0-ad21-2c40e2a6ec32.png)
### Synapse Studio divided into Activity hubs - DATA, DEVELOP, INTEGRATE, MANAGE, MONITOR
* These organize the tasks needed for building analytics solution.
![image](https://user-images.githubusercontent.com/68102477/141209544-cbb0759f-116e-4c6d-b7ad-e684dcd0d47c.png)
![image](https://user-images.githubusercontent.com/68102477/141209579-2d1b5f3e-6fc7-4aa2-b79f-d1e2f6b2d307.png)

## 3. DATA WAREHOUSING
![image](https://user-images.githubusercontent.com/68102477/141210313-a3f8efae-af9b-4bdb-b768-03d930c79f28.png)
### NEWER OPTIONS
* SYNAPSE PIPELINES - WHEN WANT TO USE ONLY AZURE COMPONENTS VS ADF - WHEN USING OTHER STORAGE COMPONENTS
![image](https://user-images.githubusercontent.com/68102477/141210665-f8933373-022a-4429-a987-b530b411352b.png)
### DEMO


## 4. Module II - Dedicated SQL Pools
![image](https://user-images.githubusercontent.com/68102477/141213245-92a43178-b653-42fd-af50-a2d0e9f5bbbe.png)
![image](https://user-images.githubusercontent.com/68102477/141213359-6b607a97-1ae4-42fe-ba63-9851b12742cf.png)
![image](https://user-images.githubusercontent.com/68102477/141213397-68a2cae5-a07a-4ad2-8a33-55cbf034472e.png)
![image](https://user-images.githubusercontent.com/68102477/141213572-9dfcb807-b743-4638-b1b0-e21cd5dd1c27.png)
![image](https://user-images.githubusercontent.com/68102477/141213648-79f22645-a82a-4834-aad3-edd38875e8a8.png)
![image](https://user-images.githubusercontent.com/68102477/141213671-6206e68e-0bc1-4198-82bd-2ba02d6c5488.png)
![image](https://user-images.githubusercontent.com/68102477/141213815-c146ea56-cf5e-4468-9255-b6ec961b86c2.png)

## 5. Data Loadin Synapse
![image](https://user-images.githubusercontent.com/68102477/141214969-5768b613-610f-427c-a3fd-bfe30c0e1751.png)
### Demo:


## 6 . Optimize data warehouse query performance in Azure Synapse Dedicated SQL Pools

# BASICS:
Azure SQL Database (and traditional versions of SQL Server) utilizes computers based on the SMP model.  Ultimately, this means that **SQL Server is installed on a single computer/server that may (and probably does) have multiple CPU’s and cores and therefore permits parallel processing.**  However, there is only one database that is doing all the work to support requests.

The data warehouse provided in Azure Synapse Analytics (and its’ antecedents) is built on a Massively Parallel Processing architecture.  In this case, **multiple computers/servers (referred to as nodes) with dedicated processors are deployed, all with SQL Server installed.**

Each instance has its own processors, memory, and dedicated storage.  One node in this scenario is the control node.  The purpose of the control node is to distribute requests to worker nodes.  The worker nodes do all work that can be done locally and report the results to the control node.  The control node then performs any additional work on the combined results from all worker nodes and reports the results to the requestor.

![image](https://user-images.githubusercontent.com/68102477/141606440-f278a15b-f316-48c6-ae35-91ef99572aa8.png)
![image](https://user-images.githubusercontent.com/68102477/141606446-a8479ce5-fc58-4dab-a86d-c982495147ec.png)

##  Central to the MPP architecture is the shard.  What is a shard? 

SHARD is one of the SQL compute nodes and its associated blob storage, referred to above as a worker node.  Shards are horizontal partitions of data.  It is possible that some data exists on all shards, but the typical usage is for a shard to own a subset of the overall data.  Every shard is held on one database server.  Each shard acts as the single source for a subset of data, determined by the distribution chosen.


There are different design considerations as well as limitations in t-SQL in MPP compared to SMP


## Referential integrity constraints cannot be applied in the Synapse Analytics data warehouse due to their being:

* No primary keys
* No foreign keys
* No unique constraints

There are probably several reasons for this, but they likely center on performance considerations, particularly if enforcement requires the database to visit other shards to determine if there is a violation.  If uniqueness or existence must be enforced, then it must be done in code.


## Distributions
The distribution of a table in an MPP architecture defines **how data will be distributed among the shards.**  While this can be considered a partitioning of the data, it is not the same as the partitioning of data that SQL Server supports.  Synapse Analytics also supports that method of partitioning. Three methods are available for defining the distribution of data in a shard of a table:

* ROUND_ROBIN
* HASH(column)
* REPLICATE

### ROUND_ROBIN
As the name suggests, the control node distributes data sequentially through the shards.  By definition, data is well distributed among each of the worker nodes. 

### REPLICATE
For a distribution that is set to REPLICATE, a copy of the data is retained on every shard.  This is generally most applicable to reference tables where the data is ‘small’.  Movement of data to the shards to satisfy join lookups is avoided unless the looked-up data is modified.  Data in a replicated table is maintained on the control node and copied as needed to the individual shards.

###  HASH({column})

In the HASH distribution, the data is organized among the shards based on a hashed value of the column passed as a parameter to the hash function.  Only one column may be used in the HASH() function.   There are many considerations when choosing the column to hash.  The choice should allow as many operations as possible to be pushed to the individual shards such that they can be performed in parallel.  

Indexing
Indexing for a sharded database generally follows the rules one would apply to a traditional database with a few exceptions.  A table should be expected to contain at least 1 million records per shard for a clustered columnstore index to be effective.  For most Synapse Analytics data warehouses that means 60 million records.  Otherwise, a heap should be chosen.  Ordinary indexes, clustered and nonclustered may be defined.  Unique indexes are not permitted. 

One can easily convert between a clustered columnstore index and a heap using the normal CREATE and DROP statements.  If one desires a clustered columnstore index that is named according to a naming convention, the table must be created as a heap and then converted to a clustered columnstore index

Distribution Check
The distribution of data in a table that is hashed on a column can be checked as follows:

DBCC PDW_SHOWSPACEUSED(‘table_name’);
It may be determined that the distribution of records is inadequate.  Alternatives can be quickly compared by generating additional versions of the table in question using CTAS (CREATE TABLE AS SELECT) to create tables with differing distributions.




https://cloudworkshop.blob.core.windows.net/azure-synapse-analytics-end-to-end-solution/Hands-on%20lab/HOL%20step-by%20step%20-%20Azure%20Synapse%20Analytics%20and%20AI.html

https://techcommunity.microsoft.com/t5/microsoft-learn/new-microsoft-learn-content-all-about-azure-synapse-analytics/m-p/1953762

https://azure.microsoft.com/en-us/services/synapse-analytics/video-demos/

https://www.microsoft.com/en-au/business/learn/cloud-training-events/

https://docs.microsoft.com/en-gb/learn/roles/data-engineer



















