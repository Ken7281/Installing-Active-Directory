# Installing-Active-Directory
<p align="center">

</p>

<h1>Active Directory - Installation</h1>
This tutorial outlines the installation of Active Directory using virtual machines in Microsoft Azure.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

*Create a virtual machine in Microsoft Azure for the Domain Controller*
*Name the Virtual Machine DC-1*

![Creating The Domain Controller VM (1)](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/c60d0705-38ef-4461-8ab2-01d263ea3008)

![Creating The Domain Controller VM (2)](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/42af2b74-f79d-4e95-94fa-81444b5feb92)

*Create a second virtual machine for the client*
*Name the virtual machine Client-1 and make sure the virtual machine is within the same resource group as DC-1*


![Creating The Client-1 VM](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/440952fb-c38e-44f2-a353-1847ddfc152c)

*Change DC-1's IP adress from dynamic to static by selecting DC-1's network interface*

![Setting DC-1 IP Adress to Static](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/f5b12438-4233-48ef-aa7d-286fb8faf81d)

*Now we have to ensure the virtual machines are able to communicate*

*Connect to the Client-1 virtual machine using remote desktop*
*Connect to the Dc-1 virtual machine using remote desktop*

*On DC-1 open the windows firewall from the start menu*

![Getting To The Windows Firewall](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/911ba5f2-7026-492f-80bc-5bce3076301a)

*Select inbound rules, filter the seacrch by clicking on the protocol tab and search for the ICMpv4* 
*Right click and select enable rule on both of the ICMP Echo Request* 

![Allowing ICMPv4 Traffic](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/0a418e6f-23b3-46a2-98ee-530479a21f86)

*This enables DC-1 and Client-1 virtual machines to communicate*

*On DC-1 select "add roles and features" on the windows server manager.* 

![Adding Roles   Features](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/b8669182-dbda-4669-9da1-6fe6cf4eb798)

*Select next until you get to the select server roles section and select "Active Directoty Domain Services" and select add features* 
*Click next and select install* 

![Installing Active Directory Onto DC1](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/a7fac71c-5978-4ffd-9285-53b39c4208a0)

*On the windows server manager click the notifications icon and select "promote this server to a domain controller"* 

![Promoting DC1 To A Domain Controller](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/a2584922-4f07-49e3-a1a3-c66750236526)

*Click the "add a new forest" bubble and create a name for the domain and select next*
*Create a password for the domain and select next until you can select install*

*After installation the remote desktop connection will be severed but Active Directory will be successfully installed onto the DC-1 virtual machine*

*To log onto DC-1 you have to use the fully qualified domain name* *Using the mydomain.com that we just created as well as the username for the virtual machine*

![Logging Into DC-1 With New Credentials](https://github.com/Ken7281/Installing-Active-Directory/assets/142465932/6bde9218-7ab4-4f18-b9ec-07c454635a31)
