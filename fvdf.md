# [AZURE DATA FACTORY TEMPLATES](https://docs.microsoft.com/en-gb/azure/data-factory/solution-templates-introduction)

## [Incrementally load data from a source data store to a destination data store](https://docs.microsoft.com/en-gb/azure/data-factory/tutorial-incremental-copy-overview)

* In a data integration solution, incrementally (or delta) loading data after an initial full data load is a widely used scenario

In this case, you define a watermark in your source database. A watermark is a column that has the last updated time stamp or an incrementing key. The delta loading solution loads the changed data between an old watermark and a new watermark. The workflow for this approach is depicted in the following diagram:

![image](https://user-images.githubusercontent.com/68102477/129472579-00bed116-bff1-42ca-bd38-9cef3b134ddd.png)



## [Create and configure a self-hosted integration runtime](https://docs.microsoft.com/en-us/azure/data-factory/create-self-hosted-integration-runtime?tabs=data-factory)


The [integration runtime (IR)](Integration runtime in Azure Data Factory) is the compute infrastructure that Azure Data Factory and Synapse pipelines use to provide data-integration capabilities across different network environments.

In Data Factory and Synapse pipelines, an activity defines the action to be performed. A linked service defines a target data store or a compute service. An integration runtime provides the bridge between the activity and linked Services. It's referenced by the linked service or activity, and provides the compute environment where the activity either runs on or gets dispatched from. This way, the activity can be performed in the region closest possible to the target data store or compute service in the most performant way while meeting security and compliance needs.

Integration runtime types

Azure
Self-hosted
Azure-SSIS

A self-hosted integration runtime can run copy activities between a cloud data store and a data store in a private network. It also can dispatch transform activities against compute resources in an on-premises network or an Azure virtual network. The installation of a self-hosted integration runtime needs an on-premises machine or a virtual machine inside a private network.


[Create self host IR template](https://github.com/Azure/azure-quickstart-templates/tree/master/quickstarts/microsoft.compute/vms-with-selfhost-integration-runtime)






![image](https://user-images.githubusercontent.com/68102477/130556543-bf888db1-65c4-4ec5-879b-9f596249b0f1.png)





![image](https://user-images.githubusercontent.com/68102477/130556633-b1512b07-21eb-4dfc-be43-4c9ec962f814.png)

![image](https://user-images.githubusercontent.com/68102477/130556613-54c634ab-73d0-43d8-a80b-968f535218fb.png)

### Azure Security Groups | Network and Application Security Groups (NSG, ASG)

![image](https://user-images.githubusercontent.com/68102477/130558415-6cccc95d-c0b2-40a1-a256-3191c0211bfd.png)

* Internet traffic should not be direclty reaching our database.
* Not all services should be able to communicate with each other.
* Create a NSG to block internet traffic to Database but allow internal traffic

![image](https://user-images.githubusercontent.com/68102477/130558713-c14d553c-8a1d-4c07-83fa-592ddd9c7d6e.png)

![image](https://user-images.githubusercontent.com/68102477/130561871-88f10512-9c35-4c11-b3cd-36c21f13478a.png)
* Use  Azure Security Groups to further block traffic from Web Server to DB (Logic server is allowed to send traffic to DB)

![image](https://user-images.githubusercontent.com/68102477/130561983-df439551-a335-4348-95b7-5f7414a7b0dd.png)

![image](https://user-images.githubusercontent.com/68102477/130562155-fdf61321-2f84-4963-bfc0-d50b693d3c62.png)


### Firewall

* MONITORS AND CONTROLS
![image](https://user-images.githubusercontent.com/68102477/130563562-c3cbb906-6f23-4e4f-8d59-90843690268f.png)

Azure Firewall is a managed cloud-based network security service that protects your Azure Virtual Network resources. It is a fully stateful firewall as a service with built-in high availability and unrestricted cloud scalability. You can centrally create, enforce, and log application and network connectivity policies across subscriptions and virtual networks. Azure Firewall uses a static public IP address for your virtual network resources allowing outside firewalls to identify traffic originating from your virtual network. The service is fully integrated with Azure Monitor for logging and analytics. 

* Adding rules in Firewall
![image](https://user-images.githubusercontent.com/68102477/130667175-a600e47f-f0cd-4fd8-a308-7191fd4761e5.png)
* allowing access from subnet
![image](https://user-images.githubusercontent.com/68102477/130667303-c2b4d74c-1b85-4f03-8a90-4ace101b11a2.png)

![image](https://user-images.githubusercontent.com/68102477/130667479-64caf59e-1e42-4c07-aead-8eb5df9bb28b.png)











































 













