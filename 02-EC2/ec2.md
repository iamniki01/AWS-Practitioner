# EC2 Services

Amazon Elastic Compute Cloud (EC2) is a web service provided by Amazon Web Services (AWS) that allows individuals or businesses to rent virtual computing resources, such as virtual machines (VMs), on which they can run their own applications. EC2 provides scalable computing capacity in the cloud and allows users to easily launch and manage virtual servers as needed.

EC2 offers a wide range of computing options, including different types of virtual machine instances with varying capabilities and pricing. Users can select the appropriate instance type based on their specific computing needs, such as memory, storage, and processing power. Additionally, EC2 provides a range of tools and features for managing and monitoring instances, including automated scaling and load balancing, virtual private clouds for increased security, and integration with other AWS services such as Amazon S3 for storage and Amazon RDS for databases.

Let me give you an example of how EC2 can be used.

    Imagine you run a small e-commerce website and you are experiencing an increase in traffic due to a seasonal sale. To handle the increase in demand, you may need additional computing resources to ensure that your website continues to run smoothly. In this scenario, you could use EC2 to rent virtual servers (known as instances) that can handle the extra traffic.

    First, you would log in to the AWS Management Console and select EC2. From there, you would select the appropriate instance type based on your computing needs, such as memory, storage, and processing power. You can also choose the region where your instances will be located, which affects latency and compliance with data protection regulations.

    Next, you would configure your instances by selecting an operating system and setting up any necessary security groups or network settings. You can also configure storage options and add any necessary software and applications to the instance.

    Once your instances are configured, you can launch them and start using them to handle the increased traffic on your website. EC2 also provides features like load balancing and auto-scaling to ensure that your website can handle the varying levels of traffic.

    Finally, when the seasonal sale is over and your traffic returns to normal, you can stop or terminate the instances you rented through EC2, which will stop the billing for the instances and save you money.

    Overall, EC2 provides a flexible and scalable solution for businesses of all sizes to rent computing resources in the cloud, without the need for upfront investment in hardware and infrastructure.

## Create EC2 instances

To create EC2 service, search `EC2` services, create EC2 service with all specification. Then it will create instance. On top of it edit security group by allowing SSH and http(for test purpose only).

Here in this example I created AMI machine and tested successfully.

_What is AMI?_

    AMI stands for Amazon Machine Image. An AMI is a pre-configured virtual machine image used to create an EC2 instance in the Amazon Web Services (AWS) cloud. It's essentially a blueprint that defines the hardware, software, and other configuration settings required to launch an EC2 instance.

    An AMI contains all the necessary information to launch an instance, such as the operating system, application server, and application code. It also includes any additional software and configuration settings that are required to run the application, such as drivers, libraries, and scripts.

    Amazon provides a wide variety of pre-built AMIs that are optimized for various use cases, such as web servers, databases, and machine learning. You can also create your own AMI by customizing an existing AMI or by building a new one from scratch.

    When you launch an EC2 instance, you choose an AMI as the starting point. This allows you to quickly and easily launch instances with the specific configuration and software that you need. You can also use AMIs to create new instances, launch instances in different regions, or launch instances with different instance types. Additionally, you can share your own AMIs with other AWS accounts or make them publicly available for other AWS users to use.

    Overall, AMIs are a key component of EC2, providing a simple and efficient way to launch virtual machines with a pre-configured operating system and software stack.

## EC2 concepts

### Instance Type

Amazon EC2 provides a wide variety of instance types, each optimized for specific use cases, such as computing, memory, storage, or networking. Each instance type provides a unique combination of virtual CPUs, memory, storage, and networking capacity. Here are some of the most commonly used instance types:

1. General Purpose Instances(t & m-series): These instances are designed for a balance of compute, memory, and networking resources. They are suitable for a wide range of workloads, including small to medium-sized databases, web servers, and development and testing environments.

   _Example_ : m5.large - This instance type belongs to the "m" family and is designed for applications that require a balance of compute and memory resources. It has 2 virtual CPUs and 8 GB of memory.

2. Compute-Optimized Instances(c-series): These instances are designed for compute-intensive workloads that require high-performance processors. They are ideal for applications that require a lot of processing power, such as high-performance computing, batch processing, and video encoding.

   _Example_ : m5.large - This instance type is designed for applications that require a balance of compute and memory resources. It has 2 virtual CPUs and 8 GB of memory. It's a good fit for mid-sized databases, web servers, and data processing.

3. Memory-Optimized Instances(r-series): These instances are designed for memory-intensive workloads, such as in-memory databases, big data processing, and real-time data processing. They have a large amount of memory and high memory bandwidth, making them suitable for applications that require fast access to large datasets.

   _Example_: r5.xlarge - This instance type is designed for memory-intensive workloads, such as in-memory databases and big data processing. It has 4 virtual CPUs and 32 GB of memory. It's ideal for applications that require fast access to large datasets.

4. Storage-Optimized Instances(i-series): These instances are designed for applications that require high levels of storage performance and capacity. They are ideal for large-scale data processing, data warehousing, and log processing.

   _Example_: i3en.24xlarge - This instance type belongs to the "i" family and is designed for storage-intensive workloads, such as large-scale data processing, data warehousing, and log processing. It has 96 virtual CPUs, 768 GB of memory, and 25.6 TB of NVMe SSD instance storage.

5. GPU Instances(p & g-series): These instances are designed for workloads that require large amounts of parallel processing power, such as deep learning, machine learning, and scientific computing. They are equipped with one or more GPUs, which provide high-performance parallel processing for compute-intensive workloads.

   _Example_: p3.2xlarge - This instance type is designed for machine learning, deep learning, and other applications that require GPU acceleration. It has 8 virtual CPUs, 16 GB of memory, and 1 NVIDIA V100 GPU. It's ideal for applications that require parallel processing of large datasets, such as image and video analysis.

6. FPGA Instances(f1 instances): These instances are designed for applications that require custom hardware acceleration, such as financial analytics, genomics research, and video transcoding. They are equipped with FPGA chips, which can be programmed to perform custom operations and accelerate specific workloads.

   _Example_: The F1 instance family uses Xilinx UltraScale+ VU9P FPGAs, which provide up to 64GB of ECC-protected DDR4 memory, up to 1.5 million logic elements, and up to 6,840 DSP engines. This makes it ideal for workloads that require high performance and low latency, such as real-time video processing, data compression, and encryption.

Each instance type comes in different sizes, which vary in terms of CPU, memory, and storage capacity. You can choose the instance type and size that best fits your workload requirements and budget.

### EC2 key-pair

An EC2 key pair is a secure way to log in to your EC2 instances. When you launch an EC2 instance, you can specify a key pair to use for SSH (Secure Shell) access to the instance. The key pair consists of a public key and a private key. You keep the private key secure and use it to log in to your instance, while the public key is stored on the instance and used to encrypt messages that can only be decrypted using the private key.

Here's how the process typically works:

First, you create a key pair in the EC2 console or using the AWS CLI. This generates a public/private key pair, with the private key being downloaded to your local machine.

When launching an EC2 instance, you can specify the key pair to use for SSH access. This will associate the public key with the instance.

Once the instance is launched, you can use the private key to log in to the instance securely via SSH. You can do this by specifying the path to the private key in your SSH client when connecting to the instance.

Using key pairs is a best practice for accessing EC2 instances securely. By using a public/private key pair, you can ensure that only authorized users can access your instances, and that all communication between your local machine and the instances is encrypted. It's important to keep your private key secure and never share it with anyone else.

### EC2 Security Groups

EC2 Security Groups are a fundamental component of the security infrastructure on AWS. They are virtual firewalls that control the inbound and outbound traffic to your EC2 instances.

A security group acts as a set of firewall rules that define which traffic is allowed to reach your instances. You can create and configure security groups to control access to your instances based on IP addresses, ports, and protocols. Each instance can be associated with one or more security groups, and each security group can have multiple rules.

When you launch an EC2 instance, you can specify which security groups to associate with the instance. By default, new instances are launched with a default security group that allows all outbound traffic and no inbound traffic.

You can configure security groups to allow traffic from specific IP addresses or ranges of IP addresses, or you can allow traffic from other security groups. You can also specify which ports and protocols are allowed for inbound traffic.

EC2 Security Groups provide a simple and effective way to manage the security of your EC2 instances. By restricting access to your instances based on IP addresses, ports, and protocols, you can help to prevent unauthorized access and protect your applications and data.

### EC2 IP-addresses

EC2 instances can have two types of IP addresses:

1. Private IP Address: Every EC2 instance is assigned a private IP address when it is launched. This IP address is used to communicate within the VPC (Virtual Private Cloud) network that the instance is launched in. Private IP addresses are not publicly routable and can only be accessed within the VPC.

2. Public IP Address: EC2 instances can also be assigned a public IP address if they are launched in a subnet that has an Internet Gateway attached to it. Public IP addresses are used to access the instance over the internet. When an instance is launched with a public IP address, it is assigned an Elastic IP address, which is a static IP address that you can associate and disassociate with your instance as needed.

It's important to note that by default, EC2 instances launched in a VPC do not have a public IP address. If you need to access your instance over the internet, you can assign a public IP address or an Elastic IP address to it. However, you should be careful when exposing your instances to the internet and should take appropriate security measures to protect your instances from unauthorized access.

### Elastic IP-address

An Elastic IP address is a static, public IP address that you can allocate to your AWS account and associate with your EC2 instances, NAT gateways, or Network Load Balancers.

By default, when you launch an EC2 instance in a VPC, it is assigned a dynamic public IP address that can change every time the instance is stopped and started. This can be a problem if you need to run a service that requires a fixed IP address, such as a website or a database.

Elastic IP addresses provide a way to work around this issue. You can allocate an Elastic IP address to your account and then associate it with an EC2 instance. The Elastic IP address remains associated with the instance until you release it or disassociate it.

Here are some important things to keep in mind about Elastic IP addresses:

- You can allocate up to 5 Elastic IP addresses per AWS account.
- When you allocate an Elastic IP address, it is charged at an hourly rate. If you do not associate the Elastic IP address with a running instance or use it to map to a NAT gateway or Network Load Balancer, you are charged an additional hourly fee.
- When you associate an Elastic IP address with an EC2 instance, you must also update the routing for the VPC subnet that the instance is in to direct traffic to the Elastic IP address.

Using Elastic IP addresses can be a useful tool for managing your EC2 instances, but it's important to be aware of the associated costs and to take appropriate security measures to protect your instances from unauthorized access.

## Testing EC2

After creating AMI/any machines open ssh console after clicking on running ec2 instance `connect`. After connecting follow this commands(make sure in security group https/ http) is enabled.

```bash
sudo su
yum update -y
yum install httpd
systemctl start httpd
systemctl enable httpd
echo "Hello World! from Ngs_dev" > /var/www/html/index.html
```

Then copy public ip of ec2 instance and run it on another tab of browser. It shows an output that stored under `/var/www/html/index.html`
