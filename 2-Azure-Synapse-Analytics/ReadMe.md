# AZURE SYNAPSE ANALYTICS


Azure Synapse Analytics is an integrated analytics platform, which combines data warehousing, big data analytics, data integration, and visualization into a single environment. 

This implements a data warehouse using a dedicated SQL pool that leverages the Massively Parallel Processing engine that brings together enterprise data warehousing and Big Data analytics.


## How Azure Synapse Analytics works

Azure Synapse SQL is a distributed query system that enables you to implement data warehousing using standard T-SQL familiar to data engineers.

Azure Synapse SQL is a distributed query system that enables you to implement data warehousing and data virtualization scenarios using standard T-SQL experiences familiar to data engineers.

Azure Synapse Studio  - Web UI to be able to access all Azure Synapse Analytics capabilities


## Create Azure Synapse Analytics workspace

This deployment creates several resources which include an **Azure Data Lake Storage Gen2 account that acts as the primary storage and the container to store workspace data. **

The **workspace stores data in Apache Spark tables.... ??** It also stores Spark application logs under a folder called /synapse/workspacename. There are endpoints created that can be used to connect to the SQL on-demand service, and the Azure Synapse Analytics Workspace itself.

Azure Synapse Analytics enables you to create **pools, either SQL pools, or Spark pools** within the workspace that can be seamlessly mixed and matched based on your requirements.   It is able to do this through Azure Synapse Analytics shared metadata, which enables the different engines to share databases and tables.


For example, A shared Hive-compatible metadata system allows tables defined on files in the data lake to be seamlessly consumed by either Spark or Hive. SQL and Spark can directly explore and analyze Parquet, CSV, TSV, and JSON files stored in the data lake. 

![image](https://user-images.githubusercontent.com/68102477/129020246-95fb7163-a5e0-4a74-ba75-cd5763e4a6b4.png)

![image](https://user-images.githubusercontent.com/68102477/129021135-5fd813bc-c787-41ed-97b6-a5f1c2e02efe.png)








## Implement a Data Warehouse with Azure Synapse Analytics

A data warehouse is a centralized relational database that integrates data from one or more disparate sources. 

Data warehouses store current and historical data and are used for reporting and analysis of the data. 

Many organizations need to store and process data more quickly and easily at an increasing scale to meet business demand and respond to market shifts. In the past this has involved complex processes, using different technologies including Big Data technologies and data integration tools to ingest and prepare the data before presenting it to applications. 

Azure Synapse Analytics is designed to simplify this process with limitless scale through one experience. Massively Parallel Processing architecture at limitless scale



![image](https://user-images.githubusercontent.com/68102477/125708158-91648194-dea3-4b00-849e-ae41067ad65e.png)

![image](https://user-images.githubusercontent.com/68102477/125708286-328ebb4a-5e37-4ecc-a4ff-f060201ece24.png)

![image](https://user-images.githubusercontent.com/68102477/125709001-53db38d2-c6d3-4fe9-9d03-c3e8edcec0bc.png)

![image](https://user-images.githubusercontent.com/68102477/125713267-020e1c00-0f63-4db6-9079-856f78dab2e9.png)

![image](https://user-images.githubusercontent.com/68102477/125713372-3f052519-ab7e-40e2-91a2-76c06d5e67ee.png)

 Design a Modern Data Warehouse using Azure Synapse Analytics
 
# Describe a Modern Data Warehouse

A modern data warehouse lets you bring together all your data at any scale easily.

You can get insights through analytical dashboards, operational reports, or advanced analytics for all your users.

## Define a Modern Data Warehouse Architecture

The process of building a modern data warehouse typically consists of:

1. Data Ingestion and Preparation.

customers build a data lake to store all their data and different data types with Azure Data Lake Store Gen2.

To ingest data, customers can do so code-free with over 100 data integration connectors with Azure Data Factory. 



2. Making the data ready for consumption by analytical tools.

3. Providing access to the data, in a shaped format so that it can easily be consumed by data visualization tools.


## Design ingestion patterns for a Modern Data Warehouse

## Understand data storage for a Modern Data Warehouse

## Prepare and transform data with Azure Synapse Analytics

## Serve data for analysis with Azure Synapse Analytics



# [DISTRIBUTED TABLES](https://docs.microsoft.com/en-us/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-tables-distribute)

|| processing of queries - distribute data so that || queries can run on them

![image](https://user-images.githubusercontent.com/68102477/125714710-2dc139f7-b7b3-46c5-b7ba-703946e76555.png)

# RESULT SET CACHING

![image](https://user-images.githubusercontent.com/68102477/125714926-473230e9-8f08-49a3-945a-480eb0f5fd4b.png)



-----------


# SYNAPSE TUNING 

* Synapse has an [MPP (Massive Parallel Processing) architecture](https://docs.microsoft.com/en-us/azure/synapse-analytics/sql/overview-architecture)
* So when you hear "nodes", these are the ones that do the compute for your queries.
* So the aim here is to distribute data across your cluster (eg paralell) to maximise performance.

There are 3 ways to distribute your data across these nodes

![image](https://user-images.githubusercontent.com/68102477/128811240-479b037a-a29a-400a-b63b-824b0c0c66aa.png)

![image](https://user-images.githubusercontent.com/68102477/128811289-cb5f69e0-f259-40d9-92b1-45fd1ff713d2.png)

### MAIN TOPICS FOR PERFORMANCE TUNING
STRUCTURE - HEAP OR CLUSTERED
STATISTICS - HOW DATABASE KNOWS WHICH ROWS ARE WHERE
DATATYPES - 
WORKLOAD MANAGEMENT - 
![image](https://user-images.githubusercontent.com/68102477/128811328-0428d0d7-f0ce-4293-aef4-141fabfe062b.png)

### HEAP TABLES ARE FASTER FOR etl 
### CCI TABLES ARE BEST FOR QUERY PERFORMANCE

![image](https://user-images.githubusercontent.com/68102477/128811461-c50ee90a-0ee6-47d9-bc7b-227cc0f0d91c.png)

### SKEWED DISTRIBUTION - WHERE MOST OF THE ROWS ARE ON FEW NODES - DATA IS NOT EVENLY DISTRIBUTED BETWEEN NODES
### DISTRIBUTION - ROUND ROBIN 
### REPLICATED 
### HASH IS BEST FOR PERFORMANCE

![image](https://user-images.githubusercontent.com/68102477/128811572-4e42a40e-eecf-49d9-ab61-fce72532cbc3.png)

![image](https://user-images.githubusercontent.com/68102477/128811726-57da1a01-ae47-4aa7-a6ec-c16b572d1db4.png)

### ELIMINATING SHUFFLING
![image](https://user-images.githubusercontent.com/68102477/128811757-e9c61b0c-3c98-4916-b1dc-8a46936e3ed0.png)

### SHUFFLING - MOVING DATA 
### VERY COSTLY
![image](https://user-images.githubusercontent.com/68102477/128811816-e7eb2a1f-ec11-4c80-9363-66622067e6f5.png)

### BY JUST CHANGING THE DISTRIBUTION 
![image](https://user-images.githubusercontent.com/68102477/128811882-a539abb0-9be4-4c0e-9a93-9272cab0fa78.png)

### SHUFFLE AND BROADCAST HAPPENING ON REPLICATED TABLES - SHOULD NEVER HAPPEN

![image](https://user-images.githubusercontent.com/68102477/128811950-f4e7bf80-4289-49f5-9891-b714656e7cbd.png)

### ROUND ROBIN 

![image](https://user-images.githubusercontent.com/68102477/128812035-c15ebc8b-e69a-48fa-bc4c-bc28564b3961.png)

### DIAGNOSTIC TOOLS

![image](https://user-images.githubusercontent.com/68102477/128812397-e7094d21-8730-4836-ae8a-fa6bbcf85743.png)


### EXPLAIN PLAN

### DSQL - DISTRIBUTED SQL GETS GENERATED INTERNALLY BY SYNPASE AFTER OPTIMIZING THE QUERIES
### NEEDS 

![image](https://user-images.githubusercontent.com/68102477/128812445-9d0b6e97-c6a4-4175-9304-5732297759ce.png)

### LABEL = TO GET THE PARTICULAR QUERY EXPLAIN PLAN
![image](https://user-images.githubusercontent.com/68102477/128812863-5015074b-3f8e-423b-b6c6-2cc585e96323.png)

![image](https://user-images.githubusercontent.com/68102477/128813117-f71fe208-a515-43d9-b77b-7d60e5e47b81.png)

### GET THE EXPLAIN PLAN OF THE QUERY

![image](https://user-images.githubusercontent.com/68102477/128813255-d50ae3f1-277a-4cc6-b1b1-c89bb33388ef.png)

### PASTE THE EXPLAIN PLAN IN THE NEW XML FILE

![image](https://user-images.githubusercontent.com/68102477/128830954-5333fab1-11cf-4b13-bbe8-d8688c3fdecf.png)

![image](https://user-images.githubusercontent.com/68102477/128830896-7f4f1e60-27f7-495d-a5b3-d2d85cd7b9a6.png)


### BROADCAST VS SHUFFLE - BOTH ARE BAD FOR PERFORMANCE
### SHUFFLE - TAKE THE RECORD AND MOVE IT TO ANOTHER NODE
### BROADCAST_MOVE - CAUSE - DATATYPES OF THE COLUMNS DO NOT MATCH IN THE JOIN/COMPARISON CONDITION (REQUIRES CONVERSION) OR REPLICATION HAS NOT YET HAPPENED 
![image](https://user-images.githubusercontent.com/68102477/128813500-9cbed675-fc98-4ea1-8877-2743fca32b2e.png)

### WE WERE JOINING MEDALLION AND TRIP TABLES
### WE CAN NOTICE THAT THE DATATYPE OF THE COLUMNS ON WHICH WE ARE JOINING (HENCE COMPARING) TABLES, IS NOT SAME.
![image](https://user-images.githubusercontent.com/68102477/128813852-f5c32c2d-d9a5-47b4-be17-24bc1b9d98b0.png)


### HENCE LET'S DO TYPECASETING

![image](https://user-images.githubusercontent.com/68102477/128814133-2f7bf4d6-62d9-4258-b5f9-d781aa1720dc.png)

### BROADCAST_MOVE HAS NOW 
![image](https://user-images.githubusercontent.com/68102477/128813978-7bd99ced-7a5d-4a2b-aa79-fb4c9e698a7e.png)

### THE 2 TBALES ARE ROUND ROBIN
### DATBASE IS HENCE SHUFFLING FOR THE JOIN
### LET'S REDISTRIBUTE AND USE HASH DISTRIBUTION

![image](https://user-images.githubusercontent.com/68102477/128830308-a2495500-de90-4bd7-b067-abb0d929652d.png)

### AFTER REFERRING EXPLAIN PLAN AND THEN AVOIDING SHUFFLE AND BROADCAST WE WERE ABLE TO IMPROVE THE QUERY PERFORMANCE

![image](https://user-images.githubusercontent.com/68102477/128830245-a8cf0d94-2f02-4e94-a019-4e8a716311ac.png)




















