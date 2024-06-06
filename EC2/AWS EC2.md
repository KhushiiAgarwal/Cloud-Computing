
**Problem statement:** 

**Launch an EC2 Instance:**

**•	Create a new EC2 instance using the AWS Management Console.**

**•	Choose an Amazon Machine Image (AMI) based on your requirements.**

**•	Configure instance details, such as instance type, security groups, and key pairs.**

**Connect to an EC2 Instance:**

**•	Use SSH (Secure Shell) or RDP (Remote Desktop Protocol) to connect to your EC2 instance.**

**•	Understand how to use key pairs for authentication.**

**Explore Different Instance Types:**

**•	Launch instances of various types (e.g., t2.micro, t3.medium, m5.large) to understand the differences in computing power and resources.**

**Create and Attach EBS Volumes:**

**•	Create Elastic Block Store (EBS) volumes and attach them to your EC2 instances.**

**•	Learn how to format and mount the attached volumes.**

**Security Groups and Network Configuration:**

**•	Experiment with security groups to control inbound and outbound traffic to your instances.**

**•	Understand how to configure network interfaces and assign Elastic IP addresses.**


1. **Launch an EC2 Instance:**

   Amazon Elastic Compute Cloud (Amazon EC2) provides on-demand, scalable computing capacity in the Amazon Web Services (AWS) Cloud. Using Amazon EC2 reduces hardware costs so you can develop and deploy applications faster.

   **Features of Amazon EC2**

- **Instances:** Virtual servers.

o	**Compute optimized:** C5, C5n, C6g, C6gd, C6gn, C6id, C6i, C6in, C7a, C7g, C7gd, C7gn

o	**Memory optimized:** R, X, Z instances

o	**Storage optimized**: D, H, I

- **Processor families**

a – AMD processors

g – AWS Graviton processors

i – Intel processors

- **Additional capabilities** 



b – EBS optimized

d – Instance store volumes

n – Network and EBS optimized

e – Extra storage or memory

z – High performance

q – Qualcomm inference accelerators

flex – Flex instance

- **Amazon Machine Images (AMIs)**

  Preconfigured templates for your instances that package the components you need for your server (including the operating system and additional software).

- **Instance types**

  Various configurations of CPU, memory, storage, networking capacity, and graphics hardware for your instances.

- **Key pairs**

  Secure login information for your instances. AWS stores the public key and you store the private key in a secure place.

- **Instance store volumes**

  Storage volumes for temporary data that is deleted when you stop, hibernate, or terminate your instance.

- **Amazon EBS volumes**

  Persistent storage volumes for your data using Amazon Elastic Block Store (Amazon EBS).

- **Regions, Availability Zones, Local Zones, AWS Outposts, and Wavelength Zones**

  Multiple physical locations for your resources, such as instances and Amazon EBS volumes.

- **Security groups**

  A virtual firewall that allows you to specify the protocols, ports, and source IP ranges that can reach your instances, and the destination IP ranges to which your instances can connect.

- **Elastic IP addresses**

  Static IPv4 addresses for dynamic cloud computing.

- **Tags**

  Metadata that you can create and assign to your Amazon EC2 resources.

- **Virtual private clouds (VPCs)**

  Virtual networks you can create that are logically isolated from the rest of the AWS Cloud. You can optionally connect these virtual networks to your own network.


1. **Create an Instance**

The virtualization type of your instance is determined by the AMI that you use to launch it. Current generation instance types support hardware virtual machine (HVM) only. Some previous generation instance types support paravirtual (PV) and some AWS Regions support PV instances

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.001.png)

These instances provide a baseline level of CPU performance with the ability to burst to a higher level when required by your workload. An Unlimited instance can sustain high CPU performance for any period whenever required.


1. **Amazon Machine Image (AMI)**

Name and OS needs to be defined to choose an Amazon Machine Image (AMI). A variety of OS can be chosen including MacOS, Windows, Ubuntu, RedHat and types of Linux (Amazon, Suse,etc).

•	An Amazon Machine Image (AMI) is a template that contains a software configuration (for example, an operating system, an application server, and applications). From an AMI, you launch an instance, which is a copy of the AMI running as a virtual server in the cloud.

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.002.png)

An AMI includes the following:

- One or more Amazon Elastic Block Store (Amazon EBS) snapshots, or, for instance-store-backed AMIs, a template for the root volume of the instance (for example, an operating system, an application server, and applications).

- Launch permissions that control which AWS accounts can use the AMI to launch instances.

- A block device mapping that specifies the volumes to attach to the instance when it's launched.


1. **Key Pair**

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.003.png)

- A key pair, consisting of a public key and a private key, is a set of security credentials that you use to prove your identity when connecting to an Amazon EC2 instance. Amazon EC2 stores the public key on your instance, and you store the private key. For Linux instances, the private key allows you to securely SSH into your instance.

- AWS uses public-key cryptography to secure the login information for your instance. A Linux instance has no password; you use a key pair to log in to your instance securely. You specify the name of the key pair when you launch your instance, then provide the private key when you log in using SSH.

- For Key pair type, choose either RSA or ED25519. Note that ED25519 keys are not supported for Windows instances.

- A key pair is generated and .pem file is downloaded in downloads folder. It will be further used for connecting to local machine using SSH or RDP.

- If not saved the key pair is lost and cannot be retrieved, so needs to be downloaded and saved properly

- A command is used to set permissions in windows similar to chmod on Unix-like systems: 

  icacls "D:\Practical\VIT\Sem6\CloudStorage\Instance1.pem" /inheritance:r /grant:r "%username%:R"

  This command removes any inherited permissions and grants read-only access specifically to the current user.

  After running this command, you should be able to use your private key securely for SSH connections.


  1. **Networking & Security**

- Amazon VPC enables  to launch AWS resources, such as Amazon EC2 instances, into a virtual network dedicated to your AWS account, known as a virtual private cloud (VPC). 

- The public IP address of an instance is associated with your instance only until it is stopped or terminated. If you require a persistent public IP address, you can allocate an Elastic IP address for your AWS account and associate it with an instance or a network interface.
- An Elastic IP address remains associated with your AWS account until you release it, and you can move it from one instance to another as needed.


![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.004.png)

- A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. 
- Inbound rules control the incoming traffic to your instance, and outbound rules control the outgoing traffic from your instance.

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.005.png)


Security Rules help connect through a protocol. It ensures smooth connectivity through standard port and specified IP for inbound/ outbound traffic


1. **Recovery Rules**

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.006.png)

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.007.png)
Recovery rules like shutdown and termination process and auto recovery are specified

1. **Launch EC2** & its specification/description

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.008.png) 


![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.009.png)

1. **Connect to an EC2 Instance using SSH:**

 

- Get the public DNS name of the instance.
- Get the user name for your instance.

- Locate the private key and set permissions (icacls "D:\Practical\VIT\Sem6\CloudStorage\Instance2.pem" /inheritance:r /grant:r "%username%:R")

 

- Install an SSH client on your local computer if not pre-installed

- ` `Use: ssh -i /path/key-pair-name.pem instance-user-name@instance-public-dns-name

  The authenticity of host 'ec2-198-51-100-1.compute-1.amazonaws.com (198-51-100-1)' can't be established.

  ECDSA key fingerprint is l4UB/neBad9tvkgJf1QZWxheQmR59WgrgzEimCG6kZY.

  Are you sure you want to continue connecting (yes/no)?

- Warning: Permanently added 'ec2-198-51-100-1.compute-1.amazonaws.com' (ECDSA) to the list of known hosts. 


![ref1]

- Specify correct Security rules including ICMP protocol for all to connect and avoid **REQUEST TIMED OUT** error.
- **Use cmd in admin mode to connect to Linux Instance using Secure Shell**

  ![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.011.png)

After Launching EC2, click on Connect and copy ssh command to be run on CMD.Use icacls to set necessary permission for .pem file.

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.012.png)

Use correct Inbound & Outbound Rules to ensure connectivity. Set VPC, subnet and security group as well as use Public IP for establishing the necessary connection using SSH client

•	A key pair, consisting of a public key and a private key, is a set of security credentials that you use to prove your identity when connecting to an Amazon EC2 instance. Amazon EC2 stores the public key on your instance, and you store the private key. For Linux instances, the private key allows you to securely SSH into your instance.

•	AWS uses public-key cryptography to secure the login information for your instance. A Linux instance has no password; you use a key pair to log in to your instance securely. You specify the name of the key pair when you launch your instance, then provide the private key when you log in using SSH.

•	For Key pair type, choose either RSA or ED25519. Note that ED25519 keys are not supported for Windows instances.

•	A key pair is generated and .pem file is downloaded in downloads folder. It will be further used for connecting to local machine using SSH or RDP.

•	If not saved the key pair is lost and cannot be retrieved, so needs to be downloaded and saved properly

•	A command is used to set permissions in windows similar to chmod on Unix-like systems: 

icacls "D:\Practical\VIT\Sem6\CloudStorage\Instance1.pem" /inheritance:r /grant:r "%username%:R"

This command removes any inherited permissions and grants read-only access specifically to the current user.

After running this command, you should be able to use your private key securely for SSH connections.


1. **Explore Different Instance Types:**

 

- An instance is a virtual server in the cloud. Its configuration at launch is a copy of the AMI that you specified when you launched the instance.
- Virtualized Instances
- Bare-metal Instances

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.013.png)

**Instance families**



C – Compute optimized

D – Dense storage

F – FPGA

G – Graphics intensive

Hpc – High performance computing

I – Storage optimized


Is – Storage optimized with a one to six ratio of vCPU to memory

Inf – AWS Inferentia

Im – Storage optimized with a one to four ratio of vCPU to memory

M – General purpose

Mac – macOS

P – GPU accelerated

R – Memory optimized

T – Burstable performance

Trn – AWS Trainium

U – High memory

VT – Video transcoding

X – Memory intensive


**Current Generation (Sixth generation and later Amazon EC2 instance types)**

- General purpose: M6a, M6g, M6gd, M6i, M6id, M6idn, M6in, M7a, M7g, M7gd, M7i, M7i-flex, T4g

- Compute optimized: C6a, C6g, C6gd, C6gn, C6i, C6id, C6in, C7a, C7g, C7gd, C7gn, C7i

- Memory optimized: R6a, R6g, R6gd, R6i, R6id, R6idn, R6in, R7a, R7g, R7gd, R7i, R7iz, X2gd, X2idn, X2iedn

- Storage optimized: I4g, I4i, Im4gn, Is4gen

- Accelerated computing: DL2q, G5g, Inf2, P5, Trn1, Trn1n

- High-performance computing: Hpc6a, Hpc6id, Hpc7a, Hpc7g

**AMI virtualization types**

- The virtualization type of your instance is determined by the AMI that you use to launch it. Current generation instance types support hardware virtual machine (HVM) only. Some previous generation instance types support paravirtual (PV) and some AWS Regions support PV instances.



1. **Create and Attach EBS Volumes:**

- Amazon EBS provides the following volume types: General Purpose SSD, Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD. The following is a summary of performance and use cases for each volume type.

- **General Purpose SSD volumes** (gp2 and gp3) balance price and performance for a wide variety of transactional workloads. These volumes are ideal for use cases such as boot volumes, medium-size single instance databases, and development and test environments.

- **Provisioned IOPS SSD volumes** (io1 and io2) are designed to meet the needs of I/O-intensive workloads that are sensitive to storage performance and consistency. They provide a consistent IOPS rate that you specify when you create the volume. This enables you to predictably scale to tens of thousands of IOPS per instance. Additionally, io2 volumes provide the highest levels of volume durability.

- **Throughput Optimized HDD volumes** (st1) provide low-cost magnetic storage that defines performance in terms of throughput rather than IOPS. These volumes are ideal for large, sequential workloads such as Amazon EMR, ETL, data warehouses, and log processing.

- **Cold HDD volumes** (sc1) provide low-cost magnetic storage that defines performance in terms of throughput rather than IOPS. These volumes are ideal for large, sequential, cold-data workloads. If you require infrequent access to your data and are looking to save costs, these volumes provide inexpensive block storage.


- Amazon Elastic Block Store (Amazon EBS) provides block level storage volumes for use with EC2 instances. EBS volumes behave like raw, unformatted block devices. You can mount these volumes as devices on your instances. EBS volumes that are attached to an instance are exposed as storage volumes that persist independently from the life of the instance.

- You can back up the data on your Amazon EBS volumes by making point-in-time copies, known as Amazon EBS snapshots. A snapshot is an incremental backup, which means that we save only the blocks on the device that have changed since your most recent snapshot.


![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.014.png)

- The root storage device of the instance determines the process you follow to create an AMI. 
- The root volume of an instance is either an Amazon Elastic Block Store (Amazon EBS) volume or an instance store volume.
- The root device for your instance contains the image used to boot the instance.

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.015.png)



![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.016.png)

Before attaching Volume state is available when a min size of 8GB and 100 IOps is used

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.017.png)

- Attach the EBS Volume to an EC2 Instance:

- In the AWS Management Console, navigate to the EC2 dashboard.
- Select your instance and go to the "Volumes" section.
- Attach the EBS volume to your instance. Note the device name (e.g., /dev/xvdf).

- Connect to the EC2 Instance:

- Use SSH or another method to connect to your EC2 instance.
- Check Available Block Devices:
- Run the following command to list the available block devices:
- **Bash: lsblk**

- Identify the newly attached EBS volume based on its size and device name.

- Create a File System:
- Use a file system creation command (e.g., mkfs) to create a file system on the EBS volume. The specific command depends on the file system type you want to use. 
- For an ext4 file system: **Bash: sudo mkfs -t ext4 /dev/xvdf**

- Create a Mount Point:

- Choose or create a directory on your instance where you want to mount the EBS volume. This is known as the mount point.
- **Bash: sudo mkdir /mnt/myebsvolume**
- Mount the EBS Volume:
- Use the mount command to mount the EBS volume to the specified directory:
- **Bash:sudo mount /dev/xvdf /mnt/myebsvolume**
- Verify the Mount:
- Run the following command to verify that the EBS volume is mounted:
- **Bash: df -h**

- Now, the EBS volume is formatted with a file system and mounted to your EC2 instance. Use the mounted directory (/mnt/myebsvolume in the example) to store and retrieve data. Adjust the paths and names based on your specific requirements and naming conventions.


1. **Security Groups and Network Configuration:**

- When you launch an instance in a VPC, you must specify a security group that's created for that VPC. After you launch an instance, you can change its security groups. Security groups are associated with network interfaces. Changing an instance's security groups changes the security groups associated with the primary network interface 
- Security group rules enable you to filter traffic based on protocols and port numbers.
- Security groups are stateful—if you send a request from your instance, the response traffic for that request is allowed to flow in regardless of inbound security group rules. For VPC security groups, this also means that responses to allowed inbound traffic are allowed to flow out, regardless of outbound rules.
- When you associate multiple security groups with an instance, the rules from each security group are effectively aggregated to create one set of rules. Amazon EC2 uses this set of rules to determine whether to allow access.

  ![ref2]

  **Using Inbound & Outbound Traffic rules the security of network is maintained. It also helps in establishing connections via internet securely. Network Interface and gateway is used to connect**


- Each instance has a default network interface, called the primary network interface. You cannot detach a primary network interface from an instance.
- In a VPC, all subnets have a modifiable attribute that determines whether network interfaces created in that subnet (and therefore instances launched into that subnet) are assigned a public IPv4 address.
- When you create a network interface, it inherits the public IPv4 addressing attribute from the subnet. If you later modify the public IPv4 addressing attribute of the subnet, the network interface keeps the setting that was in effect when it was created

![](Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.019.png)

- An Elastic IP address is a static IPv4 address designed for dynamic cloud computing. An Elastic IP address is allocated to your AWS account, and is yours until you release it.

- By using an Elastic IP address, you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account. Alternatively, you can specify the Elastic IP address in a DNS record for your domain, so that your domain points to your instance.

- An Elastic IP address is a public IPv4 address, which is reachable from the internet. If your instance does not have a public IPv4 address, you can associate an Elastic IP address with your instance to enable communication with the internet.

- Starting on February 1, 2024, AWS will charge for all public IPv4 addresses, including public IPv4 addresses associated with running instances and Elastic IP addresses.

- An Elastic IP address is static; it does not change over time.
- An Elastic IP address is for use in a specific Region only, and cannot be moved to a different Region.
- You can allocate an Elastic IP address from Amazon's pool of public IPv4 addresses, or from a custom IP address pool that you have brought to your AWS account

[ref1]: Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.010.png
[ref2]: Aspose.Words.36d70b15-e681-4ed1-8ba0-5fc28bc1e4b6.018.png
