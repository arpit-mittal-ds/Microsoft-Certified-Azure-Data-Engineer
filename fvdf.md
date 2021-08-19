# [AZURE DATA FACTORY TEMPLATES](https://docs.microsoft.com/en-gb/azure/data-factory/solution-templates-introduction)

## [Incrementally load data from a source data store to a destination data store](https://docs.microsoft.com/en-gb/azure/data-factory/tutorial-incremental-copy-overview)

* In a data integration solution, incrementally (or delta) loading data after an initial full data load is a widely used scenario

In this case, you define a watermark in your source database. A watermark is a column that has the last updated time stamp or an incrementing key. The delta loading solution loads the changed data between an old watermark and a new watermark. The workflow for this approach is depicted in the following diagram:

![image](https://user-images.githubusercontent.com/68102477/129472579-00bed116-bff1-42ca-bd38-9cef3b134ddd.png)



## Data Centers and Regions

![image](https://user-images.githubusercontent.com/68102477/130002983-96a70de6-33b9-40f4-9b37-b24532893b9f.png)

### Data Centers around the world
![image](https://user-images.githubusercontent.com/68102477/130003031-d0f6e986-1858-4fd9-9168-dda462b7268c.png)

![image](https://user-images.githubusercontent.com/68102477/130003169-5b4f5832-3688-4913-bed0-3582ec9f915d.png)

![image](https://user-images.githubusercontent.com/68102477/130008055-a32d2215-8825-4ea8-880b-a3892f01a8f3.png)





## VIRTUAL NETWORK

![image](https://user-images.githubusercontent.com/68102477/130000259-f907a8ff-18db-44c8-b064-9d715af15666.png)

![image](https://user-images.githubusercontent.com/68102477/130000405-4a17bef1-821c-4b06-a723-0595ffd2e718.png)

### Grouping Virtual Machines into Subnets and then Virtual Networks
* 1 VNet can have resources only in one region
![image](https://user-images.githubusercontent.com/68102477/130014230-841f64ee-21cc-4e19-a1d5-358e73818ba7.png)


### Infrastructure Diagram with VNET and its Subnet
![image](https://user-images.githubusercontent.com/68102477/130002786-b10a10d7-f0b6-4f2b-83c0-ee92c61bdea5.png)


6 PM to 10 AM - 1 hr dinner 7 hrs sleep 1hr breakfast - 16-9= 7 hrs study

# SECURITY

**Zero Trust model** 
which states that you should never assume trust but instead continually validate trust. 

**Defense in depth** using **Layered Approach**
is a strategy that employs a series of mechanisms to slow the advance of an attack that's aimed at acquiring unauthorized access to information. Each layer provides protection so that if one layer is breached, a subsequent layer is already in place to prevent further exposure.

### The common principles that help define a security posture are confidentiality, integrity, and availability, known collectively as CIA.

**Confidentiality:** The principle of least privilege restricts access to information only to individuals explicitly granted access. This information includes protection of user passwords, remote access certificates, and email content.

**Integrity:** prevent unauthorized changes to information at rest or in transit. A common approach used in data transmission is for the sender to create a unique fingerprint of the data by using a one-way hashing algorithm. The hash is sent to the receiver along with the data. The receiver recalculates the data's hash and compares it to the original to ensure that the data wasn't lost or modified in transit.

**Availability:** Ensure that services are available to authorized users. Denial-of-service attacks are a common cause of loss of availability to users. Natural disasters also drive system design to **prevent single points of failure and deploy multiple instances of an application to geo-dispersed locations.**

![image](https://user-images.githubusercontent.com/68102477/130031292-f1bbb218-906d-4b68-a723-e80f1470dcf0.png)


Single sign-on
The more identities a user has to manage, the greater the risk of a credential-related security incident. 

SSO with Azure Active Directory
Azure AD is a cloud-based identity service. It has built-in support for synchronizing with your on-premises Active Directory instance, or it can be used on its own. This means that all your applications, whether on-premises, in the cloud (including Microsoft 365), or even mobile, can share the same credentials. Administrators and developers can control access to data and applications by using centralized rules and policies configured in Azure AD.

Infrastructure protection

 It's critical to ensure that people and processes have only the rights they need to get their job done. Assigning incorrect access can result in data loss, data leakage, or unavailability of services.
 

Role-based access control (RBAC)
Roles are defined as collections of access permissions or sets of permissions, like read-only or contributor, that users can be granted to access an Azure service instance.
 

 
 On Azure, users, groups, and roles are all stored in Azure Active Directory (Azure AD). The Azure Resource Manager API uses role-based access control to secure all resource access management within Azure.
 
### Service principals

An identity is just a thing that can be authenticated. Obviously, this includes users with usernames and passwords. But it can also include applications or other servers, which might authenticate with secret keys or certificates.

**A service principal is an identity that a service or application uses.** Like other identities, it can be assigned roles.
 
Consider the use of Sudo on a Bash prompt OR on Windows via Run as administrator. In both of those cases, you're still signed in as the same identity as before, but you've changed your role and hence your access permissions.
 
For example, your organization can assign its deployment scripts to run authenticated as a service principal. If that's the only identity that has permission to perform destructive actions, your organization has gone a long way toward making sure that the accidental resource deletion cannothappen.


 
 
 
 
 
 













