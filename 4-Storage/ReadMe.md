

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

### Deploying an Azure Data Explorer cluster

We’ll use Azure CLI to set up an Azure Data Explorer cluster 
























