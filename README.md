<h1>Active Directory Lab -- Detailed Guide for Beginners</h1>

<h1> UNDER CONSTRUCTION </h1>

<h2>Network Diagram</h2>

![29-07-2022 AD Lab drawio](https://user-images.githubusercontent.com/112909705/191284205-bdbfdcaa-935e-4017-a003-74e57009610a.png)

<h2>Description</h2>

This guide is an attempt to help anyone that is interested in learning about why Active Directory is useful, applying the knowledge, and developing more skills for the workplace. 

<br />

This documentation will walk you through setting up an Active Directory Lab using a virtual machine (VirtualBox). 

<br />

Active Directory is a great way to learn practical knowledge that is used in an enterprise environment, which makes is a great starting point for anyone trying to learn more about IT and develop skills that are used in jobs ranging from Help Desk to Cybersecurity positions. 

<br />

After completing this lab, you will have learned more about why Active Directory is so useful, how to apply that knowledge in the workplace, and a lab environment to practice more on your own. 



<h2>Environments Used and Downloads</h2>

- <b>Oracle VirtualBox</b> 
- <b>Windows Server 2022</b>
- <b>Windows 10</b>

<h2>Prerequisites</h3> 


<h3>IT Knowledge</h3> 

You don't need to know all of these things or any of them in great depth, but the more you know, the less googling you will have to do. 
<br />

- Basic understanding of what different hardware components do, such as CPU, RAM, HDD, NIC, etc
- Basic understanding of computer networking, such as IP, subnets, default gateways, etc
- Basic understanding of Client-Server model 
- Basic understanding of different services such as DHCP, DNS, NAT, etc 





<h3>Hardware</h3> 

You don't need these things, but they are recommended for optimizing your VM's performance. 
<br />

- 8GB+ of RAM is ideal (Attempt even if under 8GB)
- 100GB+ of unused storage (Windows 10 and Server 2022 require a minimum 32GB of unused storage each) 


## Downloads 

### Virtual Machine (Oracle VirtualBox)

Download the VirtualBox and the Extension from:
https://www.virtualbox.org/wiki/Downloads

![firefox_DYwz5koyyw](https://user-images.githubusercontent.com/112909705/191357946-9f6cf39b-9e9b-4ab6-ae6e-5fb0dce53dd4.png)

![firefox_pSEJavfft1](https://user-images.githubusercontent.com/112909705/191358052-d2b8857a-709a-43ae-aa1a-8e19280e7266.png)


Do not forget to download the VirtualBox Extension Pack. It will provide more functionalities to your virtual machine that aren't automatically included, such as being able to use your USB and Webcam from your host computer (the computer you're using now). 





### Windows Server 2022 Evaluation ISO 

Download Microsoft Server 2022 Evaluation ISO: https://www.microsoft.com/en-gb/evalcenter/evaluate-windows-server-2022


![firefox_hN23JGBfHF](https://user-images.githubusercontent.com/112909705/191358335-ba56f33f-4fb9-4bb4-bd21-b33e752baef8.png)


After clicking "Download the ISO", you will need to fill in some personal information before choosing the appropriate ISO.




### Windows 10 Enterprise Evaluation ISO 

Download Microsoft Windows 10 Enterprise Evaluation ISO: https://www.microsoft.com/en-GB/evalcenter/evaluate-windows-10-enterprise


![firefox_bNxzh6GmmQ 1](https://user-images.githubusercontent.com/112909705/191358495-68d20c30-1a30-49b2-ac67-27847655d292.png)


After clicking "Download the ISO - Enterprise", you will need to fill in some personal information before choosing the appropriate ISO. 


## Introduction to Virtual Machines 

### What is a Virtual Machine? 

An easy way to describe a virtual machine is "a computer inside of a computer". 

Imagine you were to open any program, such as Google Chrome, but the window that pops up shows you a Windows 10, MacOS, or Linux system that you can interact with -- just like any other computer. It's like you have two different computers on one screen.


When you create a virtual machine on your personal computer, you allocate some resources from your physical computer (CPU, RAM, HDD/SDD, NIC, etc) to be used for the virtual machine. So if you were to allocate 33% of your CPU usage to the VM, every time you launch that VM, 33% of your CPU would be dedicated to it. The same applies with RAM. 

Host machine refers to the PC you are physically using, and the operating system that is on it. Guest machine refers to the virtual machine. 

The way that your computer (without a virtual machine) typically manages its resources is through the operating system. So, if you were using Windows 10, it would be interacting directly with the hardware. However, specialized hypervisor software allows the hardware 

![08_02_22_06_35_28](https://user-images.githubusercontent.com/112909705/191359574-b49a12d8-b769-48dd-83e3-f30d24084f61.png)


### Why a Virtual Machine? 

Useful for cloud enterprise, but also personal use. 

Buying dedicated computers to run server software is costly. It is also tedious to use your personal every-day computer (without a virtual machine) as a lab. You might break something that needs fixing, and you don't have a very functional computer in the meantime. If you use a Virtual Machine, you can just delete it, and start again. 


## Installing VirtualBox 

- Open your "Downloads" folder, or where you saved the VirtualBox installation file
- Execute the VirtualBox installation file
- Agree to all prompts 


## Setting up a Virtual Machine

- Launch Virtual Box if it's not already open 
- Select the blue icon called "New" 
- Name the Virtual Machine "Windows Server 2022" (or something similar)
- Keep the default Machine Folder, or change it if you prefer a different path
- Keep the Type as Microsoft Windows 
- Change the Version to "Others Windows (64-bit)"
- Select "Next"

![08_02_22_07_14_21](https://user-images.githubusercontent.com/112909705/191360081-2bf84249-c51b-4ac0-babc-3720952dd264.png)


- Select the amount of RAM

This depends how much RAM your computer has, but the more RAM you add, the less lag you'll experience in the VM. I'd recommend trying at least 2048MB. You don't want to allocate too much RAM, though, as it can affect your "host"(physical) computer from running properly. This would also affect the virtual machine. 

If performance isn't ideal, you can always change the value later...

![08_02_22_07_20_16](https://user-images.githubusercontent.com/112909705/191362379-77282b9a-4305-46fa-83ec-9852844bfb9d.png)



- Create a virtual hard disk now 

![08_02_22_07_26_27](https://user-images.githubusercontent.com/112909705/191362543-f84363a0-4672-42c8-b71c-a1e591700960.png)


- Select VDI (VirtualBox Disk Image)

![08_02_22_07_27_39](https://user-images.githubusercontent.com/112909705/191362675-9b817334-4cd7-4faa-85c5-ae1740ec62e7.png)

- Select "dynamically located" and hit next

![08_02_22_07_28_15](https://user-images.githubusercontent.com/112909705/191362777-4afda413-aea3-4dc9-8078-d727cbe295aa.png)


- Increase the file size to 40GB 
- Keep the file location, or change it if you prefer. 

![08_02_22_07_30_23](https://user-images.githubusercontent.com/112909705/191362890-f8a88b4c-3665-452d-bfed-44261cbb14e9.png)


- With "Windows Server 2022" being highlighted, select the yellow cog that says "Settings" 
- Select "Advanced"
- Change the following:
	- Shared Clipboard: Bidirectional
	- Drag'n'Drop: Bidirectional 

![08_02_22_07_43_26](https://user-images.githubusercontent.com/112909705/191363109-3d81d786-1584-4e60-89cb-73a5e1c9b46d.png)



If we refer back to our network diagram, we can see that we want two different networks on our Windows Server 2022 machine.  One is external, which faces the internet. The other being internal, which is a private network (we do not want the outside world being able to access this). By default, the virtual machine configured an external NIC (so it can access the internet, the outside world).  We must manually add another NIC, and we will use that to communicate with our private internal network. 

ADD NETWORK DIAGRAM IMAGE REFERENCE HERE 

- Select "Network"
- Select "Adapter 2"
- Enable Network Adapter 
- Attach to "Internal Network"

![08_02_22_07_50_09](https://user-images.githubusercontent.com/112909705/191363611-45b2da73-d076-47ef-9ba1-130fe25c0cc5.png)

- Select "System" and then "Processor"
- Change the amount of processor(s) and cores to 2 or 3. 

![08_02_22_07_58_30](https://user-images.githubusercontent.com/112909705/191363930-d486f4cb-aef4-40b7-a386-bb135f52f2c1.png)


- file > preferences > extensions > click green + > select extensions file > install 

![08_02_22_14_05_31](https://user-images.githubusercontent.com/112909705/191364048-40885098-8a65-4554-b641-9494668584a6.png)

- Click Extensions
- Click the green +

![08_02_22_14_10_49](https://user-images.githubusercontent.com/112909705/191364135-db6a7923-f0ce-4d8b-a3ab-a3e6bd137fea.png)

- Double-Click Oracle_VM_VirtualBox...

![08_02_22_14_12_43](https://user-images.githubusercontent.com/112909705/191364206-30026d06-cc70-4624-8482-a74a5e8ee760.png)

- Click Install 

![08_02_22_14_21_14 1](https://user-images.githubusercontent.com/112909705/191364279-922e2a62-48e9-437c-b1ee-6cd0ef9ff60e.png)

- Scroll down 
- Click "I Agree"

![08_02_22_14_22_36 1](https://user-images.githubusercontent.com/112909705/191364389-e3f28944-4f6b-4a39-9e65-c041e27e5972.png)

- Click "OK"

![08_02_22_14_23_37](https://user-images.githubusercontent.com/112909705/191364461-ae2bdcf3-d0fc-48e2-b9eb-42091127403e.png)


- Click "OK"

![08_02_22_14_37_16](https://user-images.githubusercontent.com/112909705/191364540-d172d0d3-35b4-4a43-94c8-3e1d06841840.png)


## Introduction to Windows Server 2022

### What is a Computer Network? 

Should I include this? 


### What is a Server?


### Why Windows Server 2022? 


Should I include this?




## Installing Windows Server 2022 on the VM 

- Windows Server 2022 highlighted 
- Click "Settings"
- Click "Storage"
- Click "Empty"
- Click the blue disc icon to the right 
- Click "Choose a disk file..."

![08_02_22_16_16_47](https://user-images.githubusercontent.com/112909705/191365044-4ebfd33e-8e0a-4619-9e00-b25f439f994c.png)


- Go to the location you saved the Windows Server 2022 ISO 
- Double-Click "Server_EVAL_...."

![08_02_22_16_17_52](https://user-images.githubusercontent.com/112909705/191368271-83afb766-1ad5-4445-bb44-d49c8969b868.png)

- Click "OK"

![08_02_22_16_20_25](https://user-images.githubusercontent.com/112909705/191368361-158f2d5c-c9fe-4230-ac99-cd75ed575e33.png)


- Click "Windows Server 2022"
- Click "Start"

![08_02_22_16_09_06](https://user-images.githubusercontent.com/112909705/191368421-1e9c4e16-672f-499e-b771-af0221902274.png)

- Select your preferred language and keyboard layout
- Click "Next" 

![08_02_22_17_37_51](https://user-images.githubusercontent.com/112909705/191368468-90d22477-ecb2-4c95-919d-7858ebdc6ad1.png)

- Select "Install Now"

![08_02_22_17_41_54](https://user-images.githubusercontent.com/112909705/191368588-e4c41129-0283-4693-95bb-000d9a482da0.png)

At this step we need to be very careful. We want to select the Standard Evaluation WITH Desktop Experience. This will provide a GUI, like what you are seeing right now, and is much more convenient and beginner-friendly.

If we were to install the regular Standard Evaluation, there would be no GUI and everything would be by CLI, so you would have to type commands to perform all of the desired actions. 

- Select "Windows Server 2022 Standard Evaluation (Desktop Experience)"
- Click "Next"

![08_02_22_17_44_04](https://user-images.githubusercontent.com/112909705/191368881-58a30079-efb6-4c49-a4bd-a219bc2bce5c.png)


- Click the box to accept the terms
- Click "Next"

![08_02_22_17_45_25](https://user-images.githubusercontent.com/112909705/191368959-c8af1999-d40a-4203-ab03-e4de88f0c466.png)

Upgrading the OS would mean that we have it already installed. We are installing Windows Server 2022 on this VM for the first time. So in this case we should go with the "Custom" installation. 

Click "Custom: Install Microsoft Server Operating System only (advanced)"

![08_02_22_17_45_52](https://user-images.githubusercontent.com/112909705/191369027-2f12015e-eb1c-4a7e-8414-2e45a2436945.png)

Now we need to select where we want to install the operating system. Earlier when we were creating the VM, we created a "Virtual Hard Disk" and allocated 40GB of storage space. That same Virtual Hard Disk is going to appear to select, which we will use. 

- Select "Drive 0 Unallocated Space - 40.0 GB - 40.0GB"
- Click "Next" 

![08_02_22_17_48_05](https://user-images.githubusercontent.com/112909705/191369124-5dd4f605-5fa4-40f0-9627-9f57939534f8.png)

The Microsoft Server 2022 installation will begin and the computer might restart a few times. 

A black screen will appear which tells you to press any key -- but don't press any key. 

It will prompt you with that message because I have the Windows Server ISO disk inserted in the optical drive, and wants to see if you want to boot from the CD. If we were to do that, we would start the entire process over again. 

![08_02_22_17_48_25](https://user-images.githubusercontent.com/112909705/191369195-c877fb88-3de4-4487-984a-c12dbbffcd39.png)

Do not press any key. Windows will load normally soon.

![08_02_22_17_50_20](https://user-images.githubusercontent.com/112909705/191369261-a8e5e35a-86c1-4c48-adec-002c8d9f672e.png)

![08_02_22_17_51_09 1](https://user-images.githubusercontent.com/112909705/191369316-384426e4-8243-413d-86de-6e5b743de243.png)

User name: Administrator 
Password: Password1

Enter the password you would like to set and click Finish. 

 This is only a lab environment so we do not need to worry about a secure password. I will be using the password: "Password1".


User name: Administrator 
Password: Password1

![08_02_22_17_56_14](https://user-images.githubusercontent.com/112909705/191369395-90eaf88b-cae1-444e-87a6-3c71b1ce91c1.png)

## First Time Logging In

When the OS is loaded, you will be required to press Ctrl+Alt+Delete to unlock the screen. Until then, you cannot log in. The reason this is the default for Windows Server is that it provides a "Secure Login", where the key sequence will ensure a genuine Windows login screen appears. This prevents usernames and passwords from being intercepted from malicious programs. 

Since we are running Windows Server on a virtual machine, if you were to press Ctrl+Alt+Delete on the keyboard, it would bring up a prompt for your host machine instead, so you cannot unlock the VM pressing Ctrl+Alt+Delete.

To get around this, you can select:
input > keyboard > insert Ctrl+Alt+Del

Another option would be to use the key sequence "Host+Del", where Host is normally the right Ctrl key. So, Ctrl (right) + Del. 


Unlock the computer by selecting:
Input > Keyboard > Insert Ctrl+Alt+Del

![08_02_22_17_58_53](https://user-images.githubusercontent.com/112909705/191369688-68f66dab-a3ec-4370-a345-b7ac56b7741c.png)

Some windows are going to automatically open. 

Check the box to not show the Windows Admin Center message again if you wish. Close the windows.  

![08_03_22_15_37_48](https://user-images.githubusercontent.com/112909705/191369788-d1e774da-9db5-4067-8848-0fd2b29a46c5.png)

We have successfully installed Windows Server 2022, so we no longer need the installation disk in the computer. Let's remove the installation disk. 

 - Right-click the blue disk near the bottom right corner
 - Click "Remove disk from virtual drive"

![08_03_22_15_41_20](https://user-images.githubusercontent.com/112909705/191369857-82142cc5-4dc8-4605-af0f-b6b118d2bcfe.png)

The Windows Server 2022 ISO disk that we inserted earlier has been removed. You can tell as it's no longer a blue colour and has a faded grey colour. 

![08_03_22_15_44_51](https://user-images.githubusercontent.com/112909705/191370055-340aade3-f1ee-47b0-bd7c-ea4d1f4a79d7.png)

### Installing VirtualBox Guest Additions 

With an empty optical drive now, let's install VirtualBox Guest Additions. 

This step is very important for making your VM experience more enjoyable. The VirtualBox Guest Additions has system application and driver software which makes the OS run faster, which decreases the delay of inputs drastically. 

- Devices > Insert Guest Additions CD Image... 

![08_03_22_15_47_28](https://user-images.githubusercontent.com/112909705/191370130-313564b2-da3f-4bd0-9d58-f948315bca32.png)

- File Explorer > CD Drive (D:) VirtualBox Guest Additions >VBoxWindowsAdditions-amd64

![08_03_22_15_50_19](https://user-images.githubusercontent.com/112909705/191370273-df8fa9d3-ee80-4919-a601-6fe4bc736c2b.png)


- Click Next

![08_03_22_15_53_28](https://user-images.githubusercontent.com/112909705/191370359-f0e3b2fe-d88d-4eba-8dad-515f8ebcf412.png)

- Click Next

![08_03_22_15_54_00](https://user-images.githubusercontent.com/112909705/191370425-a6ecb57a-520f-4b50-969a-1268b47c9734.png)

- Click Install

![08_03_22_15_54_30](https://user-images.githubusercontent.com/112909705/191370480-0ee67a74-1e06-4a03-8f9c-abeff41715c3.png)

- "Reboot now" selected
- Click "Finish" 

![08_03_22_15_55_22](https://user-images.githubusercontent.com/112909705/191370537-da7edc23-f33e-4af8-82bc-4d5619e72891.png)

You should notice the Virtual Machine runs much faster now. 

## Naming the Server's Network Adapters 

Log in to the computer.

When we created the virtual machine 1 NIC was automatically included (our external NIC). We then added another NIC and assigned it as "internal".

There are 2 NICs as a result, where one is facing the internet and the other facing the internal network. 


(FIX THIS IMAGE)

![08_03_22_14_41_20](https://user-images.githubusercontent.com/112909705/191370925-9208e99b-b7d1-44e8-b6a0-7a20ab687586.png)


The NICs came with generic names that are not very descriptive. We want to rename them to be better organized and configure other things more easily later.

Before renaming the network adapters, we need to confirm which one is the internal and which one is the external. 


Network icon (bottom right) > Network & internet settings

![08_04_22_06_42_21](https://user-images.githubusercontent.com/112909705/191371102-00cf056b-b8e3-4b6a-88d5-60004bd868d7.png)

Ethernet > Change adapter options 

![08_04_22_06_52_25](https://user-images.githubusercontent.com/112909705/191371152-37db519d-ef65-4a13-9aa8-fee19de8ada2.png)

Open the status for Ethernet and Ethernet 2

![08_04_22_06_59_23](https://user-images.githubusercontent.com/112909705/191371302-536fa24c-b42b-4319-8c55-aef33f6218dc.png)

Open the details for Ethernet and Ethernet 2

![08_04_22_07_01_21](https://user-images.githubusercontent.com/112909705/191371357-53089ae4-8cb4-4c13-9758-c30f6aaa1852.png)

When a computer is unable to obtain an IP address from DHCP it is given an IP address that starts with 169.254. This means the computer can only communicate with other computers on the local subnet, which would mean it cannot interact with any other computer outside of the subnet (cannot connect to the internet). This means that the "Ethernet" network adapter is the internally-facing NIC. 

Since the "Ethernet 2" network adapter has an IP of 10.0.2.15, which is within a normal private IP address range, it means that DHCP was able to assign an IP to "Ethernet 2", which was obtained from the home router, and "Ethernet 2" can connect to the internet. This means that "Ethernet 2" is the externally-facing NIC. 

"Ethernet" has an IP of: 169.254.112.243 -- (INTERNAL)
"Ethernet 2" has an IP of: 10.0.2.15 -- (EXTERNAL)

![08_04_22_12_30_02](https://user-images.githubusercontent.com/112909705/191371406-2ddfb6e1-c2f3-4a1e-af33-ed477150a3ac.png)

Since we know Ethernet is internal and Ethernet 2 is external, let's rename them appropriately. 

- Close both of the Network Connection Details 

![08_04_22_12_33_47](https://user-images.githubusercontent.com/112909705/191371441-4328f369-26f5-4ff4-b7e3-0c34995c3d3a.png)

Close both the NIC status'. 

![08_04_22_12_35_36](https://user-images.githubusercontent.com/112909705/191371503-0de76aa2-5a5f-48b9-b5ae-52f1390d69df.png)

Right-click "Ethernet" > Rename 

![08_04_22_07_59_35 1](https://user-images.githubusercontent.com/112909705/191371552-849e4e33-66c6-4590-8982-51257c900977.png)


Rename as "INTERNAL" or something else intuitive to read

![08_04_22_08_03_50](https://user-images.githubusercontent.com/112909705/191371630-470642af-1cc2-44df-a4eb-60cd01ab3eb8.png)

Right-click "Ethernet 2" > Rename 

![08_04_22_08_05_25](https://user-images.githubusercontent.com/112909705/191371661-b32032e1-29bc-4965-a39e-44e4e0d99ade.png)


Rename as "EXTERNAL" or something else intuitive to read.

![08_04_22_08_06_58](https://user-images.githubusercontent.com/112909705/191371714-5b7676e6-df91-4a38-bc9e-eca8de7defb9.png)


Both have been renamed and we do not need to go through all of those windows again to distinguish the NICs. This will speed up configuring other services that use either networks. 

![08_04_22_08_12_56](https://user-images.githubusercontent.com/112909705/191371785-a18b0b46-71c6-4b45-b628-fed056f31ecc.png)


## Assigning an IP Address to the Internal Adapter 

EDIT EDIT EDIT 

Why are we changing the IP address?
Talk about organization and ranges 
Talk about subnets 



- Double-click "Internal" > Properties > Internet Protocol Version 4 (TCP/IPv4)
- Use the following IP Address: 
- IP Address: 172.16.0.1
- Subnet mask: 255.255.255.0
- Default gateway: blank 

- Use the following DNS server address: 
- Preferred DNS server: 127.0.0.1 


Double-click "INTERNAL"

![08_04_22_13_41_04](https://user-images.githubusercontent.com/112909705/191372121-5900dc30-f18e-48ea-b3a3-f6f953e6e6cc.png)


Click "Properties"

![08_04_22_13_42_01 1](https://user-images.githubusercontent.com/112909705/191372216-762ec19d-8e9e-46cd-bb1e-678851c2c2be.png)

Double-click "Internet Protocol Version 4 (TCP/IPv4)"

![08_04_22_13_44_16](https://user-images.githubusercontent.com/112909705/191372307-647cf69d-0685-49d8-9db4-352180aad3be.png)

- Select "Use the following IP address"
- IP address: 172.16.0.1
- Subnet mask: 255.255.255.0
- Preferred DNS server: 127.0.0.1 
- Click "OK"

![08_04_22_13_51_21](https://user-images.githubusercontent.com/112909705/191372378-047816a0-d3ca-40a5-91be-bb8af8ee86cb.png)


## Rename the Computer 

- Right-click the Start/Windows button > System 

![08_04_22_15_55_35](https://user-images.githubusercontent.com/112909705/191372586-4cdc2fe9-9fef-4c4d-b8f3-4f5cd925d44d.png)

Click "Rename this PC" 

![08_04_22_15_56_18](https://user-images.githubusercontent.com/112909705/191372637-c214b7ef-fc22-49a4-a6d4-41c9802c0e0b.png)

- Type "DC" (for Domain Controller)
- Click "Next"

![08_04_22_15_57_56](https://user-images.githubusercontent.com/112909705/191372696-00e7694a-dc98-444a-946b-748f597937c2.png)

Click "Restart now"

![08_04_22_15_58_34](https://user-images.githubusercontent.com/112909705/191372744-f15012b7-240c-4011-8d85-ad7b0710f9b5.png)


## Installing Active Directory Domain Services 

After logging back in from the reboot, Server Manager should have automatically started. If not, search for "Server Manager". 


- Before you Begin: Next
- Installation Type: role-based or feature-based installation 
- Server Selection: Select a server from the server pool (DC, the only Server that we have, which we're on)
- Server Roles: Active Directory and Directory Services 
- AD DS: Next
- Confirmation: Install


It will take a while for it to install.


Click "Add roles and features"

![08_05_22_08_16_37](https://user-images.githubusercontent.com/112909705/191372971-e5dd7eb2-1f7c-4057-b3ee-aef4cc3f5d3c.png)

Click "Next"

![08_05_22_08_17_19](https://user-images.githubusercontent.com/112909705/191373017-7a329718-d497-4669-90c6-2d2044acb8b8.png)


- Have "Role-based or feature-based installation" selected
- Click "Next"

![08_05_22_08_18_16](https://user-images.githubusercontent.com/112909705/191373052-451d3a2c-bae5-4169-91bc-0cbfe37e4661.png)


Have our DC selected and click "Next"

![08_05_22_08_19_48](https://user-images.githubusercontent.com/112909705/191373145-78ccf4d4-6cdb-4620-813d-2b1339f7f636.png)

Click "Active Directory Domain Services"

![08_05_22_08_23_26](https://user-images.githubusercontent.com/112909705/191373336-e49a2ae4-6a1a-4308-8aac-db0fd404b85d.png)

Click "Add Features"

![08_05_22_08_24_36](https://user-images.githubusercontent.com/112909705/191373497-9ecbabe5-dfed-4940-8fbc-d62346aea103.png)

Click "Next"

![08_05_22_08_26_26](https://user-images.githubusercontent.com/112909705/191373530-98be1137-deb2-419a-8a1e-1970669dfa0d.png)

Click "Next"

![08_05_22_08_27_11](https://user-images.githubusercontent.com/112909705/191373620-6874fa8f-9d5d-4f6b-a682-54a4fd34f61d.png)

Click "Install"

![08_05_22_08_27_43](https://user-images.githubusercontent.com/112909705/191374071-b9e44642-fea2-4613-b306-70a45d776557.png)


Installation might take a while. 

- Click "Close"

![08_05_22_08_29_04](https://user-images.githubusercontent.com/112909705/191374118-31bf0d95-56ea-402d-8854-b4d23f5c85fd.png)


