# AWS EBS

AWS EBS (Elastic Block Store) is a cloud storage service provided by Amazon Web Services (AWS). It offers durable block-level storage volumes that can be attached to Amazon EC2 instances, providing persistent storage for your applications.

EBS volumes are network-attached storage devices that behave like raw, unformatted block devices such as hard drives. They are independent of EC2 instances and can be attached to or detached from instances as needed. You can create, attach, detach, and delete EBS volumes independently of the running state of an EC2 instance.

Here's a step-by-step guide on how to create an EBS volume:

1. Sign in to the AWS Management Console and open the Amazon EC2 console.

2. Click on "Volumes" in the left navigation pane.

3. Click on the "Create Volume" button.

4. In the "Create Volume" wizard, configure the following settings:

   - Availability Zone: Choose the desired availability zone where the EBS volume will reside.
   - Volume Type: Select the appropriate volume type based on your requirements, such as General Purpose SSD (GP2), Provisioned IOPS SSD (io1), or others.
   - Size: Specify the size of the volume in gibibytes (GiB).
   - Additional settings: You can configure optional settings like encryption, snapshot, and tags.

5. Click on the "Create Volume" button to create the EBS volume.

Once the EBS volume is created, you can attach it to an EC2 instance by following these steps:

1. In the EC2 console, navigate to the "Instances" section.

2. Select the EC2 instance to which you want to attach the EBS volume.

3. Right-click on the instance and choose "Attach Volume."

4. In the "Attach Volume" dialog box, select the EBS volume from the "Volume" drop-down menu.

5. Specify the "Device" name, such as `/dev/sdf`, that will be assigned to the volume on the instance.

6. Click on the "Attach" button to attach the EBS volume to the EC2 instance.

The EBS volume will be attached to the specified EC2 instance and will appear as a new block device within the instance. You can then format and mount the volume within the instance as needed, similar to any other disk.

Remember that EBS volumes incur costs based on their size and type, so it's important to manage them efficiently and consider the specific needs of your applications.
