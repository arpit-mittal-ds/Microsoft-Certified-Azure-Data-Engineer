Work with relational data in Azure

Relational databases, and specifically Microsoft SQL Server, have been among the most common tools for handling that data for decades.

If we want to manage our data using the cloud, we can just use Azure virtual machines to host our own Microsoft SQL Server instances. Sometimes that's the right solution, but Azure offers another way that is often much easier and more cost effective. Azure SQL databases are a Platform-as-a-Service (PaaS) offering, meaning much less infrastructure and maintenance to manage yourself.


Why Azure SQL Database is a good choice for running your relational database

Cost and Convenience - With Azure SQL Database, we manage the hardware, software updates, and OS patches for you.
Scale - With Azure SQL Database, you can adjust the performance and size of your database on the fly when your needs change.
Security - Azure SQL Database comes with a firewall that's automatically configured to restrict connections from the Internet. You can allow access to specific IP addresses that you trust. 

Further we will learn:
Which configuration and pricing options are available for your Azure SQL database
How to create an Azure SQL database from the portal
How to use Azure Cloud Shell to connect to your Azure SQL database, add a table, and work with data


finish in next 4 hrs - clock 3 hrs. 6 to 10.-------------------

One server, many databases - When you create your first Azure SQL database, you also create an Azure SQL logical server. Think of a logical server as an administrative container for your databases. You can control logins, firewall rules, and security policies through the logical server. You can also override these policies on each database within the logical server.


Azure SQL Database has two purchasing models: DTU and vCore.
What are DTUs?
DTU stands for Database Transaction Unit, and is a combined measure of compute, storage, and IO resources. Think of the DTU model as a simple, preconfigured purchase option.
Because your logical server can hold more than one database, there's also the idea of eDTUs, or elastic Database Transaction Units. This option enables you to choose one price, but allow each database in the pool to consume fewer or greater resources depending on current load.

What are vCores?
vCores are Virtual cores, which give you greater control over the compute and storage resources that you create and pay for.
While the DTU model provides fixed combinations of compute, storage, and IO resources, the vCore model enables you to configure resources independently. For example, with the vCore model you can increase storage capacity but keep the existing amount of compute and IO throughput.
Your transportation and logistics prototype only needs one Azure

What are SQL elastic pools?
When you create your Azure SQL database, you can create a SQL elastic pool.
SQL elastic pools relate to eDTUs. They enable you to buy a set of compute and storage resources that are shared among all the databases in the pool. Each database can use the resources they need, within the limits you set, depending on current load.

What is Azure Cloud Shell?
