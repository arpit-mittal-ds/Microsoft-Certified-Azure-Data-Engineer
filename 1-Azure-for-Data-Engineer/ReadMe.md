
# [AZURE DATA ENGINEER](https://docs.microsoft.com/en-us/learn/certifications/azure-data-engineer/)

## What is Azure


## [How Does Azure work ?](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/get-started/what-is-azure)

Azure uses a technology known as virtualization.

Virtualization separates the tight coupling between a computer's CPU and its operating system using an abstraction layer called a hypervisor.

The hypervisor emulates all the functions of a real computer and its CPU in a virtual machine.

It can run multiple virtual machines at the same time, and each virtual machine can run any compatible operating system such as Windows or Linux.

Azure takes this virtualization technology and repeats it on a massive scale in Microsoft data centers throughout the world.

Each data center has many racks filled with servers. Each server includes a hypervisor to run multiple virtual machines.

## Understand the evolving world of data 

Over the last decade, the amount of data that systems and devices generate has increased significantly. Because of this increase, new technologies, roles, and approaches to working with data are affecting data professionals

* Exponential increase in the number of devices and software that generate data.
* Data is key - Business stakeholders use data to make business decisions. Consumers use data to make decisions such as what to buy.


## Tasks of an Azure data engineer:

* Design and develop data storage and data processing solutions for the enterprise.
* Set up and deploy cloud-based data services such as blob services, databases, and analytics.
* Secure the platform and the stored data. Make sure only the necessary users can access the data.
* Ensure business continuity in uncommon conditions by using techniques for high availability and disaster recovery.
* Monitor to ensure that the systems run properly and are cost-effective.

## EXAMPLE - Design a data engineering project by following the five phases: source, ingest, prepare, analyze, and consume.

Contoso Health Network recently deployed IoT devices to its intensive care unit (ICU). Here are the goals of the project:

* Capture data on patient biometric monitoring in real time to help physicians treat their patients.
* Store the biometric data so that Contoso's research center can further analyze it in the future.
* Use Azure Machine Learning to understand which treatments improve the quality of care and reduce the likelihood that a patient will be readmitted to the hospital.
* Create a visualization of the data's history for Contoso's chief medical officer.

![image](https://user-images.githubusercontent.com/68102477/128694625-66be149f-c169-454e-ab71-ac1ee8960fed.png)

*  Azure IoT Hub to capture real-time data from the ICU's IoT devices.
*  Azure Stream Analytics to stream and enrich the IoT data, to create windows and aggregations, and to integrate Azure Machine Learning.
*  Azure Data Lake Storage Gen2 to store the biometric data at high speed.
*  Azure Data Factory to perform the extract, load, transform, and load (ELTL) process to move the data from the data lake store to Azure SQL Data Warehouse.
*  Azure SQL Data Warehouse to provide data warehousing services to support the chief medical officer's needs.
*  Power BI to create the patient dashboard. Part of the dashboard will show real-time telemetry about the patient's condition. The other part will show the patient's recent history.
*  Azure Machine Learning to process both raw and aggregated data. Researchers will use this to perform predictive analytics on patient readmittance.



## [Azure Data Architecture](https://docs.microsoft.com/en-us/azure/architecture/data-guide/)

## Two general categories of data solution: traditional RDBMS workloads and big data solutions

**Traditional RDBMS workloads**

* These workloads include online transaction processing (OLTP) and online analytical processing (OLAP). 
* Data in OLTP systems is typically relational data with a predefined schema and a set of constraints to maintain referential integrity. 
* Often, data from multiple sources in the organization may be consolidated into a data warehouse, using an ETL process to move and transform the source data.

### [Big data architectures](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/)

* A big data architecture is designed to handle the ingestion, processing, and analysis of **data that is too large or complex for traditional database systems.** 
* The data may be processed in batch or in real time. 
* Big data solutions typically **involve a large amount of non-relational data, such as key-value data, JSON documents, or time series data.** 
* Often **traditional RDBMS systems are not well-suited** to store this type of data. 
* The term NoSQL refers to a family of databases designed to hold non-relational data. The term isn't quite accurate, because many non-relational data stores support SQL compatible queries. The term NoSQL stands for **"Not only SQL".**

**The goal here is to select the right data architecture or data pipeline for your scenario, and then select the Azure services and technologies that best fit your requirements.**


### REFERENCES

https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/sqldw-walkthrough

https://faun.pub/model-your-azure-synapse-analytics-data-warehouse-4b3b7206ccd7


## Cloud environments

* Cloud computing environments provide the physical and logical infrastructure to host services, virtual servers, intelligent applications, and containers for their subscribers.
* Different from on-premises physical servers, cloud environments require no capital investment. Instead, an organization provisions service in the cloud and **pays only for what it uses.**
* Scalability - Scalability in on-premises systems is complicated and time-consuming. But **scalability in the cloud can be as simple as a mouse click.** Typically, **scalability in the cloud is measured in compute units.**
* Availability - Azure duplicates customer content for redundancy and high availability. Many services and platforms use SLAs to ensure that customers know the capabilities of the platform they're using.
* Total cost of ownership - Cloud systems like Azure track costs by subscriptions. A subscription can be based on usage that's measured in compute units, hours, or transactions. * * The cost includes hardware, software, disk storage, and labor. Because of economies of scale, an on-premises system can rarely compete with the cloud in terms of the measurement of the service usage. In cloud systems, the **cost usually is low and aligns more closely with the actual usage.**

