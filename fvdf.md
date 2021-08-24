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










































 













