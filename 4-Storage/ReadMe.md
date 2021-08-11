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












