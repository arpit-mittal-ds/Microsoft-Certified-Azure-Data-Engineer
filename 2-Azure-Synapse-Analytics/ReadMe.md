# AZURE SYNAPSE ANALYTICS


Azure Synapse Analytics is an integrated analytics platform, which combines data warehousing, big data analytics, data integration, and visualization into a single environment. 

This implements a data warehouse using a dedicated SQL pool that leverages the Massively Parallel Processing engine that brings together enterprise data warehousing and Big Data analytics.


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

### 











