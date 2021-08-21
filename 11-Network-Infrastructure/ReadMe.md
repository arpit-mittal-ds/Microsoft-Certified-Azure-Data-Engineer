
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



# ARCHITECT NETWORK INFRASTRUCTURE IN AZURE

* You can put multiple VMs in a VNet (Virtual Network) and can let them communicate. Also you can put other services in that VNet.
![image](https://user-images.githubusercontent.com/68102477/130219946-b646f4d0-b3f9-4a7b-8fcb-f60027e6f9ba.png)

* While creating a VNet you specify a range of IP Addresses for the VMs.
![image](https://user-images.githubusercontent.com/68102477/130220130-13fc4196-1e72-4f5d-a04c-acda2df2ec96.png)


![image](https://user-images.githubusercontent.com/68102477/130220320-e59ad934-02da-4c86-b465-e7e8769c2411.png)

![image](https://user-images.githubusercontent.com/68102477/130220372-422d18ff-5342-4701-991e-68746b3acd4c.png)

Address space '10.0.0.0/16' overlaps with address space '10.0.0.0/16' of virtual network 'VNET1'. Virtual networks with overlapping address space cannot be peered. If you intend to peer these virtual networks, change address space '10.0.0.0/16'.
Peered virtual network address space

![image](https://user-images.githubusercontent.com/68102477/130220641-51c923d7-c9be-4372-992d-6d6d516f66fd.png)


![image](https://user-images.githubusercontent.com/68102477/130220761-7c11e466-3ce8-4c35-bf7a-bd76b48a8faf.png)

![image](https://user-images.githubusercontent.com/68102477/130220815-78d49cb4-a4a1-4a6b-9afe-5bf9a63bded0.png)

### [SERVICE ENDPOINTS](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview)
* Endpoints allow you to secure your critical Azure service resources to only your virtual networks. 
* Service Endpoints enables private IP addresses in the VNet to reach the endpoint of an Azure service **without needing a public IP address**.

![image](https://user-images.githubusercontent.com/68102477/130227735-f3055a24-2cbd-474f-9e1f-a2cacd01ad3c.png)

**With service end point configured the traffic from VM (in a subnet) 
![image](https://user-images.githubusercontent.com/68102477/130229077-b9e1e03a-8ec6-405f-9865-f3750a380ea8.png)

![image](https://user-images.githubusercontent.com/68102477/130229283-3cc84b0e-cfd9-4613-a578-65b7142f9168.png)

* service endpoint is connected from a subnet

* difference b/w service enpoint and private endpoint

* private endpoint is only for a particular service...not to whole account
* private endpoint connection is via NIC

![image](https://user-images.githubusercontent.com/68102477/130236536-3a4a7972-2f88-4c51-b60b-9a2c7ab6f8e0.png)

What is a subnet?
A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient. Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

![image](https://user-images.githubusercontent.com/68102477/130311477-32141d0e-195b-4cb0-a073-5b73b937435a.png)


What do the different parts of an IP address mean?
This section focuses on IPv4 addresses, which are presented in the form of four decimal numbers separated by periods, like 203.0.113.112
Every IP address has two parts. The first part indicates which network the addre
Why is subnetting necessary?
As the previous example illustrates, the way IP addresses are constructed makes it relatively simple for Internet routers to find the right network to route data into. However, in a Class A network (for instance), there could be millions of connected devices, and it could take some time for the data to find the right device. This is why subnetting comes in handy: subnetting narrows down the IP address to usage within a range of devices.ss belongs to. The second part specifies the device within that network. However, the length of the "first part" changes depending on the network's class.

### [Prepare Azure and on-premises virtual networks by using Azure CLI commands](https://docs.microsoft.com/en-us/learn/modules/connect-on-premises-network-with-vpn-gateway/3-exercise-prepare-azure-and-on-premises-vnets-using-azure-cli-commands?ns-enrollment-type=LearningPath&ns-enrollment-id=learn.architect-network-infrastructure)


deploy a site-to-site VPN

This VPN will allow your on-premises servers to connect to resources in Azure. 

![image](https://user-images.githubusercontent.com/68102477/130302869-675e2587-94ae-452a-b7af-94befdeae327.png)

![image](https://user-images.githubusercontent.com/68102477/130303597-4062155f-c989-4058-afc8-a9e010d5191d.png)

CREATE THE AZURE-SIDE RESOURCES
* create the Azure-VNet-1 virtual network and the Services subnet
* add the subnet (GatewaySubnet) to vnet - Azure-VNet-1 
* create the LNG-HQ-Network LOCAL network gateway -ip-address 94.0.252.160 (This gateway represents the on-premises network that you're connecting to)

CREATE THE SIMULATED ON-PREMISES NETWORK AND SUPPORTING RESOURCES
* create the HQ-Network virtual network and the Applications subnet.
* add subnet (GatewaySubnet) to vnet - HQ-Network ----same subnet is added to this VM as well.
* create the LNG-Azure-VNet-1 LOCAL network gateway. --gateway-ip-address 94.0.252.160 - ip address is same

Create the Azure-side VPN gateway
* create the PIP-VNG-Azure-VNet-1 public IP address
* create the VNG-Azure-VNet-1 virtual network
* create the VNG-Azure-VNet-1 VIRTUAL network gateway.


Create the on-premises VPN gateway
* create the PIP-VNG-HQ-Network public IP address
* create the VNG-HQ-Network virtual network
* create the VNG-HQ-Network virtual network gateway.

Update the local network gateway IP references




![image](https://user-images.githubusercontent.com/68102477/130312544-b3be6b7c-f603-46f4-aa5e-d2b28265ae55.png)











 

















