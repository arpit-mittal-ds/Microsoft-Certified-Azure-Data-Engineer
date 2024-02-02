# 

## Project Introduction

The City of New York would like to develop a Data Analytics platform on Azure Synapse Analytics to accomplish two primary objectives:

1. Analyze how the City's financial resources are allocated and how much of the City's budget is being devoted to overtime.
2. Make the data available to the interested public to show how the City’s budget is being spent on salary and overtime pay for all municipal employees.

You have been hired as a Data Engineer to create high-quality data pipelines that are dynamic, can be automated, and monitored for efficient operation. The project team also includes the city’s quality assurance experts who will test the pipelines to find any errors and improve overall data quality.

The source data resides in Azure Data Lake and needs to be processed in a NYC data warehouse. The source datasets consist of CSV files with Employee master data and monthly payroll data entered by various City agencies.


![image](https://github.com/arpit-mittal-ds/Microsoft-Certified-Azure-Data-Engineer/assets/68102477/33c83cd3-695d-4e2a-8af0-500f97544b8c)

We will be using Azure Data Factory to create Data views in Azure SQL DB from the source data files in DataLake Gen2. Then we built our dataflows and pipelines to create payroll aggregated data that will be exported to a target directory in DataLake Gen2 storage over which Synapse Analytics external table is built. At a high level your pipeline will look like below

![image](https://github.com/arpit-mittal-ds/Microsoft-Certified-Azure-Data-Engineer/assets/68102477/1c938ac4-9c0a-467e-9316-17ea720ea470)
















