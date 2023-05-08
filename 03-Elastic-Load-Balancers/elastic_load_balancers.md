# Elastic Load Balancers

## Cloud approaches with AWS cloud provider

Cloud computing is a model for delivering on-demand computing resources over the internet. There are different cloud service models like Infrastructure as a Service (IaaS), Platform as a Service (PaaS), and Software as a Service (SaaS). In this response, I will explain IaaS and PaaS with examples from the Amazon Web Services (AWS) cloud provider.

1. Infrastructure as a Service (IaaS) is a cloud computing model in which cloud providers offer virtualized computing resources over the internet, such as virtual machines (VMs), storage, and network infrastructure. With IaaS, customers can scale up or down their computing resources as needed, and they only pay for what they use. In this model, the customer is responsible for managing the operating system, middleware, and applications running on top of the infrastructure provided by the cloud provider.

   AWS provides several IaaS services, including Amazon Elastic Compute Cloud (EC2), Amazon Simple Storage Service (S3), and Amazon Virtual Private Cloud (VPC). EC2 allows users to create virtual machines on the AWS infrastructure, while S3 provides scalable object storage for files, images, and videos. VPC allows customers to create a private network within the AWS cloud, which they can configure and control.

2. Platform as a Service (PaaS) is a cloud computing model in which cloud providers offer a platform for developing, testing, and deploying applications over the internet. In this model, the cloud provider manages the underlying infrastructure and operating system, while the customer is responsible for managing the applications and data. With PaaS, customers can quickly build and deploy applications without worrying about the underlying infrastructure.

   AWS provides several PaaS services, including AWS Elastic Beanstalk, AWS Lambda, and AWS App Runner. Elastic Beanstalk is a fully managed service for deploying web applications, while Lambda is a serverless computing service that allows customers to run code without managing the underlying infrastructure. App Runner is a fully managed service for deploying containerized applications, providing an easy-to-use interface for building and deploying applications.

In summary, IaaS provides customers with virtualized computing resources over the internet, while PaaS provides a platform for developing, testing, and deploying applications over the internet. AWS provides several IaaS and PaaS services, allowing customers to choose the best approach for their specific needs.

## Elastic Load Balancer

Elastic Load Balancer (ELB) is a service provided by Amazon Web Services (AWS) that distributes incoming traffic across multiple targets, such as Amazon Elastic Compute Cloud (EC2) instances or containers, in multiple Availability Zones to improve the availability and scalability of applications.

ELB works by automatically detecting healthy targets and routing traffic to them, while also detecting and automatically removing unhealthy targets. ELB can also automatically scale up or down the number of targets based on the incoming traffic, providing automatic load balancing and scaling capabilities for applications.

There are three types of ELBs provided by AWS:

1. Classic Load Balancer: This is the original ELB service, which is designed to provide basic load balancing capabilities for applications running on EC2 instances. It supports both HTTP and HTTPS protocols and can distribute traffic across multiple EC2 instances.

2. Application Load Balancer: This is a more advanced ELB service that operates at the application layer (Layer 7) of the OSI model. It supports advanced routing capabilities, including host- and path-based routing, and provides support for containerized applications running on Amazon Elastic Container Service (ECS).

3. Network Load Balancer: This is the newest ELB service and operates at the transport layer (Layer 4) of the OSI model. It provides high-performance load balancing for TCP and UDP traffic, making it ideal for applications that require high throughput, low latency, and high scalability.

4. Gateway Load Balancer (used to Deploy, scale, and run third-party virtual appliances). Gateway Load Balancer helps you easily deploy, scale, and manage your third-party virtual appliances. It gives you one gateway for distributing traffic across multiple virtual appliances while scaling them up or down, based on demand. This decreases potential points of failure in your network and increases availability.

Overall, ELB is a powerful tool that helps to improve the availability, scalability, and performance of applications running on AWS. It provides automatic load balancing and scaling capabilities that help to ensure that applications can handle incoming traffic and remain highly available, even during periods of high demand.

### Steps to create ELB to target 2 instances

Here are the high-level steps to create an Elastic Load Balancer (ELB) in AWS and configure it to target two instances:

1. Log in to the AWS Management Console and navigate to the EC2 dashboard.

2. Launch two EC2 instances in the same region, in separate Availability Zones.

3. Create a security group for the instances that allows inbound traffic on the ports you want to use for the application.

4. Create a target group for the instances that will be the target of the ELB. Choose the protocol, port, and health check settings for the target group.

5. Register the two instances with the target group.

6. Create a new load balancer and choose the type of load balancer you want to create (Application Load Balancer or Network Load Balancer).

7. Configure the load balancer settings, including the listener protocol and port.

8. In the Configure Routing screen, add a new target group and select the target group created in step 4 as the target group for the load balancer.

9. Configure the health check settings for the load balancer to monitor the health of the instances in the target group.

10. Configure any additional settings for the load balancer, such as security groups or SSL/TLS certificates.

11. Review and create the load balancer.

12. Wait for the load balancer to become active and then test it by connecting to the load balancer's DNS name and verifying that traffic is distributed evenly across the two instances.

These are the high-level steps to create an Elastic Load Balancer and configure it to target two instances in AWS. Note that there may be additional configuration steps required depending on the specific needs of your application.

## Scalability

Scalability is the ability of a system to handle increasing amounts of work, traffic, or data by adding or removing resources. There are two types of scalability: horizontal and vertical.

1. Horizontal Scaling: In horizontal scaling, additional resources are added to a system in order to handle increasing load or traffic. This can be achieved by adding more servers, instances, or containers to a system. The aim of horizontal scaling is to distribute the load across multiple resources, which increases the overall capacity of the system.

   For example, consider an e-commerce website that experiences high traffic during the holiday season. To handle the increased traffic, the website can horizontally scale by adding more instances of its web servers. Each instance would handle a portion of the incoming traffic, allowing the website to handle more overall traffic.

2. Vertical Scaling: In vertical scaling, resources are added to or removed from a single instance of a system in order to handle increasing or decreasing load. This can be achieved by upgrading the hardware specifications of the system, such as increasing the CPU, memory, or storage capacity.

   For example, consider a database that is becoming slow due to increased traffic. Instead of adding more instances of the database, the database can be vertically scaled by upgrading the hardware specifications of the single instance. This would allow the database to handle more incoming queries and transactions, without requiring additional instances.

In summary, horizontal scaling adds more resources to a system to handle increased traffic, while vertical scaling increases the resources of a single instance to handle increased traffic. Both approaches are useful for achieving scalability in different scenarios, and often a combination of both horizontal and vertical scaling is used to achieve optimal performance and scalability.

## Tenancy

Tenancy refers to the level of isolation provided by the underlying infrastructure of a cloud computing environment. There are three types of tenancy in cloud computing:

1. Shared Tenancy: In shared tenancy, multiple customers share the same physical infrastructure and resources. This is also known as a multi-tenant environment. In this type of tenancy, each customer is logically isolated from one another, but they share the same physical hardware and underlying infrastructure. This approach is typically used for low-cost, entry-level cloud services.

For example, a shared hosting provider allows multiple customers to host their websites on the same physical server. Each customer has their own directory and access to a shared pool of resources, such as CPU, memory, and storage.

2. Dedicated Tenancy: In dedicated tenancy, a customer is assigned their own physical infrastructure and resources. This provides a higher level of isolation and security compared to shared tenancy, as the customer has complete control over the underlying hardware and infrastructure.

For example, a customer can lease a dedicated server from a cloud provider, which is exclusively used by that customer. The customer can install their own operating system, applications, and have full control over the resources on the server.

3. Isolated Tenancy: In isolated tenancy, a customer is assigned their own physical infrastructure, but with additional security and isolation measures in place to ensure complete logical separation from other tenants. This type of tenancy provides the highest level of isolation and security.

For example, a government agency may require an isolated environment for their cloud services due to the sensitivity of their data. The cloud provider may deploy the service in a physically separate data center with additional security measures, such as dedicated firewalls, intrusion detection systems, and access controls.

In summary, shared tenancy provides the lowest level of isolation and security, while dedicated and isolated tenancy provide higher levels of isolation and security at a higher cost. The choice of tenancy depends on the customer's requirements for security, performance, and cost.
