# [AZURE DATA FACTORY TEMPLATES](https://docs.microsoft.com/en-gb/azure/data-factory/solution-templates-introduction)

## [Incrementally load data from a source data store to a destination data store](https://docs.microsoft.com/en-gb/azure/data-factory/tutorial-incremental-copy-overview)

* In a data integration solution, incrementally (or delta) loading data after an initial full data load is a widely used scenario

In this case, you define a watermark in your source database. A watermark is a column that has the last updated time stamp or an incrementing key. The delta loading solution loads the changed data between an old watermark and a new watermark. The workflow for this approach is depicted in the following diagram:

![image](https://user-images.githubusercontent.com/68102477/129472579-00bed116-bff1-42ca-bd38-9cef3b134ddd.png)














 













