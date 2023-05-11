# AWS Subnets

In Amazon Web Services (AWS), a subnet is a subdivision of a Virtual Private Cloud (VPC) that allows you to segment your VPC's IP address range into smaller, more manageable subranges. Each subnet represents a range of IP addresses that you can use to deploy resources within your VPC. Here's an explanation of subnets and their applications, as well as the difference between VPC and subnets:

A subnet is a logical network segment within a VPC. It is associated with a specific Availability Zone (AZ) in a given region. When creating a subnet, you define an IP address range (CIDR block) that falls within the IP address range of the VPC. Subnets enable you to partition your VPC into smaller network segments, which can have different networking configurations and access controls. Subnets provide the following benefits and applications:

1. Network Segmentation: Subnets allow you to divide your VPC's IP address range into smaller, isolated segments. This provides a way to logically separate different components of your infrastructure, such as frontend and backend servers, databases, and other resources.

2. Availability Zone Isolation: Each subnet is associated with a specific AZ, which ensures that resources deployed within the subnet are located in the same AZ. This enables high availability and fault tolerance by distributing resources across multiple AZs within a region.

3. Security and Access Control: Subnets can be configured with Network Access Control Lists (ACLs) and security groups to control inbound and outbound traffic to resources within the subnet. This allows you to implement fine-grained security policies and restrict network access based on your requirements.

4. Routing and Internet Connectivity: Each subnet has its own route table, which controls the traffic flow between subnets and the internet. You can configure routing rules and internet gateways to enable communication between subnets and external networks.

### Difference between VPC and Subnets:

- VPC: A VPC is the top-level networking construct in AWS. It is a logically isolated section of the AWS cloud where you can launch and manage AWS resources. A VPC defines the IP address range, subnets, routing tables, security settings, and connectivity options for the resources within it.

- Subnets: Subnets are subdivisions within a VPC that define smaller IP address ranges and are associated with specific AZs. Subnets enable network segmentation, control traffic flow, and provide isolation and availability within the VPC. Multiple subnets can exist within a VPC, allowing for the deployment of resources across different network segments.

In summary, a VPC is the overarching network environment in AWS, while subnets are the smaller segments within the VPC that allow for network segmentation, security controls, and resource placement. Subnets are a fundamental building block of a VPC, enabling you to create separate network segments and control the networking aspects of your infrastructure within AWS.

## TYpes of Subnets

In AWS, there are three types of subnets that you can create within a Virtual Private Cloud (VPC):

1. Public Subnets:
   A public subnet is a subnet that is directly accessible from the internet. It is associated with a route table that has a route to an internet gateway, allowing resources within the subnet to have inbound and outbound internet connectivity. Public subnets are typically used for resources that need to be publicly accessible, such as web servers or instances that require direct internet access.

2. Private Subnets:
   A private subnet is a subnet that is not directly accessible from the internet. It is associated with a route table that does not have a route to an internet gateway. Resources within a private subnet can still access the internet by using a network address translation (NAT) gateway or an instance acting as a NAT device. Private subnets are commonly used for resources that do not require direct internet connectivity, such as application servers or backend databases.

3. VPN-only Subnets:
   A VPN-only subnet is a subnet that is not accessible from the internet and does not have a direct internet gateway. It is used when you want to establish connectivity to your VPC through a virtual private network (VPN) connection or AWS Direct Connect. VPN-only subnets are typically used when you need to connect your VPC to an on-premises data center or other external networks securely.

It's important to note that the classification of a subnet as public, private, or VPN-only depends on the associated route table's configuration. By configuring the appropriate routes and route tables, you can control the connectivity options and access levels for resources within different subnets of your VPC.

By using a combination of public, private, and VPN-only subnets within your VPC, you can achieve network segregation, security, and connectivity requirements for your AWS infrastructure.
