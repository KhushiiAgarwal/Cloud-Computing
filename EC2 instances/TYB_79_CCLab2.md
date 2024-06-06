Name : Khushi Agarwal

Roll no:-79

Division: TY-CS-B

**Problem statement Lab 2: To setup AWS accounts and launch instances.**

1. **Setup AWS account: Setup Username and Enter Card details. (Continuing using my old account)**

` `Amazon Elastic Compute Cloud (Amazon EC2) provides on-demand, scalable computing capacity in the Amazon Web Services (AWS) Cloud. Using Amazon EC2 reduces hardware costs so you can develop and deploy applications faster.

1. **Launch EC2 instance** 

![ref1]

Instance ID is generated after launching.

![ref2]

` `![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.003.png)

1. **Creation of Instance**

1. **Create an Instance**

The virtualization type of your instance is determined by the AMI that you use to launch it. Current generation instance types support hardware virtual machine (HVM) only. Some previous generation instance types support paravirtual (PV) and some AWS Regions support PV instances

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.004.png)

These instances provide a baseline level of CPU performance with the ability to burst to a higher level when required by your workload. An Unlimited instance can sustain high CPU performance for any period whenever required.


1. **Amazon Machine Image (AMI)**

Name and OS needs to be defined to choose an Amazon Machine Image (AMI). A variety of OS can be chosen including MacOS, Windows, Ubuntu, RedHat and types of Linux (Amazon, Suse,etc).

•	An Amazon Machine Image (AMI) is a template that contains a software configuration (for example, an operating system, an application server, and applications). From an AMI, you launch an instance, which is a copy of the AMI running as a virtual server in the cloud.

An AMI includes the following:

•	One or more Amazon Elastic Block Store (Amazon EBS) snapshots, or, for instance-store-backed AMIs, a template for the root volume of the instance (for example, an operating system, an application server, and applications).

•	Launch permissions that control which AWS accounts can use the AMI to launch instances.

•	A block device mapping that specifies the volumes to attach to the instance when it's launched.

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.005.png)


1. **Key Pair**

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.006.png)

1. A key pair, consisting of a public key and a private key, is a set of security credentials that you use to prove your identity when connecting to an Amazon EC2 instance. Amazon EC2 stores the public key on your instance, and you store the private key. For Linux instances, the private key allows you to securely SSH into your instance.

1. AWS uses public-key cryptography to secure the login information for your instance. A Linux instance has no password; you use a key pair to log in to your instance securely. You specify the name of the key pair when you launch your instance, then provide the private key when you log in using SSH.

1. For Key pair type, choose either RSA or ED25519. Note that ED25519 keys are not supported for Windows instances.

1. A key pair is generated and .pem file is downloaded in downloads folder. It will be further used for connecting to local machine using SSH or RDP.

1. If not saved the key pair is lost and cannot be retrieved, so needs to be downloaded and saved properly

1. A command is used to set permissions in windows similar to chmod on Unix-like systems: 

   icacls "D:\Practical\VIT\Sem6\CloudStorage\Instance1.pem" /inheritance:r /grant:r "%username%:R"

   This command removes any inherited permissions and grants read-only access specifically to the current user.

   After running this command, you should be able to use your private key securely for SSH connections.


   1. **Networking & Security**
- Amazon VPC enables  to launch AWS resources, such as Amazon EC2 instances, into a virtual network dedicated to your AWS account, known as a virtual private cloud (VPC). 

- The public IP address of an instance is associated with your instance only until it is stopped or terminated. If you require a persistent public IP address, you can allocate an Elastic IP address for your AWS account and associate it with an instance or a network interface.
- An Elastic IP address remains associated with your AWS account until you release it, and you can move it from one instance to another as needed.

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.007.png)

- A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. 
- Inbound rules control the incoming traffic to your instance, and outbound rules control the outgoing traffic from your instance.

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.008.png)

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.009.png)


1. **Recovery Rules**

![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.010.png)   ![](Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.011.png)
Recovery rules like shutdown and termination process and auto recovery are specified

1. **Launch EC2** & its specification/description

![ref3] 


![ref4]



**Features of Amazon EC2**

1. **Instances:** Virtual servers.

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


- **Instance families**



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

- General purpose: M6a, M6g, M6gd, M6i, M6id, M6idn, M6in, M7a, M7g, M7gd, M7i, T4g

- Compute optimized: C6a, C6g, C6gd, C6gn, C6i, C6id, C6in, C7a, C7g, C7gd, C7gn, C7i

- Memory optimized: R6a, R6g, R6gd, R6i, R7a, R7g, R7gd, R7i, R7iz, X2gd, X2idn, X2iedn

- Storage optimized: I4g, I4i, Im4gn, Is4gen

- Accelerated computing: DL2q, G5g, Inf2, P5, Trn1, Trn1n

- High-performance computing: Hpc6a, Hpc6id, Hpc7a, Hpc7g

1. **Amazon Machine Images (AMIs)**

Preconfigured templates for your instances that package the components you need for your server (including the operating system and additional software).

- **AMI virtualization types:** The virtualization type of your instance is determined by the AMI that you use to launch it. Current generation instance types support hardware virtual machine (HVM) only. Some previous generation instance types support paravirtual (PV) and some AWS Regions support PV instances.

1. **Instance types**

Various configurations of CPU, memory, storage, networking capacity, and graphics hardware for your instances.

1. **Key pairs**

Secure login information for your instances. AWS stores the public key and you store the private key in a secure place.

1. **Instance store volumes**

Storage volumes for temporary data that is deleted when you stop, hibernate, or terminate your instance.

1. **Amazon EBS volumes**

Persistent storage volumes for your data using Amazon Elastic Block Store (Amazon EBS).

1. **Regions, Availability Zones, Local Zones, AWS Outposts, and Wavelength Zones**

Multiple physical locations for your resources, such as instances and Amazon EBS volumes.

1. **Security groups**

A virtual firewall that allows you to specify the protocols, ports, and source IP ranges that can reach your instances, and the destination IP ranges to which your instances can connect.

1. **Elastic IP addresses**

Static IPv4 addresses for dynamic cloud computing.

1. **Tags**

Metadata that you can create and assign to your Amazon EC2 resources.

1. **Virtual private clouds (VPCs)**

Virtual networks you can create that are logically isolated from the rest of the AWS Cloud. You can optionally connect these virtual networks to your own network.

[ref1]: Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.001.png
[ref2]: Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.002.png
[ref3]: Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.012.png
[ref4]: Aspose.Words.995bbfef-79f9-4c5f-ac73-338611181938.013.png
