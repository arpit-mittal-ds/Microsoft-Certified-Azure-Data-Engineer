
# AZURE DATABRICKS

## CREATE NEW AZURE DATABRICKS INSTANCE
![image](https://user-images.githubusercontent.com/68102477/129675233-4dc0fcee-c9ed-4f33-9cde-66311ffae4fc.png)
## GENERATE DATABRICKS NEW TOKEN
![image](https://user-images.githubusercontent.com/68102477/129678106-790fa244-8ca9-42ec-8f66-4f311abe994e.png)
## ADD THE TOKEN TO THE KEY VAULT
![image](https://user-images.githubusercontent.com/68102477/129678520-2c526f96-c2e8-47f2-8251-290f205795d3.png)
![image](https://user-images.githubusercontent.com/68102477/129679399-c5e2fd63-a749-45e4-8191-3944cfd4c39e.png)
![image](https://user-images.githubusercontent.com/68102477/129679613-da0bae16-2fc5-4704-9451-8cb060ecad4d.png)
![image](https://user-images.githubusercontent.com/68102477/129679651-93f7de81-ec26-49d7-9f5b-8b6d8543506d.png)
## Create linked service for Azure Key Vault
![image](https://user-images.githubusercontent.com/68102477/129680469-b317e8be-e89f-40fd-8579-c74471a20956.png)
![image](https://user-images.githubusercontent.com/68102477/129683654-d631f115-08e2-432a-837d-f53c36ebf7b7.png)
![image](https://user-images.githubusercontent.com/68102477/129683963-df06c91a-92fb-4ba9-ab14-e8a551bd7160.png)
**This linked service contains the connection information to the Databricks cluster:**
![image](https://user-images.githubusercontent.com/68102477/129684258-c98928fb-643a-449d-9793-8f3c7e8b8d82.png)
## [FINALLY CREATE AN AZURE DATA FACTORY PIPELINE THAT EXECUTES A DATABRICKS NOTEBOOK AGAINST THE DATABRICKS JOBS CLUSTER](https://docs.microsoft.com/en-us/azure/data-factory/transform-data-using-databricks-notebook)



