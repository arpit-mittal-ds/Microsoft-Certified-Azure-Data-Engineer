
A virtual private network (VPN) is a type of private interconnected network. 

VPNs use an encrypted tunnel within another network. They're typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public Internet). Traffic is encrypted while traveling over the untrusted network to prevent eavesdropping or other attacks.







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


A virtual private network (VPN) is a type of private interconnected network. VPNs use an encrypted tunnel within another network. They're typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public Internet). Traffic is encrypted while traveling over the untrusted network to prevent eavesdropping or other attacks.

VPNs can enable us to share sensitive information between locations.

Azure VPN gateways
A VPN gateway is a type of Virtual Network Gateway. VPN gateways are deployed in Azure virtual networks and enable the following connectivity:

Connect on-premises datacenters to Azure virtual networks through a site-to-site connection.
Connect individual devices to Azure virtual networks through a point-to-site connection.
Connect Azure virtual networks to other Azure virtual networks through a network-to-network connection.
Visualization of a VPN connection to Azure.

![image](https://user-images.githubusercontent.com/68102477/130187416-bb4eaf75-50f7-4fa5-a56a-0954f5f6c577.png)

You can deploy only one VPN gateway in each virtual network, but you can use one gateway to connect to multiple locations, including other Azure virtual networks or on-premises datacenters.

When you deploy a VPN gateway, you specify the VPN type: either policy-based or route-based. The main difference of these two types of VPNs is how traffic to be encrypted is specified

## Deploy VPN gateways

Before you can deploy a VPN gateway, you'll need some Azure and on-premises resources.

Required Azure resources

Virtual network. Deploy an Azure virtual network with enough address space for the additional subnet that you'll need for the VPN gateway. 

GatewaySubnet. Deploy a subnet called GatewaySubnet for the VPN gateway. Use at least a /27 address mask to make sure you have enough IP addresses in the subnet for future growth. 

Public IP address. 


Local network gateway. 

Virtual network gateway. Create the virtual network gateway to route traffic between the virtual network and the on-premises datacenter or other virtual networks. 

Connection. Create a Connection resource to create a logical connection between the VPN gateway and the local network gateway.

![image](https://user-images.githubusercontent.com/68102477/130187817-03c2a6b6-adaf-48bb-9d33-2d2c5cb09faa.png)






































