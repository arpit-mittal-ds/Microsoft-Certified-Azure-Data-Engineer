
# SECURITY

**Zero Trust model** 
which states that you should never assume trust but instead continually validate trust. 

**Defense in depth** using **Layered Approach**
is a strategy that employs a series of mechanisms to slow the advance of an attack that's aimed at acquiring unauthorized access to information. Each layer provides protection so that if one layer is breached, a subsequent layer is already in place to prevent further exposure.

### The common principles that help define a security posture are confidentiality, integrity, and availability, known collectively as CIA.

**Confidentiality:** The principle of least privilege restricts access to information only to individuals explicitly granted access. This information includes protection of user passwords, remote access certificates, and email content.

![image](https://user-images.githubusercontent.com/68102477/130203964-965f5edf-a8e4-49f7-9f65-190bff59e80e.png)



**Integrity:** prevent unauthorized changes to information at rest or in transit. A common approach used in data transmission is for the sender to create a unique fingerprint of the data by using a one-way hashing algorithm. The hash is sent to the receiver along with the data. The receiver recalculates the data's hash and compares it to the original to ensure that the data wasn't lost or modified in transit.

![image](https://user-images.githubusercontent.com/68102477/130204027-ee05914e-a3d1-463e-8033-8d37b32d8074.png)

**Availability:** Ensure that services are available to authorized users. Denial-of-service attacks are a common cause of loss of availability to users. Natural disasters also drive system design to **prevent single points of failure and deploy multiple instances of an application to geo-dispersed locations.**

![image](https://user-images.githubusercontent.com/68102477/130031292-f1bbb218-906d-4b68-a723-e80f1470dcf0.png)

![image](https://user-images.githubusercontent.com/68102477/130203252-3ad909a3-5d85-43d3-9bd1-d6f56963a14e.png)

![image](https://user-images.githubusercontent.com/68102477/130203484-a1fde788-29db-4a0a-8206-346a8cf9147a.png)
![image](https://user-images.githubusercontent.com/68102477/130203506-fe7e1bd1-2c0f-4f82-a76a-22c52bbbb022.png)
![image](https://user-images.githubusercontent.com/68102477/130203602-8318c948-4556-40f4-97d2-42da1439d106.png)
![image](https://user-images.githubusercontent.com/68102477/130203644-3e107026-9468-4804-a265-4a4c3369ef74.png)
![image](https://user-images.githubusercontent.com/68102477/130203729-a20acf54-03d0-455b-b7f9-ecc0912eab1d.png)
![image](https://user-images.githubusercontent.com/68102477/130203800-641921d4-0692-401f-8e89-0167cdf64394.png)
![image](https://user-images.githubusercontent.com/68102477/130203836-f4d42778-5dd8-43ec-b969-328e15683f97.png)







### Single sign-on
The more identities a user has to manage, the greater the risk of a credential-related security incident. 

### SSO with Azure Active Directory
Azure AD is a cloud-based identity service. It has built-in support for synchronizing with your on-premises Active Directory instance, or it can be used on its own. This means that all your applications, whether on-premises, in the cloud (including Microsoft 365), or even mobile, can share the same credentials. Administrators and developers can control access to data and applications by using centralized rules and policies configured in Azure AD.


### Role-based access control (RBAC)
Roles are defined as collections of access permissions or sets of permissions, like read-only or contributor, that users can be granted to access an Azure service instance.
 
On Azure, users, groups, and roles are all stored in Azure Active Directory (Azure AD). The Azure Resource Manager API uses role-based access control to secure all resource access management within Azure.

Consider the use of Sudo on a Bash prompt OR on Windows via Run as administrator. In both of those cases, you're still signed in as the same identity as before, but you've changed your role and hence your access permissions.
 
### WHAT IS A SERVICE PRINCIPAL?

An identity is just a thing that can be authenticated. Obviously, this includes users with usernames and passwords. But it can also include applications or other servers, which might authenticate with secret keys or certificates.

**A service principal is an identity that a service or application uses.** Like other identities, it can be assigned roles.
  
For example, your organization can assign its deployment scripts to run authenticated as a service principal. If that's the only identity that has permission to perform destructive actions, your organization has gone a long way towards making sure that the accidental resource deletion do not happen.

### what is MANAGED IDENTITY
The creation of service principals can be a tedious process. There are also many touch points that can make maintaining service principals difficult. Managed identities for Azure resources are much easier and will do most of the work for you.

**A managed identity** can be instantly created for any Azure service that supports it. (The list is constantly growing.) When you create a managed identity for a service, you're creating an account on the Azure AD tenant. Azure infrastructure will automatically take care of authenticating the service and managing the account. You can then use that account like any other Active Directory account, including letting the authenticated service securely access other Azure resources.
 
 
### What is encryption?
Encryption is the process of making data unreadable and unusable. To use or read the encrypted data, it must be decrypted, which requires the use of a secret key. There are two top-level types of encryption: symmetric and asymmetric.

**Symmetric encryption** uses the same key to encrypt and decrypt the data. Consider a password manager application. You enter your passwords, and they're encrypted with your own personal key. (Your key is often derived from your master password.) When the data needs to be retrieved, the same key is used and the data is decrypted.

**Asymmetric encryption** uses a public key and private key pair. Either key can encrypt but can't decrypt its own encrypted data. To decrypt, you need the paired key. Asymmetric encryption is used for things like TLS (used in HTTPS) and data signing.
 
### WHAT IS ENCRYPTION AT REST?
 Regardless of the storage mechanism, encryption of data at rest ensures that the stored data is unreadable without the keys and secrets needed to decrypt it. If an attacker obtained a hard drive with encrypted data and didn't have access to the encryption keys, the attacker would have great difficulty compromising the data. 
 
### WHAT IS ENCRYPTION IN TRANSIT?
Data in transit is the data that's actively moving from one location to another, such as across the internet or through a private network. An organization can handle secure transfer by encrypting the data before sending it over a network, or setting up a secure channel to transmit unencrypted data between two systems. 

### Identify and classify data

 The organization needs to start by identifying and classifying the types of data that it's storing, and align this with the business and regulatory requirements for the storage of data.
 
 ![image](https://user-images.githubusercontent.com/68102477/130044012-cde651bd-9ddc-453c-9dd6-23455e38b9d7.png)


### What is Identity 
* a thing that gets authenticated such as username, email id, etc.

### authentication (AuthN) and authorization (AuthZ)
### What is Authentication
* Process of verification / assertion of identity.

### What is authorization?
Authentication establishes the user's identity, but authorization is the process of establishing **what level of access** an authenticated person or service has. It specifies **what data they're allowed to access** and what they can do with it.

**Examples**

**Encrypting raw storage** - Azure Storage encryption for data at rest helps you protect your data to meet your organizational security and compliance commitments. The Azure Storage platform automatically encrypts your data with 256-bit Advanced Encryption Standard (AES) encryption before persisting it to disk and then decrypts the data during retrieval.

### AZURE KEY VAULT

**Encrypting secrets** - We've seen that the encryption services all use keys to encrypt and decrypt data. How do we ensure that the keys themselves are secure? You might also have passwords, connection strings, or other sensitive pieces of information that you need to securely store.


### What is Azure Key Vault?

**Azure Key Vault is a cloud service that works as a secure store for secrets**

Azure Key Vault is a secret store: **a centralized cloud service for storing app secrets - configuration values like passwords and connection strings** that must remain secure at all times. Key Vault helps you control your apps' secrets by keeping them in a single central location and providing secure access, permissions control, and access logging.

What is a secret in Key Vault?
In Key Vault, a secret is a name-value pair of strings.

Key Vault's API uses Azure Active Directory to authenticate users and apps. 

Create Key Vaults for your applications
A best practice is to create a separate vault for each deployment environment of each of your applications, such as development, test, and production.

![image](https://user-images.githubusercontent.com/68102477/130159744-0eba9aba-43f4-4d2f-bef6-1dfd924922f4.png)


### Problems with Classic Approach of Client and Server Authentication
![image](https://user-images.githubusercontent.com/68102477/129502674-591de703-0f13-42d1-ae1b-bc3e18d79ff4.png)

![image](https://user-images.githubusercontent.com/68102477/129502711-df17ec50-45d9-47e7-8b1e-a9801e803ce1.png)

### Using Azure AD for Identity Management or Authenticatiion between Client and Server

![image](https://user-images.githubusercontent.com/68102477/129502875-71532a4e-4a29-4702-90a8-c1c6ea0715d4.png)

![image](https://user-images.githubusercontent.com/68102477/129502946-54f0f91e-ede8-41ae-844d-02767f940159.png)


## What is Azure Active Directory?

* Azure AD is Microsoft's cloud-based identity and access management service.

* A tenant is a representation of an organization. A tenant is typically separated from other tenants and has its own identity.

**Azure AD provides services such as:**

**Authentication** - verifying identity to access applications and resources. It also includes providing functionality such as self-service password reset, multifactor authentication, a custom list of banned passwords, and smart lockout services.

**Single sign-on** - enables a user to sign in one time and use that credential to access multiple resources and applications from different providers. A single identity is tied to a user, which simplifies the security model. 


### We already use Azure AD to do a single-sign-on while using various Microsoft's Services
### Basically if we have logged on to one service then we do not require to log on to another one
![image](https://user-images.githubusercontent.com/68102477/129502270-d03c51df-e793-4e3e-b78b-78f624c2fd65.png)

### Again in Azure CLoud resources we use Azure AD CENTRALIZED service to authenticate to various Azure cloud resources
![image](https://user-images.githubusercontent.com/68102477/129502356-3afa5331-89b9-4652-bc4c-f0a3d8d97f68.png)

### Demo

* CREATE A NEW ACTIVE DIRECTORY
* ASSOCIATE THE EXISTING SUBSCRIPTION TO THE NEW ACTIVE DIRECTORY

![image](https://user-images.githubusercontent.com/68102477/129505604-c7442474-b809-4519-bd29-9ba751b203b2.png)

![image](https://user-images.githubusercontent.com/68102477/129505623-45ced121-27dc-4bce-8de6-4635fb0bfa3b.png)

![image](https://user-images.githubusercontent.com/68102477/129506026-6e1699e9-2aae-47be-a6ea-27e3fbda9156.png)



### [Relationship between Subscription and Active Directory](https://docs.microsoft.com/en-gb/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory?amp;clcid=0x9)

**Newly Created Active Directory (and associated tenant and organization) will not have access to the Subscription present in previous Default Directory
![image](https://user-images.githubusercontent.com/68102477/129506461-b73fdcb8-9cfe-4c1e-9cb0-8d4951beb863.png)

* Multiple Azure subscriptions can establish a trust relationship with an instance of Azure Active Directory (Azure AD) in order to authenticate and authorize security principals and devices against Azure services.  
* Each subscription can only trust a single directory.
* When a user signs up for a Microsoft cloud service - Azure, a new default Azure AD tenant is created and the user is made a member of the Global Administrator role. 

![image](https://user-images.githubusercontent.com/68102477/129507294-b8f1ccb7-df19-45f0-9865-f79838f98b0d.png)

### Subscription: A logical container for your resources. 
* Each Azure resource is associated with only one subscription. 

**Azure account:** The email address that you provide when you create an Azure subscription is the Azure account for the subscription. The party that's associated with the email account is responsible for the monthly costs that are incurred by the resources in the subscription. **Each subscription is associated with only one Azure account.**

**Azure AD tenant:** A dedicated and trusted instance of Azure AD. An Azure AD tenant is automatically created when your organization first signs up for a Microsoft cloud service subscription like Microsoft Azure. An Azure tenant represents a single organization.

**Resource groups:** Logical containers that you use to group related resources in a subscription. Each resource can exist in only one resource group. 1 Subscription can have multiple Resource groups, representing a grouping within a subscription, and are commonly used to represent a collection of assets required to support a workload, application, or specific function within a subscription.

### Associate a subscription to a directory
**It can take several hours for the Subscrition to switch to the new Active Directory**
![image](https://user-images.githubusercontent.com/68102477/129507718-90b33e71-a46e-487b-b4ef-42fb3cffea1f.png)


### Create a new user

![image](https://user-images.githubusercontent.com/68102477/129646761-8e539e93-f8bb-4a15-9f86-13b9c0f74829.png)



### What is network security?
Network security is protecting the communication of resources within and outside your network. The goal is to limit exposure at the network layer across your services and systems. 

![image](https://user-images.githubusercontent.com/68102477/130046465-801a61c7-7131-407c-8159-0a8f1f04d53c.png)

![image](https://user-images.githubusercontent.com/68102477/130046640-f814b9f3-b7db-4331-9636-46bd4c1786f4.png)

Virtual network security
Inside a virtual network, it's important to limit communication between resources to only what's required.

For communication between virtual machines, network security groups are a critical piece to restrict unnecessary communication. 







### [Secure your Azure Storage account](https://docs.microsoft.com/en-us/learn/modules/secure-azure-storage-account/2-storage-security-features)

**1. Protect the data at rest**
 - All data written to Azure Storage is automatically encrypted by Storage Service Encryption (SSE) with a 256-bit Advanced Encryption Standard (AES) cipher
 -  It can't be disabled.
 -  Azure Key Vault stores the keys automatically to help you control and manage the disk-encryption keys and secrets.

![image](https://user-images.githubusercontent.com/68102477/129651144-82d808a4-2468-46c4-ad00-9c107dcd8e25.png)


**2. Protect the data in transit**
 - Has to be ENABLED
 - After you enable secure transfer, connections that use HTTP will be refused. 
 - HTTPS have to be used, by the APIs, after TLS has been enabled


**3. Control who can access data - ACCOUNT KEY vs SHARED ACCESS SIGNATURE**

**3.A. Storage account keys – for admin only**

In Azure Storage accounts, shared keys are called storage account keys. Azure creates two of these keys (primary and secondary) for each storage account you create. The keys give access to everything in the account.
You'll find the storage account keys in the Azure portal view of the storage account. Just select Settings > Access keys.
Because these keys are powerful, use them only with trusted in-house applications that you control completely. If the keys are compromised, change the key values in the Azure portal. 
Only for admin - Not for Storage Users.
Re-generate periodically.
Never share with external third party Apps. Use SAS instead.

* The client embeds the shared key in the HTTP Authorization header of every request, and the Storage account validates the key.

![image](https://user-images.githubusercontent.com/68102477/129652051-00557881-3743-4fa4-b255-05f51c3c435c.png)
You can easily authenticate and access Azure Data Lake Storage Gen2 (ADLS Gen2) storage accounts using an Azure storage account access key

**[Example of using account keys](https://docs.databricks.com/data/data-sources/azure/adls-gen2/azure-datalake-gen2-get-started.html)

**3.B. shared access signature (SAS)** is a URI that grants restricted access rights to Azure Storage resources. You can provide a shared access signature to clients who should not be trusted with your storage account key but whom you wish to delegate access to certain storage account resources. By distributing a shared access signature URI to these clients, you grant them access to a resource for a specified period of time.

**4. Audit storage access**




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
![image](https://user-images.githubusercontent.com/68102477/129703302-2b782282-bf8f-4018-bbeb-d0844087d37f.png)
![image](https://user-images.githubusercontent.com/68102477/129704300-8f293915-6590-4547-86d7-6404fa7eeb15.png)
![image](https://user-images.githubusercontent.com/68102477/129705427-9a3855e3-9314-4a5d-b685-4095902fd0d6.png)
![image](https://user-images.githubusercontent.com/68102477/129707595-a5ea426c-cd25-4129-88ad-a186c167f13f.png)
![image](https://user-images.githubusercontent.com/68102477/129710411-45d977bd-c68c-47ad-86a6-22d012257dc8.png)





# AZURE SECURITY CENTER

![image](https://user-images.githubusercontent.com/68102477/130155765-2ffc84ba-a671-4109-a806-e700c7feac7e.png)


# AZURE SENTINEL
* Collects and Aggregates security data 
* Detect Threats
* Investigate threads using AI
* Respond to incidents using built in analytics

![image](https://user-images.githubusercontent.com/68102477/130156121-de20f7be-8c7a-4e09-a08c-35f600736b7e.png)

## FIREWALL

Is a network security device that **monitors** incoming and outgoing network **traffic** and decides whether to allow or block traffic based on defined set of security rules. 
Example: 
Allow traffic only from a range of IP addresses.
only allow Specific network protocol 
![image](https://user-images.githubusercontent.com/68102477/130205660-56cbc19a-40e4-43c3-8213-2a6cca7ea44a.png)
![image](https://user-images.githubusercontent.com/68102477/130205884-8328f7a1-e1f1-4704-b2d0-a1b5a4c13ab6.png)

### DDoS
![image](https://user-images.githubusercontent.com/68102477/130206071-1d5a0578-9be9-4359-86ac-c0ffdd475950.png)

![image](https://user-images.githubusercontent.com/68102477/130206170-1049c2b9-49a3-4551-b025-0f882ca38118.png)
![image](https://user-images.githubusercontent.com/68102477/130206208-03beab46-0733-4a48-8f72-b5430c680f49.png)
![image](https://user-images.githubusercontent.com/68102477/130206389-3aa05671-a02c-4505-8cbf-4c30f8a6f61c.png)

### Filter network traffic by using NETWORK SECURITY GROUPS(a kind of firewall)

* Basically NSG will contain multiple inbound and outboud security rules that enable us to filter traffic.
![image](https://user-images.githubusercontent.com/68102477/130206641-15467f33-e0e1-4c4f-8403-5a1734fae8b9.png)
* Each RULE specifies following properties:
![image](https://user-images.githubusercontent.com/68102477/130206756-11c3493d-66fb-45d3-91b6-ba029354dec3.png)

### [Exercise - Configure network access to a VM by using a network security group](https://docs.microsoft.com/en-us/learn/modules/secure-network-connectivity-azure/6-configure-access-network-security-group)

1. Create a Linux VM and installing Nginx, a popular web server, on that VM. 
2. To make your web server accessible, you then create a network security group (NSG) rule that allows inbound access on port 80 (HTTP). 

![image](https://user-images.githubusercontent.com/68102477/130210424-d3d0f249-a748-409a-8a9e-885173fb181d.png)





