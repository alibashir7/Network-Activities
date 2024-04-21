<h1>Network Activities</h1>

<h2>Description</h2>
In this lab, we will create a Windows 10 and Ubuntu Server virtual machines (VM) in Azure and perform some network activities. Specifically, we will work with Azure Network Security Groups (Firewall Resources), Wireshark (a protocal analyzer), and a bunch of command-line tools. The purpose of this lab is to gain a better understanding of firewalls and solidify our understanding of network protocols and ports.
<br />

<h2>Environments Used </h2>
- <b>Windows 10</b> (21H2)

<h2>Network Protocal and Ports</h2>
A network protocal is an establish set of rules that determine how data is transmitted between different devices in the same network.
There are two protocals that are used for transmitting data over networks, particularly the internet. These protocals are TCP and UDP. TCP (Transmission Control Protocal) is a connection-oriented protocol, meaning it gaurantees dilivery of network traffic. UDP (User Datagram Protocal) this is the best dilivery of network traffic as its much quicker with less overhead. The biggest downside of this method is that the traffic might not get to its destination.
  
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
<br />

<h2>Downloading Wireshark in VM1:</h2>

At this point, watch the following video in order to download Wireshark on your VM. Make sure the wireshark installation is done on your VM and not your personal computer, and use the Edge browser in order to do so. https://youtu.be/Y-JNp_DDQ9w?si=0tep_5WhHWXqFWlG 

When you finish you should see the Wireshark application on your VM's home page. If not, you can search for the application in the Windows Start menu.
<br /><img src="https://imgur.com/YPb4Q3q.png" height="80%" width="80%" alt=/>
<br />
<br />

<h2>Creating Ubuntu Server VM in Azure:</h2>

Now we will create an Ubuntu Server VM in Azure. Ubuntu is an open-source operating system that runs on Linux. Follow the example below to create an exact replica of the of the VM. 
<img src="https://imgur.com/tKEqePl.png" height="80%" width="80%" alt=/>
<br />
<br />
<img src="https://imgur.com/MSrkkNk.png" height="80%" width="80%" alt=/>
<br />
<br />
We will name this machine VM2, and we will add it to VM 1's resource group. 
<br /><img src="https://imgur.com/DxyyHxM.png" height="80%" width="80%" alt=/>
<br />
<br />
Once again, don't forget to create your own username and password for the VM's login credentials. 
<br /><img src="https://imgur.com/5H5JFuf.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/5SLIpSA.png" height="80%" width="80%" alt=/>
<br />
<br />
Make sure the virtual network is set to VM1 (vnet).
<br /><img src="https://imgur.com/kkRCkdA.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/zX5PdM9.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/3eRLwJk.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/wrcJ70j.png" height="80%" width="80%" alt=/>
<br />
<br />

<h2>Wireshark, Network Security Groups, and Protocals:</h2>

Now we will go back into VM 1 and open the wireshark application we downloaded. Once open, we will click the blue icon in the top left corner of the screen.
<br /><img src="https://imgur.com/lAZ6EBx.png" height="80%" width="80%" alt=/>
<br />
<br />
You will now see the live traffic that is happening on our VM. 
<br /><img src="https://imgur.com/XJSaLb4.png" height="80%" width="80%" alt=/>
<br />
<br />
To filter the traffic that is coming through in the search bar, we will type icmp and hit enter. ICMP (Internet Control Messaging Protocal) is a protocal that Ping uses. Ping is used to test the connectivity between different hosts on the network or internet. 
<br /><img src="https://imgur.com/5s3fEHw.png" height="80%" width="80%" alt=/>
<br />
<br />
Next, quickly go back to our Azure portal and make note of the private IP address of our VM2. Proceed back into VM1, and open the command prompt using the start menu. Open it as an administrator. Once open, we will ping our VM2 using the private IP address we copied, as shown in the image below. Right away, you'll see the live ICMP traffic on Wireshark. You'll see the request and reply traffic that is generated from both machines. 
<br /><img src="https://imgur.com/PpBQbSy.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/4jSybms.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/eMXo5xt.png" height="80%" width="80%" alt=/>
<br />
<br />
Now ping apple.com, and once again, we see the traffic that is generated in Wireshark. After that, type in the command prompt ping -t 10.0.0.5. In your case, this will be the private IP address of your VM2. This will generate a continuous ping in the command prompt, which you will see in wireshark. 
<br /><img src="https://imgur.com/tQbCng7.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/amcbB2g.png" height="80%" width="80%" alt=/>
<br />
<br />
What we will do now is go into our Azure portal and change the firewall in our VM2 to not allow ICMP traffic to come through. When we do that, this should interrupt the traffic coming through our ping request in the command prompt. Essentially, what it'll do is prevent our VM1 from receiving reply messages from our VM2. To do this, we will go to the network security group in our Azure portal, select VM2, head to inbound security rules, and add a new rule. Follow along below.
<br /><img src="https://imgur.com/VUbjVP5.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/v3qhv5A.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/EhqRzVz.png" height="80%" width="80%" alt=/>
<br />
<br />
Fill in the following below and hit add. If at any time you are confused about exactly what we are doing, you can click the i icon next to each rule.
<br /><img src="https://imgur.com/gQEpnp5.png" height="80%" width="80%" alt=/>
<br />
<br />
The rule will be added upon successful completion.
<br /><img src="https://imgur.com/04p50Cg.png" height="80%" width="80%" alt=/>
<br />
<br />
Give your VM1 some time, and you should see the ping request start to time out in the command prompt. You'll also notice in wireshark that VM1 is requesting but receiving no reply from VM2. This is because it is getting blocked by VM2's firewall.  
<br /><img src="https://imgur.com/JuGaVwb.png" height="80%" width="80%" alt=/>
<br />
<br />
Let's delete the rule now, and everything should go back to normal.
<br /><img src="https://imgur.com/e27IUdg.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/pEqvKPj.png" height="80%" width="80%" alt=/>
<br />
<br />
Give wireshark and the command prompt a moment, and you should start to see the ping request work like normal again. To stop the continous ping just hit Ctrl C on your keyboard.
<br /><img src="https://imgur.com/6EaqfW0.png" height="80%" width="80%" alt=/>
<br />
<br />
Next, we will explore SSH traffic on Wireshark. SSH (Secure Shell Protocal) is like a remote desktop connection, except it only gives us access to the other computer's command line. Once again, type in ssh in the wireshark search bar and hit enter. We are now filtering through ssh traffic.
<br /><img src="https://imgur.com/FomkYCJ.png" height="80%" width="80%" alt=/>
<br />
<br />
Now to ssh into our VM2, we will type in the command prompt: ssh username@private IP address VMs. In my case, that will be ssh cclabusers@10.0.0.5. We will be presented with yes or no; type in yes, then type in your VM2's password. You will not be able to see the password you type in on your screen, so if you get it wrong, just keep trying until you type it in correctly. As we are trying to ssh into our VM2 you will see the ssh traffic generating in wireshark.
<br /><img src="https://imgur.com/PrGllvB.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/EIsCZhk.png" height="80%" width="80%" alt=/>
<br />
<br />
Anytime we type in a command in the terminal of VM2 you will see it generate traffic in wireshark. To get out of the ssh we just type in exit and it returns us to our VM1 terminal.
<br /><img src="https://imgur.com/9nfJ3aN.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/YYDWpWv.png" height="80%" width="80%" alt=/>
<br />
<br />
Now we will filter traffic for dhcp. DHCP(Dynamic Host Configuration Protocal) is used to automatically assign an IP address to a host.
<br /><img src="https://imgur.com/4RuMNzb.png" height="80%" width="80%" alt=/>
<br />
<br />
To trigger dhcp traffic lets type in the terminal ipconfig /renew. This command is used to automatically  assign our IP address to a host. 
<br /><img src="https://imgur.com/RXjJiPX.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/kkqB93G.png" height="80%" width="80%" alt=/>
<br />
<br />

<h2> Conclusion </h2>
