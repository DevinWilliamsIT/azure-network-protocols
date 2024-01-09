<p align="center">
</p>

![image](https://github.com/DevinWilliamsIT/azure-network-protocols/assets/155914712/92da05e4-aff4-4ff1-9023-a002ef9f195d)

<h1>Building intuition for DNS</h1>
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

In this tutorial we are going to
<ul>
  <li>Inspect DNS A-Records</li>
  <li>Create some of our own A-records on the server and observe them from the client</li>
  <li>Delete records from server and clear the client DNS cache to gain understanding</li>
  <li>Touch on "CNAME" records</li>
</ul>

<p>
  <b>Note: You must complete the Configuring On-premises Active Directory within Azure VMs lab before continuing with this since they are connect.</b>
</p>

<h2>Actions and Observations</h2>

<br />

<p>
 1. Firstly, we are going to do an A-Record Exercise.
  <li>Connect/log into DC-1 as your domain admin account (mydomain.com\steph_admin)</li>
  <li>Connect/log into Client-1 as an admin (mydomain\steph_admin)</li>
  <li>From Client-1 try to ping “mainframe” notice that it fails</li>
  <li>Nslookup “mainframe” notice that it fails (no DNS record)</li>
  <li>Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address</li>
  <li>Go back to Client-1 and try to ping it. Observe that it works</li>
</p>

![image](https://github.com/DevinWilliamsIT/azure-network-protocols/assets/155914712/f1b95415-a504-4afa-9f65-2fcc0956d943)

<p>
 An "A" record in DNS maps a domain name to an IP address, ensuring that when users access the domain, the DNS system knows which server to direct the request to. Without "A" records, websites and services wouldn't be accessible via their domain names.
</p>

![image](https://github.com/DevinWilliamsIT/azure-network-protocols/assets/155914712/0bd610d9-3de5-4586-abf8-05aa15b31c67)

![image](https://github.com/DevinWilliamsIT/azure-network-protocols/assets/155914712/084aa36b-7cac-4b84-b717-e5d8a99cfebf)

![image](https://github.com/DevinWilliamsIT/azure-network-protocols/assets/155914712/14e5145c-d9e5-4b37-bc72-1e0dd0703e9a)

![image](https://github.com/DevinWilliamsIT/azure-network-protocols/assets/155914712/6a380a91-08c4-4982-b2a1-fc0566623e99)

<br />

<p>
2. Next we are going to do a local DNS cache exercise.
  <ul>
    <li>Go back to DC-1 and change mainframe’s record address to 8.8.8.8</li>
    <li>Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address</li>
    <li>Observe the local dns cache (ipconfig /displaydns)</li>
    <li>Flush the DNS cache (ipconfig /flushdns). Observe that the cache is empty</li>
    <li>Attempt to ping “mainframe” again. Observe the address of the new record is showing up</li>
    </ul>
</p>









<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
