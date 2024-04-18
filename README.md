<h1>Network Activities</h1>

<h2>Description</h2>
In this lab, we will create a Windows 10 and Ubuntu virtual machines (VM) in Azure and perform some network activities. Specifically, we will work with Azure Network Security Groups (Firewall Resources), Wireshark (a protocal analyzer), and a bunch of command-line tools. The purpose of this lab is to gain a better understanding of firewalls and solidify our understanding of network protocols and ports.
<br />

<h2>Environments Used </h2>
- <b>Windows 10</b> (21H2)

  
<h2>Creating Windows 10 VM in Azure:</h2>

The first thing we will do is create a Windows 10 VM in Azure. Follow the following images below and create an exact replica VM. Don't create a resource group; we will let Azure create a resource group for us. <br/>
<img src="https://imgur.com/tKEqePl.png" height="80%" width="80%" alt=/>
<br />
<br />
<img src="https://imgur.com/MSrkkNk.png" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://imgur.com/nRapBKP.png" height="80%" width="80%" alt=/>
<br />
Make sure to create your own username and password for the VM; we will use them to log into the computer.
<br /><img src="https://imgur.com/LVirbVS.png" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://imgur.com/kuzsASQ.png" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://imgur.com/P7zCi0I.png" height="80%" width="80%" alt=/>
<br />
Open Remote Desktop Connection on your computer and type in the public IP address of your VM shown in the VM portal. Follow it up by entering the VM credentials we created.
<br /><img src="https://imgur.com/BhnckxK.png" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://imgur.com/o7GQXoN.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/BLP4JKi.png" height="80%" width="80%" alt=/>
<br />
<br />
You will now be logged into the Windows 10 VM. Go through the setup screen until you arrive at the homepage.
<br /><img src="https://imgur.com/IUsSEXm.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/eQBWze4.png" height="80%" width="80%" alt=/>
<br />
<br /><br /><img src=".png" height="80%" width="80%" alt=/>
<br />
<br />
At this point, watch the following video in order to download Wireshark on your VM. Make sure the wireshark installation is done on your VM and not your personal computer, and use the Edge browser in order to do so. https://youtu.be/Y-JNp_DDQ9w?si=0tep_5WhHWXqFWlG

When you finsish you should see the Wireshark application on your VMs home page. If not you can search for the application in the Windows start menu.
<br /><br /><img src="https://imgur.com/undefined.png" height="80%" width="80%" alt=/>
<br />
<br />
