Windows Server 2022 Installation
================================

Windows Server is an operating system created by Microsoft for use as a server for businesses and other organizations. It provides a platform for centralized management and administration of applications, data storage, and other services. It is available in various editions and has features like Active Directory, Remote Desktop Services, and Hyper-V virtualization, among others. Windows Server is designed to be highly scalable, secure, and reliable, making it an ideal choice for many organizations.

.. image:: ./../image/winsrv/srv2022installation/ws2022.jpg

Windows Server 2022 is the latest version of the Windows Server operating system developed by Microsoft. It was released in October 2021 and comes with several new features and improvements over previous versions. Some of the new features in Windows Server 2022 include:

* Improved Hybrid Capabilities: Windows Server 2022 provides better integration with Microsoft's Azure cloud services, making it easier to deploy and manage hybrid environments.
* Enhanced Security: The new version of Windows Server includes improved security features, such as support for hardware-based security and enhanced encryption capabilities.
* Increased Scalability: Windows Server 2022 has been designed to support larger environments and more demanding workloads, with improved performance and increased capacity for storage and networking.
* Improved Management: The new version includes updated management tools and a streamlined setup process, making it easier for administrators to manage and maintain the server.

Windows Server 2022 is available in several editions, including Standard, Datacenter, and Essentials, each with different features and capabilities to meet the needs of different types of organizations.

Installation Platform
---------------------

Windows Server 2022 can be installed on a physical server or as a virtual machine on a hypervisor platform. The installation process involves several steps, including:

This document is written with below conditions. 

* Installation media of Windows Server 2022 has been downloaded in .ISO format from `Microsoft Evaluation center <https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022>`_.
* VMware esxi platform is used in this example
* Upload the .ISO file to the VMware datastore 
* Windows Server 2022 Datacenter edition with graphical interface is used in this example
* This is a fresh OS installation. Not an upgrade

Setting up VM
-------------

Setting up a virtual machine (VM) for Windows Server 2022 in VMware ESXi involves the following steps:

1. Login to ESXi, select Virtual Machines and click "Create/Register VM"

.. image:: ./../image/winsrv/srv2022installation/cr_vm.png

2. New virtual machine wizard will start. select "Create a new virtual machine" and click Next.

.. image:: ./../image/winsrv/srv2022installation/1.png

3. Give a name for the VM, select Guest OS family and version. Click Next

.. image:: ./../image/winsrv/srv2022installation/2.png

4. Select appropriate storage. Click Next

.. image:: ./../image/winsrv/srv2022installation/3.png

5. As per the guest OS selection, ESXi will determine hardware configuration. If needed, change CPU, Memory and Hard disk. Connect the right network and mound the .ISO file uloaded earlier. Click Next.

.. image:: ./../image/winsrv/srv2022installation/4.png

6. Verify the VM setting and click Finish. 

.. image:: ./../image/winsrv/srv2022installation/5.png

Windows Server 2022 Setup
-------------------------

Once the VM creation is completed, you can start the virtual machine and connect the console with any of ther given method. 

1. Press any key to boot from installtion media 

.. image:: ./../image/winsrv/srv2022installation/6.png

2. Select the language, time and currency format, and keyboard layount. Click Next.

.. image:: ./../image/winsrv/srv2022installation/7.png

3. Click Install

.. image:: ./../image/winsrv/srv2022installation/8.png

4. Slect the appropriate OS edition and if needed Desktop experience for GUI. In our case, we are using Windows Server 2022 Datacenter Evaluation (Desktop Experience). 

.. image:: ./../image/winsrv/srv2022installation/9.png

5. Accept the license agreement and click Next. 

.. image:: ./../image/winsrv/srv2022installation/10.png

6. Select Custom to install a fresh OS.

.. image:: ./../image/winsrv/srv2022installation/11.png

7. Select appropriate drive to install the OS. You can create necessary partitions if needed. In our case, we have only one disk and no complicated partition requirements needed. select the Drive 0 and click Next. Windows OS will create necessary partitions automatically. 

.. image:: ./../image/winsrv/srv2022installation/12.png

8. Installation will copy necessary files and it may restart the computer few times. 

.. image:: ./../image/winsrv/srv2022installation/13.png

.. image:: ./../image/winsrv/srv2022installation/14.png

9. Once the installation is completed, it will prompt to set a Administrator password. This is the local Administrator account of the server. Enter a password and click Next. 

.. image:: ./../image/winsrv/srv2022installation/15.png

10. Press Ctrl + Alt + Del to unlock the the login screen. You have to chose VM input and select the key combination. 

.. image:: ./../image/winsrv/srv2022installation/16.png

11. Enter the Administrator password you set in previous step to login. 

.. image:: ./../image/winsrv/srv2022installation/17.png

12. You will land in the Desktop of Windows Server 2022. 

.. image:: ./../image/winsrv/srv2022installation/18.png

VMware Tools Installation 
-------------------------

VMware Tools is a set of services and modules that enable several features in VMware products for better management of guests operating systems and seamless user interactions with them.

VMware Tools has the ability to:

* Pass messages from the host operating system to the guest operating system.
* Customize guest operating systems as a part of the vCenter Server and other VMware products.
* Run scripts that help automate guest operating system operations. The scripts run when the power state of the virtual machine changes.
* Synchronize the time in the guest operating system with the time on the host operating system

1. Select the VM in ESXi, Click Action > Gust OS > Install VMware Tools. This will mount the installation CD-ROM to the guest OS. 

2. Select Setup or select autorun to start the installtion. Click Next at welcome screen.  

.. image:: ./../image/winsrv/srv2022installation/19.png

3. You can customize the setup here. Typical option is good enough. 

.. image:: ./../image/winsrv/srv2022installation/20.png

4. Click install to begin the setup. 

.. image:: ./../image/winsrv/srv2022installation/21.png

5. Click finish and restart the VM. 

.. image:: ./../image/winsrv/srv2022installation/22.png

.. image:: ./../image/winsrv/srv2022installation/23.png
