





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






