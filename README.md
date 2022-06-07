<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
Project includes a simple setup of an Active Directory home lab environment where I can learn to understand how active directory works.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>

<h2>Program walk-through:</h2>

<p align="center">
<h3>Set up the lab: </h3>
 I downloaded isos for Windows Server 2019 and Windows 10 Enterprise. I changed network settings for Windows Server 2019 where I changed Adapter 1 to NAT and Adapter 2 to internal network.
<br />
I changed the network settings for the Windows Server 2019 Image by going to the internal connection and changing the properties and put the ip address 172.16.0.1 with /24 as the subnet mask. No need for a gateway, as the IP for the internal network is itself. For the DNS sever, I used 127.0.0.1 as it is a loopback address which means that it loops back to itself. <br />
<br /> 
 Internet Access: <br/>
<img src="https://i.imgur.com/2uFKdYt.jpg" height="80%" width="80%" alt="Internet Access"/>
<br />
<h3>Create Groups in Active Directory Users and Computers: </h3>
I created new groups in Active Directory Users and Computers, one for admins and one for users. I wanted to create an administrative account.

<br>New Groups in Active Directory:  <br/>
<img src="https://i.imgur.com/UZA6x3c.jpg" height="80%" width="80%" alt="New Groups in Active Directory"/>
<br />
<br />
<h3>Configure DHCP to allow clients to receive their own IP addresses to connect to the internet. </h3>
Once you added DHCP to Server Manager, you can go to DHCP to configure settings. I went to IPv4 and gave a range of 172.16.0.100-200 and a subnet of /24. DHCP gives out IP addresses to devices on a lease, meaning the other devices do not keep their ip addresses, the devices would have to request to the DHCP server to refresh the ip address so the device can keep using it. Then I added the ip address of the gateway "172.16.0.1" to make it so devices connect to the gateway will receive their IP address from the DHCP server.
<br />
 <br>DHCP Configuration:</br>
<img src="https://i.imgur.com/uDRN4wy.jpg" height="80%" width="80%" alt="DHCP"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
