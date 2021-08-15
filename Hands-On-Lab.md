
# [AZURE DATA ENGINEER](https://docs.microsoft.com/en-us/learn/certifications/azure-data-engineer/)

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


###  multiple ways to interact with Azure:

* Using the [Azure portal UI](https://azure.microsoft.com/)
* Using the Azure REST API
* Using the command line

All these ultimately end up calling the Azure REST API, behind which sits the Azure Resource Manager

![image](https://user-images.githubusercontent.com/68102477/129435208-4c9b39fc-423d-4046-9128-15ec1a221845.png)


* The Azure Resource Manager (ARM) is the deployment and management service for Azure. It provides a management layer that enables you
to create, update, and delete resources in your Azure account.

* Azure Resource Manager templates are JSON files that define the infrastructure and configuration of Azure resources. The templates use a declarative syntax, where you specify the resources to deploy and the properties of those resources.
* 
Azure Resource Manager templates can get complex, so you wouldn’t usually create
them “by hand.” You either get them already set up by someone else, or you initially
deploy your resources interactively using the Azure Portal or CLI, and then export the
corresponding Azure Resource Manager template. Exporting the template for a
resource means Azure generates the corresponding JSON to describe an existing
deployment. 


 focusing on DevOps and automation, we will avoid UI interaction as
much as possible and instead rely on scripting, which we can more easily transition from
ad hoc to automated. In most cases, this means using the command line

To interact with Azure using the command line, we will use PowerShell Core and
the Azure CLI.  Azure CLI is a multiplatform command line for interacting with Azure. It’s used
for configuration and task automation.

### [CODE REFERENCE]( https://github.com/vladris/azure-data-engineering)

## [AZURE CLI](Install Azure CLI on Windows)

## [QUICK OVERVIEW OF POWERSHELL](https://blog.netwrix.com/2018/02/21/windows-powershell-scripting-tutorial-for-beginners/)

![image](https://user-images.githubusercontent.com/68102477/129430686-e9b0e3fb-2818-4d26-8e60-e444ca39fbe9.png)

![image](https://user-images.githubusercontent.com/68102477/129430808-5b7c3151-51ae-48ec-8522-2d0fe29856e4.png)

Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'; rm .\AzureCLI.msi

A cmdlet is a PowerShell command with a predefined function, similar to an operator in a programming language. Here are some key things to know about cmdlets:

There are system, user and custom cmdlets.
Cmdlets output results as an object or as an array of objects.
Cmdlets can get data for analysis or transfer data to another cmdlet using pipes (I’ll discuss pipes more in a moment).
Cmdlets are case-insensitive. For example, it doesn’t matter whether you type “Get-ADUser”, “get-aduser” or “gEt-AdUsEr”.
If you want to use several cmdlets in one string, you must separate them with a semicolon (;).

A cmdlet always consists of a verb (or a word that functions as a verb) and a noun, separated with a hyphen (the “verb-noun” rule). For example, some of the verbs include:

Get — To get something
Set — To define something
Start — To run something
Stop — To stop something that is running
Out — To output something
New — To create something (“new” is not a verb, of course, but it functions as one)

Get-Help -Category 

Get-Help -Azure

![image](https://user-images.githubusercontent.com/68102477/129431005-6a0b4415-cb2d-41db-a372-389912533525.png)

## AZURE CLI



## AZURE DATA STORAGE

### Understand types of data and then map them to correct Azure data platform technologies / Choose a data storage approach in Azure

**Classify your data**

**Structured data** - data structure is defined at design time -  in the form of tables. Relational systems react slowly to changes in data requirements because the structural database needs to change every time a data requirement changes. When new columns are added, you might need to bulk-update all existing records to populate the new column throughout the table.

**Un-structured data** - In non-relational systems, the data structure isn't defined at design time, and data is typically loaded in its raw format. The data structure is defined only when the data is read.



## What is an AZURE STORAGE ?

* Azure provides many ways to store your data. There are multiple database options like Azure SQL Database, Azure Cosmos DB, and Azure Table Storage. Azure offers multiple ways to store and send messages, such as Azure Queues and Event Hubs. You can even store loose files using services like Azure Files and Azure Blobs.

* **Azure selected four of these DATA SERVICES and placed them together under the name AZURE STORAGE.** The four services are Azure Blobs, Azure Files, Azure Queues, and Azure Tables. The following illustration shows the elements of Azure Storage.

![image](https://user-images.githubusercontent.com/68102477/129471705-e305aafc-b16a-4fc7-9878-429f5e80d721.png)

* These four were given special treatment because they are all **primitive, cloud-based storage services and are often used together in the same application.**

## What is an AZURE STORAGE ACCOUNT?

**A storage account is a container that groups a set of Azure Storage services together. Only data services from Azure Storage can be included in a storage account (Azure Blobs, Azure Files, Azure Queues, and Azure Tables).** The following illustration shows a storage account containing several data services.

![image](https://user-images.githubusercontent.com/68102477/129471753-68769d75-1af2-4d1c-a341-7f979bbef3a5.png)

**Combining data services into a storage account lets you manage them as a group. The settings you specify when you create the account, or any that you change after creation, are applied to everything in the account.**

### How many storage accounts do you need?

**A storage account represents a collection of settings like location, replication strategy, and subscription owner. You need one storage account for every group of settings that you want to apply to your data.**


# Azure Storage offers four configuration options:

## Azure Blob: A scalable object store for text and binary data.

If you need to provision a data store that will **store but not query data**, your cheapest option is to set up a storage account as a Blob store. 

If you create a storage account as a Blob store, you can't query the data directly. **To query it, either move the data to a store that supports queries or set up the Azure Storage account for a data lake storage account.**

## Azure Files: Managed file shares for cloud or on-premises deployments

## Azure Queue: A messaging store for reliable messaging between application components

## Azure Table: A NoSQL store for no-schema storage of structured data

To ingest data into your system, use Azure Data Factory, Storage Explorer, the AzCopy tool, PowerShell, or Visual Studio. 

Azure Storage also provides you with fine-grained control over who has access to your data. You'll secure the data by using keys or shared access signatures. 

Azure Resource Manager provides a permissions model that uses role-based access control (RBAC). Use this functionality to set permissions and assign roles to users, groups, or applications.


## Data storage in Azure Data Lake Storage ADLS

* Data Lake Storage Gen2 builds on Azure Blob storage capabilities to optimize it specifically for analytics workloads. This integration enables analytics performance, the tiering and data lifecycle management capabilities of Blob storage, and the high-availability, security, and durability capabilities of Azure Storage.

* A benefit of Data Lake Storage Gen2 is that you can treat the data as if it's stored in a Hadoop Distributed File System. With this feature, you can store the data in one place and access it through compute technologies including Azure Databricks, Azure HDInsight, and Azure Synapse Analytics without moving the data between environments.

* Azure Data Lake Storage organizes the stored data into a hierarchy of directories and subdirectories, much like a file system, for easier navigation. As a result, data processing requires less computational resources, reducing both the time and cost

* Because Data Lake Storage supports Azure Active Directory ACLs, security administrators can control data access by using the familiar Active Directory Security Groups. Role-based access control (RBAC) is available both in Gen1 and Gen2. Built-in security groups include ReadOnlyUsers, WriteAccessUsers, and FullAccessUsers.

* Enable the firewall to limit traffic to only Azure services. Data Lake Storage **automatically encrypts data at rest, protecting data privacy.**

select Storage account - blob  => select StorageV2 (general-purpose v2) => the Data lake storage gen2(preview) option is set to Enabled 

In Azure Blob storage, you can store large amounts of unstructured ("object") data, in a single hierarchy, also known as a flat namespace. You can access this data by using HTTP or HTTPs. Azure Data Lake Storage Gen2 builds on blob storage and optimizes I/O of high-volume data by using hierarchical namespaces 

Hierarchical namespaces organize blob data into directories and stores metadata about each directory and the files within it. This structure allows operations, such as directory renames and deletes, to be performed in a single atomic operation

If you want to store data without performing analysis on the data, set the Hierarchical Namespace option to Disabled to set up the storage account as an Azure Blob storage account. You can also use blob storage to archive rarely used data or to store website assets such as images and media.

If you are performing analytics on the data, set up the storage account as an Azure Data Lake Storage Gen2 account by setting the Hierarchical Namespace option to Enabled. Because Azure Data Lake Storage Gen2 is integrated into the Azure Storage platform, applications can use either the Blob APIs or the Azure Data Lake Storage Gen2 file system APIs to access data.


[Examine uses for Azure Data Lake Storage Gen2](https://docs.microsoft.com/en-us/learn/modules/introduction-to-azure-data-lake-storage/6-use-cases)

# STORAGE

Storage is the
core piece of a data platform
around which everything else
is built. Data gets ingested
into the storage layer and is
distributed from there. All
workloads (data processing,
analytics, and machine
learning) access this layer.

### DEFINITIONS

* A dataset is a collection of data. In the case of tabular data, a dataset corresponds to one or more tables.

* A data fabric is an environment for storing and managing data.
From a consumer perspective, it represents a single storage technology—the
“fabric” on which the data persists. Examples of data fabrics in Azure are SQL,
Azure Data Explorer, Blob Storage, and so forth.

* Upstream
systems are systems from which we ingest data into our platform. 

* Downstream
systems are systems that consume data from our data platform.

Different teams in
an organization uses different
technologies to store data.

Example - The
website team uses Azure Data
Explorer, the payments team
uses Azure SQL, while the
customer success team uses a
third-party solution from which
we can get data via an API.
So in this example, a data platform needs
to stitch together data from multiple fabrics.

A large data platform needs to accommodate heterogenous data
storage. By heterogenous data storage, we mean data spread across multiple data fabrics.

We need to embrace having data across multiple storage solutions, not only for ingestion. Different workloads might perform better on different data fabrics 

 For example, Azure Data Explorer excels at querying millions
of rows in a matter of seconds, which identifies anomalies or produces aggregates.
Suppose we want to keep a large amount of data for historical reasons or simply to
allow other teams within our enterprise to copy the data to their systems. In this case,
Azure Data Explorer with its high-performance indexing and caching capabilities
might be overkill, so we can park the data in a cheap storage like Azure Data Lake
Storage

![image](https://user-images.githubusercontent.com/68102477/129006996-734aa307-e384-4f78-9696-4867689f3f8d.png)

## INGESTION

### Having a single source of truth

While we should embrace supporting multiple data fabrics, there is value in having a
“single source of truth”—one storage solution through which all data in the system
flows. Figure 2.4 shows Azure Data Explorer as such a single source of truth for our
data platform.

![image](https://user-images.githubusercontent.com/68102477/129009592-0698ed6c-ab23-4054-a8d5-565a3121b8e9.png)

a data issue upstream.
Once the issue is identified and corrected, we need to re-ingest the data. The single
source of truth helps because once we know the data has been updated there, the
updates flow seamlessly throughout the system. Contrast this with a setup in which various datasets land in different data fabrics. We would have to track the data flow of a
single dataset to make sure a fix is propagated correctly.
 The trade-off to be aware of is that the more data we move around, the more
latency and costs we incur and the more failure points we introduce into the system.
For example, if we ingest data from the payments team into Azure Data Explorer, then
we copy it to Azure Data Lake Storage, either of the steps could fail; we might run into
an issue ingesting into Azure Data Explorer, or we might run into an issue copying
into Azure Data Lake Storage. If we ingest the data directly into Azure Data Lake Storage, we have just one failure point, although it will be harder to tie this data together
with the data available in Azure Data Explorer. We need to find the right balance
between placing the data in the optimal storage solution for the processing we are trying to do and for keeping things at a reasonable cost and complexity level.

## Azure Data Explorer

Azure Data Explorer is a fast, fully managed data analytics service for analysis on large
volumes of data




# DEFINITIONS

* Infrastructure as code is the process of managing and provisioning infrastructure through automation by relying on configuration files and automation scripts as opposed to manual and interactive configurations.

* Codeless infrastructure is an infrastructure built by configuring existing services and connecting them to achieve the required scenarios. This is done with as little custom code as possible.

* ETL (short for extract, transform, load) is the general process of
copying data from one or more sources into a destination, while applying any
required transformation. Moving data around and running various processes on a schedule is a complex topic.

* A data lake is a system or repository of data, usually object blobs or
files, stored in its natural, raw format. Data lakes store structured, semistructured, and unstructured data, which is available for users and other systems
to read and process.


Focus should move from developing infrastructure to **connfiguring, deploying, and monitoring it,** and then **focusing on solving some of the higher-level challenges of the domain.** In our case, these challenges are around scaling out data workloads and governance concerns.

Some Azure services cover both storage and compute. For example, Azure Data
Explorer provides an integrated environment to both ingest data and perform analytics on it. Other services cover a single aspect; we can put data in a data lake, but we
need to connect some compute resource like Azure Machine Learning to it in order
to use the data.

The general format of an az command is
**az  group  [ subgroup ]  command   arguments**
  
 ### Creating an Azure resource group
  
 az group create --location "Central US" --name "MyResourceGroup"

![image](https://user-images.githubusercontent.com/68102477/129431291-1c934409-fb46-4a88-a5dc-f9b4b02897e6.png)

![image](https://user-images.githubusercontent.com/68102477/129431702-3dff40d0-81e4-46f5-b4c8-96442a294ac7.png)


### Deploy a Kusto (Azure Data Explorer) Cluster

![image](https://user-images.githubusercontent.com/68102477/129431916-a6c2615e-5c6d-45ab-9112-8c2f2b6ef0eb.png)

### Create a storage account

* The general-purpose storage account can be used for all four services: blobs, files, tables, and queues.

### Create another resource group for storage account
az group create --location "Central US" --name adls-rg

### create storage account
az storage account create --name "adlsarpit" --resource-group adls-rg --enable-hierarchical-namespace true

![image](https://user-images.githubusercontent.com/68102477/129432308-ef20de57-07c6-465b-93a5-240a911923ae.png)
  
### Azure Data Lake Storage (ADLS)

is a highly scalable and cost-efficient big data storage solution. Unlike Azure Data Explorer, Azure Data Lake Storage deals exclusively with storage. You can think of Azure Data Lake Storage as a filesystem in the cloud. Reading and processing data stored in the data lake requires an additional service to provide compute. 
 
Azure Data Lake Storage Gen2 is built on top of the basic [Azure Storage account](https://azure.microsoft.com/en-us/services/storage/) with additional filesystem capabilities. We create an Azure Data Lake Storage Gen2 instance the same way as a storage account with an additional setting to enable hierarchical namespaces.

### Next, provision a filesystem in this storage account as the following listing shows

az storage fs create --account-name "adlsarpit" --name fs1

![image](https://user-images.githubusercontent.com/68102477/129432376-0831fc4d-ea79-4542-8cfe-95584d1ecb6f.png)

### . Now, let’s create a file on our machine and upload it to the storage account. 

![image](https://user-images.githubusercontent.com/68102477/129432466-a73cf35b-2a77-4240-a448-ce8c4cb9ae95.png)

![image](https://user-images.githubusercontent.com/68102477/129434470-200dd51d-cdde-4611-a6f3-6cc2cb9dfc6f.png)


## Installing the azure-devops extension

az extension add --name azure-devops

### Let’s also generate a [personal access token so we can log into DevOps from Azure CLI](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=preview-page)

![image](https://user-images.githubusercontent.com/68102477/129434726-1d824fcc-3fa9-41ef-af48-782d630e610a.png)

### Logs in to Azure DevOps by providing the personal access token value

az devops login

### CREATE AN ORGANIZATION

![image](https://user-images.githubusercontent.com/68102477/129434872-b1904dd7-cfaa-4120-860f-d1ccd196f45b.png)

###  Creating a new project within the organization


az devops project create --organization "https://dev.azure.com/dataengineering-arpit" --name DE


### All az devops commands need to run against an organization and project

 Now we have a DevOps solution set up through which we can support source control and automated deployments
 
### Deploying infrastructure
First, let’s make sure our infrastructure can be deployed from Git. Our Azure Data
Explorer cluster was originally set up using Azure CLI. We will look at setting up an
automated deployment from the Azure Resource Manager templates stored in Git,
using Azure Pipelines. 


###  Exporting an Azure Resource Manager template

* Creates a new ARM subfolder for storing ARM templates

mkdir ARM

* Exports an ARM template for a resource group 

az group export --name adx-rg --include-parameter-default-value | Out-File ./ARM/adx-rg.json

![image](https://user-images.githubusercontent.com/68102477/129437864-21b03216-ed53-4ad2-aa3c-f4b4f59257e1.png)


Azure Resource Manager templates can get complex, so you wouldn’t usually create
them “by hand.” You either get them already set up by someone else, or you initially
deploy your resources interactively using the Azure Portal or CLI, and then export the
corresponding Azure Resource Manager template. It is the preferred method to deploy infrastructure automatically. Let’s commit it to Git and push it to our DevOps remote repository. 

### [Install Git Credential Manager Core](https://docs.microsoft.com/en-us/azure/devops/repos/git/set-up-credential-managers?view=azure-devops)

![image](https://user-images.githubusercontent.com/68102477/129438181-33698644-16ed-4438-8c75-1df88961803a.png)

This way we can commit the JSON ARM Templates to Git. 

N Azure Pipelines is a cloud service that you can use to automatically
build and test code, publish it to other users, and deploy it automatically.

 We store everything in Git, and we
deploy everything through pipelines. Before jumping into authoring pipelines,
there’s one more step we need to take—connecting our Azure DevOps project to our
Azure subscription.

## Azure Data Factory

# spin up an Azure Data Factory instance

* [setup.ps1 script should be used in production]()
*
* Break up of Steps

### Creates a new resource group to host our data factory
az group create --location "Central US" --name adf-rg

### Installs the datafactory extension
az extension add --name datafactory

### Provisions the data factory in the newly created resource group
az datafactory factory create --location "Central US" --name "adfarpit" --resource-group adf-rg

![image](https://user-images.githubusercontent.com/68102477/129465585-bde37520-5901-4922-9de6-a7910870f84b.png)

**Usually, you would set up the data movement through the visual editor. We’re going to use Azure CLI because it is more concise; instead of showing a series of screenshots, we’ll create a JSON file and run a command. In fact, once we set up DevOps for Azure Data Factory, WE SHOULD NOT USE CLI TO PROVISION OBJECTS.**

### Setting up the data source

* First, we need to set up our data source: the [Bing COVID-19 open dataset](http://mng.bz/y9vy). We will start by creating a linked service.

**DEFINITION Linked services are much like connection strings. They define the connection information needed for the data factory to connect to external resources.**

* Azure Data Factory can connect to many external resources, from Azure-native services like Azure SQL, Azure Data Explorer, and Azure Data Lake Storage to Amazon S3, SAP HANA, and to generic resources like FTP shared, HTTP servers, and so on.

* For our scenario, we need to connect to an HTTP server for the source and ADLS for the destination.

### Creating an HttpServer linked service

az datafactory linked-service create --factory-name "adfarpit" --resource-group adf-rg --name bingcovid19 --properties '@bingcovid19.json'

We just configured our Azure Data Factory to connect to the open dataset via HTTP.


### Now we’ll define the dataset.
* DEFINITION A dataset simply references the data you want to use in ADF.

Linked services tell Azure Data Factory how to connect to an external resource. Datasets tell Azure Data Factory what to expect there. 




































## CREATE A COSMOS DB ACCOUNT



# SYNAPSE

Azure Synapse Analytics is an integrated analytics platform, which combines data warehousing, big data analytics, data integration, and visualization into a single environment. 

This implements a data warehouse using a dedicated SQL pool that leverages the Massively Parallel Processing engine that brings together enterprise data warehousing and Big Data analytics.


## [CREATE A SYNAPSE WORKSPACE](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-create-workspace)


This deployment creates several resources which include an **Azure Data Lake Storage Gen2 account that acts as the primary storage and the container to store workspace data. **

The **workspace stores data in Apache Spark tables.... ??** It also stores Spark application logs under a folder called /synapse/workspacename. There are endpoints created that can be used to connect to the SQL on-demand service, and the Azure Synapse Analytics Workspace itself.

Azure Synapse Analytics enables you to create **pools, either SQL pools, or Spark pools** within the workspace that can be seamlessly mixed and matched based on your requirements.   It is able to do this through Azure Synapse Analytics shared metadata, which enables the different engines to share databases and tables.


For example, A shared Hive-compatible metadata system allows tables defined on files in the data lake to be seamlessly consumed by either Spark or Hive. SQL and Spark can directly explore and analyze Parquet, CSV, TSV, and JSON files stored in the data lake. 

![image](https://user-images.githubusercontent.com/68102477/129020246-95fb7163-a5e0-4a74-ba75-cd5763e4a6b4.png)

### You need to select a Data Lake Storage Gen2 account and a container in that account to create a workspace.

![image](https://user-images.githubusercontent.com/68102477/129021135-5fd813bc-c787-41ed-97b6-a5f1c2e02efe.png)


[How to set up access control for your Synapse workspace](https://docs.microsoft.com/en-gb/azure/synapse-analytics/security/how-to-set-up-access-control?WT.mc_id=Portal-Microsoft_Azure_Synapse)

Data in a data warehouse is stored in permanent tables that are populated using an extract, transform, and load (ETL) process by services such as Azure Synapse pipelines, or Azure Data Factory. As a result, you need to understand the data that is stored in the sources systems, how it should arrive within the data warehouse, which in turn dictates how you should cleanse or transform the data.

Dedicated SQL pools represent a collection of analytic resources that are being provisioned when using Synapse SQL. When you need predictable performance and cost, creating dedicated SQL pools to reserve processing power for data permanently stored in SQL tables in a data warehouse is the best approach to take.

The serverless model is ideal for unplanned or ad hoc workloads that the diagnostic analytics approach would generate.

## [ANALYZE DATA WITH A SERVERLESS SQL POOL](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-sql-on-demand)


## [CREATE A SERVERLESS APACHE SPARK POOL](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-sql-pool)

## ANALYZE DATA WITH APACHE SPARK POOL


Big data workloads are defined as workloads to handle data that is too large or complex for traditional database systems. Apache Spark processes large amounts of data in memory, which boosts the performance of analyzing big data more effectively, and this capability is available within Azure Synapse Analytics, and is referred to as Spark pools.

To achieve this capability, Spark pool clusters are groups of computers that are treated as a single computer and handle the execution of commands issued from notebooks. The clusters allow processing of data to be parallelized across many computers to improve scale and performance. It consists of a Spark Driver and Worker nodes. The Driver node sends work to the Worker nodes and instructs them to pull data from a specified data source. Moreover, you can configure the number of nodes that are required to perform the task.

**Support for Azure Data Lake Storage Generation 2**

Spark pools in Azure Synapse can use Azure Data Lake Storage Generation 2 as well as BLOB storage.

The primary use case for Apache Spark for Azure Synapse Analytics is to process big data workloads that cannot be handled by Azure Synapse SQL, and where you don’t have an existing Apache Spark implementation.

Perhaps you must perform a complex calculation on large volumes of data. Handling this requirement in Spark pools will be far more efficient than in Synapse SQL. You can pass the data through to the Spark cluster to perform the calculation, and then pass the processed data back into the data warehouse, or back to the data lake.

If you already have a Spark implementation in place already, Azure Synapse Analytics can also integrate with other Spark implementations such as Azure Databricks, so you don’t have to use the feature in Azure Synapse Analytics if you already have a Spark setup already.

So 3 options - Synapse SQL, Synapse Spark Pools, Azure Databricks.



## [CREATE A DEDICATED SQL POOL](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-sql-pool)

## ANALYZE DATA WITH DEDICATED SQL POOLS


## [ANALYZE DATA IN A STORAGE ACCOUNT](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-storage)



## [INTEGRATE WITH PIPELINES](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-pipelines)


# [AZURE DATA LAKE](https://github.com/MSRConnections/Azure-training-course/blob/master/Content/Data%20Lake/Azure%20Data%20Lake%20HOL.md)



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















# Using PolyBase to load data from Azure storage to Azure SQL Data Warehouse.


### DATA IS INITIALLY STORED IN AZURE BLOB

![image](https://user-images.githubusercontent.com/68102477/128795342-4d717402-baa9-4d33-b02f-e0a05081b2a2.png)

### CONNECT TO SYNAPSE USING VISUAL STUDIO AND EXPAND EXTERNAL TABLES 

* USING EXTERNAL TABLES, POLYBASE ALLOWS TO ACCESS AND QUERY DATA STORED OUTSIDE DATABASE

![image](https://user-images.githubusercontent.com/68102477/128795553-4fcae6f9-c4cd-4438-9830-de8ad6d619ca.png)

### STEP 1 - AUTHENTICATE AGAINST AZURE STORAGE ACCOUNT

* GET THE STORAGE KEY FROM AZURE STORAGE ACCOUNT

![image](https://user-images.githubusercontent.com/68102477/128795691-072b6036-1553-432a-a881-cff15241cdca.png)

* CREATE MASTER KEY IN SYNAPSE AND CREATE DATABSE SCOPED CREDENTIAL

![image](https://user-images.githubusercontent.com/68102477/128795773-284683b1-0c72-42fb-953d-43c7f80ebb3a.png)

### STEP 2 - CREATE EXTERNAL DATA SOURCE 

* BASICALLY WE ARE SPECIFYING LOCATION AND CREDENTIALS FOR AZURE BLOB ACCOUNT
* TYPE - HADOOP BECAUSE POLYBASE USES HADOOP APIs TO ACCESS AZURE STORAGE DATA 

![image](https://user-images.githubusercontent.com/68102477/128795994-0253b475-0d97-4539-b6f9-a410cdb1fc5b.png)

### STEP 3 - CREATE EXTERNAL FILE FORMAT

* TO SPECIFY THE LAYOUT OF THE DATA - IN THIS CASE - COMMA SEPARATED FILE

![image](https://user-images.githubusercontent.com/68102477/128796626-0684c07c-866a-4afa-9b44-6a9d091c4e07.png)


### STEP 4 - CREATE EXTERNAL TABLE

* SPECIFY LOCATION - DIRECTORY WHERE THE FILE RESIDES IN AZURE BLOB

![image](https://user-images.githubusercontent.com/68102477/128796748-2192b88a-7172-4144-ad5a-a55da59e436b.png)


### STEP 5 - LOAD THE DATA TO SYNAPSE

![image](https://user-images.githubusercontent.com/68102477/128796847-e6fb5046-aedb-4327-86ff-c390d1d75082.png)






# SECURITY

Identity has become the new primary security boundary. Accurately proving that someone is a valid user of your system, with an appropriate level of access, is critical to maintaining control of your data. This identity layer is now more often the target of attack than the network is.


Compare authentication and authorization

Two fundamental concepts that you need to understand when talking about identity and access are authentication (AuthN) and authorization (AuthZ).

Authentication and authorization both support everything else that happens. They occur sequentially in the identity and access process.

For example, all employees can access inventory and pricing software, but only store managers can access payroll and certain accounting software.

What is authentication?
Authentication is the process of establishing the identity of a person or service that wants to access a resource. It involves the act of challenging a party for legitimate credentials and provides the basis for creating a security principal for identity and access control. It establishes whether the user is who they say they are.

What is authorization?
Authentication establishes the user's identity, but authorization is the process of establishing what level of access an authenticated person or service has. It specifies what data they're allowed to access and what they can do with it.

![image](https://user-images.githubusercontent.com/68102477/129080269-832a0d1e-b495-4fb5-b903-9c01e8123fd2.png)

![image](https://user-images.githubusercontent.com/68102477/129120635-3a65ae36-f5f3-484b-888d-4d76ac900593.png)

The identification card represents credentials that the user has to prove their identity (you'll learn more about the types of credentials later in this module.) Once authenticated, authorization defines what kinds of applications, resources, and data that user can access.


What is Azure Active Directory?

Tailwind Traders already uses Active Directory to secure its on-premises environments. The company doesn't want its users to have a different username and password to remember for accessing applications and data in the cloud. Can the company integrate its existing Active Directory instance with cloud identity services to create a seamless experience for its users?

For on-premises environments, Active Directory running on Windows Server provides an identity and access management service that's managed by your own organization. Azure AD is Microsoft's cloud-based identity and access management service.

A tenant is a representation of an organization. A tenant is typically separated from other tenants and has its own identity.


Azure AD provides services such as:

Authentication

This includes verifying identity to access applications and resources. It also includes providing functionality such as self-service password reset, multifactor authentication, a custom list of banned passwords, and smart lockout services.

Single sign-on
What's single sign-on?
Single sign-on enables a user to sign in one time and use that credential to access multiple resources and applications from different providers.

More identities mean more passwords to remember and change
SSO enables you to remember only one username and one password to access multiple applications. A single identity is tied to a user, which simplifies the security model. Application management

You can manage your cloud and on-premises apps by using Azure AD.

Application management

You can manage your cloud and on-premises apps by using Azure AD.

Device management

Along with accounts for individual people, Azure AD supports the registration of devices. 



Connecting Active Directory with Azure AD enables you to provide a consistent identity experience to your users.

There are a few ways to connect your existing Active Directory installation with Azure AD. Perhaps the most popular method is to use Azure AD Connect.


![image](https://user-images.githubusercontent.com/68102477/129120658-1b2e56d5-0659-461b-879a-f1a5c7b0d5d9.png)

![image](https://user-images.githubusercontent.com/68102477/129120675-fe671ae0-059c-469d-a8f2-821dd6fe85ea.png)

![image](https://user-images.githubusercontent.com/68102477/129120706-af0ab132-2f88-4028-b42f-4dd74564a18b.png)

![image](https://user-images.githubusercontent.com/68102477/129120720-97629bdb-fe86-4caa-892f-129ba89cdf2c.png)

![image](https://user-images.githubusercontent.com/68102477/129120729-70b6703c-1ff2-441b-bee1-23d123fe0b92.png)

![image](https://user-images.githubusercontent.com/68102477/129121244-6c814e39-6068-4d6c-8beb-56dc2c413b49.png)

## COMMAND LINE TOOLS (BASH OR POWERSHELL)

![image](https://user-images.githubusercontent.com/68102477/129121314-e18bdeb0-ba23-4a30-b48e-4d3d1e04ed40.png)

![image](https://user-images.githubusercontent.com/68102477/129121414-aadc3740-8746-425c-928b-9a957c5f069f.png)

![image](https://user-images.githubusercontent.com/68102477/129121669-d735e59f-3d11-4dfa-81a4-03390a7d479a.png)

### Azure Resource Group 

* A logical grouping of few resources on Azure which share the same lifecycle.


### Azure Subscription

![image](https://user-images.githubusercontent.com/68102477/129122479-18b69377-00f7-4196-b766-5a2464d1a05e.png)

### Azure Resource Manager (ARM) - ARM Templates

![image](https://user-images.githubusercontent.com/68102477/129136394-b4bbbe2a-1edc-4ef3-be48-a8f211b5f1c2.png)

![image](https://user-images.githubusercontent.com/68102477/129182626-3debf122-2bfa-4c41-9f36-f64c1445a109.png)


### Using Powershell - can get all the commands for Azure

![image](https://user-images.githubusercontent.com/68102477/129182575-95e7d93c-87d9-4a72-902f-7be50c3520c3.png)


![image](https://user-images.githubusercontent.com/68102477/129182889-2ae720a7-08b1-4e94-9bb0-18ae1e988106.png)

![image](https://user-images.githubusercontent.com/68102477/129183283-a99547ac-b0a1-4dc1-9cef-96750128cb05.png)


## AZURE IDENTITY MANAGEMENT

![image](https://user-images.githubusercontent.com/68102477/129183442-805eb095-439e-4b4b-9c83-e91c34381996.png)













# WHAT IS DEVOPS ?

The standard across the software industry used to be for the **development team (Dev)
to implement services** and for the **operations team (Ops) to deploy them in the production environment and then monitor them.** The thinking behind this was that the
production environment needed to be locked down, and operational concerns like
provisioning machines, configuration, and monitoring required a different set of
skills than the design and development of services. **DevOps, on the other hand, lets
software engineers take charge of the end-to-end process.**


**DEFINITION** 

A DevOps team owns their solution end to end, from requirements
gathering and design through development and testing to deployment, monitoring, and fixing production issues.


**Two major shifts in the industry caused the emergence of DevOps.**

* The first is the broad adoption of agile software development practices, which aim to optimize the
time it takes for software delivery, from requirements to production. 

*  The second major shift is the move to the cloud. . The key change is the move from individual servers, which
require a lot of maintenance and attention, to infrastructure that can be provisioned
and deprovisioned on demand. 

The shift to the cloud created a renewed focus on automation for deployment and
configuration, which is an invaluable tool in the DevOps toolbox. The infrastructureas-code process of managing and provisioning infrastructure makes deployment and
operational concerns much more like software development. 

**Some of the key software tools that enable DevOps follow:**

* Source code management
* Build automation
* Packaging
* Release automation
* Monitoring and alerting

**BENEFIT**
We store our configuration in DevOps Repos (Git) and deploy using a pipeline.
If needed, we can replicate the deployment in a different environment.


It might seem like a lot of extra effort, but we know from software engineering the
value of automation. It might be easier to, for example, test some code manually once
or twice, but with a small investment in test automation, we save a lot of time in the
long run. We can run tests much more frequently and catch issues as early as they
appear, and that ends up saving us a lot of manual testing time.

DevOps removes
the coordination overhead between the two teams and the issues this overhead produces. For example, a deployment fails and the developer says, “It works on my
machine.” Then the developer works with the ops counterpart to identify the issue.

## DEPLOYING INFRASTRUCTURE




## AZURE DEVOPS

* Azure Pipelines, which we will use to automate build, validation, and deployment

* Source control, also known as Azure Repos, which includes Git hosting, code
review, and policies.

![image](https://user-images.githubusercontent.com/68102477/128985454-9dbb0664-50c8-41c0-9e47-c3d21a4a48be.png)

![image](https://user-images.githubusercontent.com/68102477/128985500-d38beabf-6eeb-463a-aa91-0fa7b00ec3bd.png)

![image](https://user-images.githubusercontent.com/68102477/128985583-cb9c23f0-5e21-4e88-bd1b-0d6cd8acb449.png)

![image](https://user-images.githubusercontent.com/68102477/128985607-73c445a0-8461-4fa5-bb6e-d6992d7fe8a8.png)

### Authenticate against your tenant so that the DevOps service is provisioned under your Azure account


![image](https://user-images.githubusercontent.com/68102477/129005072-48816076-816a-4a44-b273-dc2e3e6fa118.png)

















