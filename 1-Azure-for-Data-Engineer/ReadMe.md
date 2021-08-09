# Notes

**[Azure for the Data Engineer](https://docs.microsoft.com/en-us/learn/paths/azure-for-the-data-engineer/)**

## Understand the evolving world of data 

Over the last decade, the amount of data that systems and devices generate has increased significantly. Because of this increase, new technologies, roles, and approaches to working with data are affecting data professionals

1. Exponential increase in the number of devices and software that generate data.
2. Data is key - Business stakeholders use data to make business decisions. Consumers use data to make decisions such as what to buy.

Differences between on-premises data technologies and cloud data technologies.

Outline how the role of the data professional is changing in organizations.
Identify use cases that involve these changes.


## Tasks of an Azure data engineer:

* Design and develop data storage and data processing solutions for the enterprise.
* Set up and deploy cloud-based data services such as blob services, databases, and analytics.
* Secure the platform and the stored data. Make sure only the necessary users can access the data.
* Ensure business continuity in uncommon conditions by using techniques for high availability and disaster recovery.
* Monitor to ensure that the systems run properly and are cost-effective.

## Design a data engineering project by following the five phases: source, ingest, prepare, analyze, and consume.

Contoso Health Network recently deployed IoT devices to its intensive care unit (ICU). Here are the goals of the project:

* Capture data on patient biometric monitoring in real time to help physicians treat their patients.
* Store the biometric data so that Contoso's research center can further analyze it in the future.
* Use Azure Machine Learning to understand which treatments improve the quality of care and reduce the likelihood that a patient will be readmitted to the hospital.
* Create a visualization of the data's history for Contoso's chief medical officer.

![image](https://user-images.githubusercontent.com/68102477/128694625-66be149f-c169-454e-ab71-ac1ee8960fed.png)

*  Azure IoT Hub to capture real-time data from the ICU's IoT devices.
*  Azure Stream Analytics to stream and enrich the IoT data, to create windows and aggregations, and to integrate Azure Machine Learning.
*  Azure Data Lake Storage Gen2 to store the biometric data at high speed.
*  Azure Data Factory to perform the extract, load, transform, and load (ELTL) process to move the data from the data lake store to Azure SQL Data Warehouse.
*  Azure SQL Data Warehouse to provide data warehousing services to support the chief medical officer's needs.
*  Power BI to create the patient dashboard. Part of the dashboard will show real-time telemetry about the patient's condition. The other part will show the patient's recent history.
*  Azure Machine Learning to process both raw and aggregated data. Researchers will use this to perform predictive analytics on patient readmittance.




