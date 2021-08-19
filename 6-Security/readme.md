
# SECURITY

### What is Identity 
* a thing that gets authenticated such as username, email id, etc.

### authentication (AuthN) and authorization (AuthZ)
### What is Authentication
* Process of verification / assertion of identity.

### What is authorization?
Authentication establishes the user's identity, but authorization is the process of establishing what level of access an authenticated person or service has. It specifies what data they're allowed to access and what they can do with it.


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













