# Using PolyBase to load data from Azure storage to Azure SQL Data Warehouse.


### DATA IS INITIALLY STORED IN AZURE BLOB

![image](https://user-images.githubusercontent.com/68102477/128795342-4d717402-baa9-4d33-b02f-e0a05081b2a2.png)

### CONNECT TO SYNAPSE USING VISUAL STUDIO

![image](https://user-images.githubusercontent.com/68102477/128795438-c501ddd8-aa3e-4bfc-a406-14620c062b64.png)

### EXPAND EXTERNAL TABLES 

* USING EXTERNAL TABLES, POLYBASE ALLOWS TO ACCESS AND QUERY DATA STORED OUTSIDE DATABASE

![image](https://user-images.githubusercontent.com/68102477/128795553-4fcae6f9-c4cd-4438-9830-de8ad6d619ca.png)

### STEP 1 - AUTHENTICATE AGAINST AZURE STORAGE ACCOUNT

* GET THE STORAGE KEY FROM AZURE STORAGE ACCOUNT

![image](https://user-images.githubusercontent.com/68102477/128795691-072b6036-1553-432a-a881-cff15241cdca.png)

* CREATE MASTER KEY IN SYNAPSE AND CREATE DATABSE SCOPED CREDENTIAL

![image](https://user-images.githubusercontent.com/68102477/128795720-6c633fd5-e9d7-4978-8c76-729d2aa9e60d.png)

![image](https://user-images.githubusercontent.com/68102477/128795773-284683b1-0c72-42fb-953d-43c7f80ebb3a.png)

### STEP 2 - CREATE EXTERNAL DATA SOURCE 

* BASICALLY WE ARE SPECIFYING LOCATION AND CREDENTIALS FOR AZURE BLOB ACCOUNT
* TYPE - HADOOP BECAUSE POLYBASE USES HADOOP APIs TO ACCESS AZURE STORAGE DATA 

![image](https://user-images.githubusercontent.com/68102477/128795994-0253b475-0d97-4539-b6f9-a410cdb1fc5b.png)

### STEP 3 - 

