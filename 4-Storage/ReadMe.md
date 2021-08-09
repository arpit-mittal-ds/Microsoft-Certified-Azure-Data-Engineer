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
















