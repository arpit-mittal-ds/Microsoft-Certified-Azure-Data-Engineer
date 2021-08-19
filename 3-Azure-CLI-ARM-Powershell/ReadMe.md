





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








