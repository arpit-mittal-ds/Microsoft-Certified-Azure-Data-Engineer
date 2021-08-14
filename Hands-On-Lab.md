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

Using the Azure portal UI at https://azure.microsoft.com/
 Using the Azure REST API
 Using the command line

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



## CREATE A COSMOS DB ACCOUNT


# SYNAPSE


## [CREATE A SYNAPSE WORKSPACE](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-create-workspace)


## [ANALYZE DATA WITH A SERVERLESS SQL POOL](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-sql-on-demand)


## [CREATE A SERVERLESS APACHE SPARK POOL](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-sql-pool)

## ANALYZE DATA WITH APACHE SPARK POOL



## [CREATE A DEDICATED SQL POOL](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-sql-pool)

## ANALYZE DATA WITH DEDICATED SQL POOLS


## [ANALYZE DATA IN A STORAGE ACCOUNT](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-analyze-storage)



## [INTEGRATE WITH PIPELINES](https://docs.microsoft.com/en-gb/azure/synapse-analytics/get-started-pipelines)


# [AZURE DATA LAKE](https://github.com/MSRConnections/Azure-training-course/blob/master/Content/Data%20Lake/Azure%20Data%20Lake%20HOL.md)





























