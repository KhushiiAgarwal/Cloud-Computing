



**PROBLEM STATEMENT: To install an OS using VirtualBox/ VMWare Workstation. Add Storage to create new virtual disk.**

1. **Installation of Virtual Box:** 

![](Aspose.Words.df6be2dc-e062-4c50-8af8-11cb647a82e2.001.png)

Downloading Oracle Virtual Box and set-up. Specifying folder for installation.

1. ` `**Adding storage capacity to Virtual Machine**

![](Aspose.Words.df6be2dc-e062-4c50-8af8-11cb647a82e2.002.png)

Defining Base memory, CPU and disk size requirement of a Virtual Machine before creating it as per required OS.

Selected Base Memory as 1024MB and Disk size as 1 GB with 1 processor


![](Aspose.Words.df6be2dc-e062-4c50-8af8-11cb647a82e2.003.png)

Final specifications after creation of virtual machine.

1. **Understanding Virtualization**: 

   A process to share hardware resources with other devices over internet and the hardware is at abstract level. Physical servers consume electricity, take up storage space, and need maintenance. Virtualization removes all these limitations by abstracting physical hardware functionality into software. By using Virtual Box, a Virtual Machine is set without worrying about hardware and the machine can use any OS without worrying about host machine OS. Select storage and disk size. Use ISO image for starting an instance.

   **Virtual machine:** A virtual machine is a software-defined computer that runs on a physical computer with a separate operating system and computing resources. The physical computer is called the host machine and virtual machines are guest machines. Multiple virtual machines can run on a single physical machine. Virtual machines are abstracted from the computer hardware by a hypervisor.

   **Hypervisor**

   The hypervisor is a software component that manages multiple virtual machines in a computer. It ensures that each virtual machine gets the allocated resources and does not interfere with the operation of other virtual machines. There are two types of hypervisors.

   **Type 1 hypervisor**

   A type 1 hypervisor, or bare-metal hypervisor, is a hypervisor program installed directly on the computer’s hardware instead of the operating system. Due to better performance, it’s commonly used by enterprise applications. E.g. VMware ESXi hypervisor

   **Type 2 hypervisor**

Hosted hypervisor or the type 2 hypervisor is installed on an operating system. Type 2 hypervisors are suitable for end-user computing. E.g. VMware Workstation/Oracle Virtual Box

**What are the different types of virtualization?**

1. **Server virtualization:** Server virtualization is a process that partitions a physical server into multiple virtual servers. It is an efficient and cost-effective way to use server resources and deploy IT services in an organization. Without server virtualization, physical servers use only a small amount of their processing capacities, which leave devices idle.

1. **Storage virtualization:** Storage virtualization combines the functions of physical storage devices such as network attached storage (NAS) and storage area network (SAN). Storage virtualization uses all physical data storage and creates a large unit of virtual storage that you can assign and control by using management software.

1. **Network virtualization**:  Network virtualization is a process that combines all of these network resources to centralize administrative tasks. Administrators can adjust and control these elements virtually without touching the physical components, which greatly simplifies network management.
   1. **Software-defined networking:*** Software-defined networking (SDN) controls traffic routing by taking over routing management from data routing in the physical environment.
   1. **Network function virtualization*:*** Network function virtualization technology combines the functions of network appliances, such as firewalls, load balancers, and traffic analyzers that work together, to improve network performance.

1. **Data virtualization:** Data virtualization creates a software layer between this data and the applications that need it. Data virtualization tools process an application’s data request and return results in a suitable format. Thus, organizations use data virtualization solutions to increase flexibility for data integration and support cross-functional data analysis.

1. **Application virtualization:** Application virtualization pulls out the functions of applications to run on operating systems other than the operating systems for which they were designed.

   To achieve application virtualization

   1. **Application streaming** – Users stream the application from a remote server, so it runs only on the end user's device when needed.
   1. **Server-based application virtualization** – Users can access the remote application from their browser or client interface without installing it.
   1. **Local application virtualization** – The application code is shipped with its own environment to run on all operating systems without changes.
1. **Desktop virtualization:** Desktop virtualization is used to run these different desktop operating systems on virtual machines, which your teams can access remotely. This type of virtualization makes desktop management efficient and secure, saving money on desktop hardware
1) **Virtual desktop infrastructure:** Virtual desktop infrastructure runs virtual desktops on a remote server. 
1) **Local desktop virtualization:** Local desktop infrastructure runs the hypervisor on a local computer and create a virtual computer with a different operating system.

**How is virtualization different from cloud computing?**

1) Virtualization technology makes cloud computing possible. Cloud providers set up and maintain their own data centers. They create different virtual environments that use the underlying hardware resources.
1) Cloud computing is the on-demand delivery of computing resources over the internet with pay-as-you-go pricing. Instead of buying, owning, and maintaining a physical data center, you can access technology services, such as computing power, storage, and databases, as you need them from a cloud provider.
