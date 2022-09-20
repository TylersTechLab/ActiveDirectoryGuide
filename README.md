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

