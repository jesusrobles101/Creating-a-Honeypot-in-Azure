## Configuring Honeypot VMs in Azure
![Open NSG](https://github.com/user-attachments/assets/c0ba0b4d-f043-49d5-99b1-a0fdc60a0f4b)

 To create a Vulnerable Environment for this project the first thing we need to do is deploy as many virtual machines as we need. For this project, I deployed two VMs, one Linux and one Windows OS. Next, I configured the Network Security Groups to allow all inbound connections from any source to any port.
 - Log into your Azure account and select Virtual Machines.
 - Click on the "+" to create a new Virtual Machine.
 - Make sure both machines are in the same resource group, region, and Virtual Network.
 - Once the Windows VM is created log into it through RDP and turn off all firewall settings
 - type wf.msc into the search bar and click
 - Click Windows Defender Firewall Properties

![image](https://github.com/user-attachments/assets/7c3c339d-4804-4b40-b885-28eca5856ca4)

   - On Domain, Public, and Private Profiles choose "off" under "Firewall State".

![image](https://github.com/user-attachments/assets/5e5bf4c9-36ca-401b-81a6-6cfdbeba9519)

- Back in Azure's search bar type "Network Security Groups"
- All the VMs you have set up will show their NSG. Click one and add a new rule that allows inbound connections to all ports
- Set the priority to the lowest of all the rules. This will ensure this rule will always be followed. 

![image](https://github.com/user-attachments/assets/81ccc521-41b9-45f3-8559-d0bb933779db)

If you would like to check if the VM is allowing inbound traffic you can open the administrator command prompt and type "ping" then the VM IP address. 

## Conclusion
Creating multiple machines that are open to the internet essentially creates a honey net that will allow attackers to attempt to log into your VMs as much as they want. This isn't something that you would want to do in a real environment (unless you were creating a real honeynet for a company, but you would probably make it much more complex than we are in this project). Now you have a honeynet set up that allows all traffic through, allowing you to attract and observe attackers in a controlled environment. 
