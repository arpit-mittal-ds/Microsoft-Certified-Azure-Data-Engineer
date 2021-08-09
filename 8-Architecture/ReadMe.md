#Notes

https://docs.microsoft.com/en-us/azure/architecture/data-guide/

## Two general categories of data solution: traditional RDBMS workloads and big data solutions

**Traditional RDBMS workloads**

These workloads include online transaction processing (OLTP) and online analytical processing (OLAP). Data in OLTP systems is typically relational data with a predefined schema and a set of constraints to maintain referential integrity. Often, data from multiple sources in the organization may be consolidated into a data warehouse, using an ETL process to move and transform the source data.

![image](https://user-images.githubusercontent.com/68102477/122543146-cda42a00-d06e-11eb-9b00-3edc864e2c75.png)

**Big data solutions**

A big data architecture is designed to handle the ingestion, processing, and analysis of data that is too large or complex for traditional database systems. The data may be processed in batch or in real time. Big data solutions typically involve a large amount of non-relational data, such as key-value data, JSON documents, or time series data. Often traditional RDBMS systems are not well-suited to store this type of data. The term NoSQL refers to a family of databases designed to hold non-relational data. The term isn't quite accurate, because many non-relational data stores support SQL compatible queries. The term NoSQL stands for "Not only SQL".

![image](https://user-images.githubusercontent.com/68102477/122543247-eb718f00-d06e-11eb-98e2-5d3c16eceab3.png)

**The goal here is to help you select the right data architecture or data pipeline for your scenario, and then select the Azure services and technologies that best fit your requirements.**



https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/sqldw-walkthrough

https://faun.pub/model-your-azure-synapse-analytics-data-warehouse-4b3b7206ccd7









