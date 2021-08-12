Identity has become the new primary security boundary. Accurately proving that someone is a valid user of your system, with an appropriate level of access, is critical to maintaining control of your data. This identity layer is now more often the target of attack than the network is.


Compare authentication and authorization

Two fundamental concepts that you need to understand when talking about identity and access are authentication (AuthN) and authorization (AuthZ).

Authentication and authorization both support everything else that happens. They occur sequentially in the identity and access process.

For example, all employees can access inventory and pricing software, but only store managers can access payroll and certain accounting software.

What is authentication?
Authentication is the process of establishing the identity of a person or service that wants to access a resource. It involves the act of challenging a party for legitimate credentials and provides the basis for creating a security principal for identity and access control. It establishes whether the user is who they say they are.

What is authorization?
Authentication establishes the user's identity, but authorization is the process of establishing what level of access an authenticated person or service has. It specifies what data they're allowed to access and what they can do with it.

![image](https://user-images.githubusercontent.com/68102477/129080269-832a0d1e-b495-4fb5-b903-9c01e8123fd2.png)

![image](https://user-images.githubusercontent.com/68102477/129120635-3a65ae36-f5f3-484b-888d-4d76ac900593.png)

The identification card represents credentials that the user has to prove their identity (you'll learn more about the types of credentials later in this module.) Once authenticated, authorization defines what kinds of applications, resources, and data that user can access.


What is Azure Active Directory?

Tailwind Traders already uses Active Directory to secure its on-premises environments. The company doesn't want its users to have a different username and password to remember for accessing applications and data in the cloud. Can the company integrate its existing Active Directory instance with cloud identity services to create a seamless experience for its users?

For on-premises environments, Active Directory running on Windows Server provides an identity and access management service that's managed by your own organization. Azure AD is Microsoft's cloud-based identity and access management service.

A tenant is a representation of an organization. A tenant is typically separated from other tenants and has its own identity.


Azure AD provides services such as:

Authentication

This includes verifying identity to access applications and resources. It also includes providing functionality such as self-service password reset, multifactor authentication, a custom list of banned passwords, and smart lockout services.

Single sign-on
What's single sign-on?
Single sign-on enables a user to sign in one time and use that credential to access multiple resources and applications from different providers.

More identities mean more passwords to remember and change
SSO enables you to remember only one username and one password to access multiple applications. A single identity is tied to a user, which simplifies the security model. Application management

You can manage your cloud and on-premises apps by using Azure AD.

Application management

You can manage your cloud and on-premises apps by using Azure AD.

Device management

Along with accounts for individual people, Azure AD supports the registration of devices. 



Connecting Active Directory with Azure AD enables you to provide a consistent identity experience to your users.

There are a few ways to connect your existing Active Directory installation with Azure AD. Perhaps the most popular method is to use Azure AD Connect.


![image](https://user-images.githubusercontent.com/68102477/129120658-1b2e56d5-0659-461b-879a-f1a5c7b0d5d9.png)

![image](https://user-images.githubusercontent.com/68102477/129120675-fe671ae0-059c-469d-a8f2-821dd6fe85ea.png)

![image](https://user-images.githubusercontent.com/68102477/129120706-af0ab132-2f88-4028-b42f-4dd74564a18b.png)

![image](https://user-images.githubusercontent.com/68102477/129120720-97629bdb-fe86-4caa-892f-129ba89cdf2c.png)

![image](https://user-images.githubusercontent.com/68102477/129120729-70b6703c-1ff2-441b-bee1-23d123fe0b92.png)

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




























