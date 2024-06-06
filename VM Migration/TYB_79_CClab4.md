**Name : Khushi Agarwal**

**Roll no:-79**

**Division: TY-CS-B**

**Problem statement Lab 3: To Deploy Virtual Machine on Hypervisor such as KVM, ESXi. Take Backup and Migrate them**

Process to share hardware resources with other devices over internet and the hardware is at abstract level. Physical servers consume electricity, take storage space, and need maintenance. Virtualization removes all these limitations by abstracting physical hardware functionality into software. 

**Virtual machine:** A virtual machine is a software-defined computer that runs on a physical computer with a separate operating system and computing resources. The physical computer is called the host machine and virtual machines are guest machines. Multiple virtual machines can run on a single physical machine. Virtual machines are abstracted from the computer hardware by a hypervisor.

**Migration:** The movement of VMs from one resource to another, such as from one physical host to another physical host, or data store to data store, is known as VM migration. There are two types of VM migration: cold and live. 

- Cold migration occurs when the VM is shut down. 
- Live migration occurs while the VM is actually running.

**KVM or Kernel Virtual Machine**: Kernel Virtual Machine. KVM (for Kernel-based Virtual Machine) is a full virtualization solution for Linux on x86 hardware containing virtualization extensions that allows the kernel to function as a hypervisor.

**ESXi** is one of the primary components in the VMware infrastructure software suite. 

**VMware ESXi** is an enterprise-class, type-1 hypervisor developed by VMware for deploying and serving virtual computers. ESXi is a Type 1 hypervisor, meaning it runs directly on system hardware without the need for an OS. As a type-1 hypervisor, ESXi is not a software application that is installed on an operating system; instead, it includes and integrates vital OS components, such as a kernel.

1. **Need a ready VM on Linux/ Ubuntu**

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.001.png)

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.002.png)

1. **Click on File and select ‘export appliances’. Select the virtual machine you would like to export.**

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.003.png)



1. **Click on Next till its processing on the default settings (Select a dest folder for your file):**

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.004.png)

   A file would be created which is your backup file.

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.005.png)

1. **Now go to Virtual Box dashboard to remove the backed up VM**

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.006.png)

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.007.png)


1. **Click on Import Appliances now and select the .ova backup file at your destination which you selected**

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.008.png)

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.009.png)

1. **Click on Import with the default settings:**

![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.010.png)

1. **Successfully Backed up and restored the VM using Cold migration:**

   ![](Aspose.Words.ff8126eb-f85d-42ac-ac1b-f149f99ffd83.011.png)






