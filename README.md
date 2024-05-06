<h1>Network Activities</h1>

<h2>Description</h2>
In this lab, we will create a Windows 10 and Ubuntu Server virtual machines (VM) in Azure and perform some network activities. Specifically, we will work with Azure Network Security Groups (Firewall Resources), Wireshark (a protocal analyzer), and a bunch of command-line tools. The purpose of this lab is to gain a better understanding of firewalls and solidify our understanding of network protocols and ports.
<br />

<h2>Environments Used </h2>

- <b>Windows 10</b> (22H2)
- <b>Ubuntu Server</b> (22.04 LTS)

<h2>Network Protocal and Ports</h2>
A network protocal is an establish set of rules that determine how data is transmitted between different devices in the same network.
There are two protocals that are used for transmitting data over networks, particularly the internet. These protocals are TCP and UDP. TCP (Transmission Control Protocal) is a connection-oriented protocol, meaning it gaurantees dilivery of network traffic. UDP (User Datagram Protocal) this is the best dilivery of network traffic as its much quicker with less overhead. The biggest downside of this method is that the traffic might not get to its destination.
  
<h2>Creating Windows 10 VM in Azure:</h2>
The first thing we will do is create a Windows 10 VM in Azure. Follow the following images below and create an exact replica VM. Don't create a resource group; we will let Azure create a resource group for us. <br/>
<img src="https://github.com/alibashir7/Network-Activities/assets/165006117/242dd479-7ebb-4248-a534-e792ed508721" height="80%" width="80%" alt=/>
<br />
<br />
<img src="https://github.com/alibashir7/Network-Activities/assets/165006117/8285c48e-231d-43f5-a21a-117b6fab4acf" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/18540b1f-9215-4274-8dd7-d922ecd47e37" height="80%" width="80%" alt=/>
<br />
Make sure to create your own username and password for the VM; we will use them to log into the computer.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/ce0637dc-23aa-4aa0-8c65-d30419e74fbe" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/95fd480c-88c6-4ce4-bc1f-7ab4d2558287" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/c7cfc032-6511-4961-8969-9920a3121cd4" height="80%" width="80%" alt=/>
<br />
Open Remote Desktop Connection on your computer and type in the public IP address of your VM shown in the VM portal. Follow it up by entering the VM credentials we created.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/eab64446-3072-499c-8a59-810dfc12d0c8" height="80%" width="80%" alt=/>
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/8ec1e818-910a-4926-a18f-25959d1fac9d" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/125dd822-ab7b-4e4b-a943-e0e02cf2ab2a" height="80%" width="80%" alt=/>
<br />
<br />
You will now be logged into the Windows 10 VM. Go through the setup screen until you arrive at the homepage.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/01a903eb-1bd5-4e5d-836c-e3c5bf8ad174" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/d5547679-70be-4ad0-8e1e-8e970d774004" height="80%" width="80%" alt=/>
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
<img src="https://github.com/alibashir7/Network-Activities/assets/165006117/e8996971-23e9-47f8-bb7b-f84ee8d8b5cf" height="80%" width="80%" alt=/>
<br />
<br />
<img src="https://github.com/alibashir7/Network-Activities/assets/165006117/c76c34c8-b9bf-48c7-9a08-ba3e09cea3bf" height="80%" width="80%" alt=/>
<br />
<br />
We will name this machine VM2, and we will add it to VM 1's resource group. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/3c2addfc-8b28-4a72-a7d7-1d1c18a75e99" height="80%" width="80%" alt=/>
<br />
<br />
Once again, don't forget to create your own username and password for the VM's login credentials. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/c3abb536-aef7-4312-a8e4-a7fc97ddff18" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/9cbb81cd-8a8d-411d-aa7c-5df51c8a3e6c" height="80%" width="80%" alt=/>
<br />
<br />
Make sure the virtual network is set to VM1 (vnet).
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/befd9e08-c073-400b-a5ed-8fc06dbee378" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/0919568a-187d-45d1-afed-e2d849ca7bb4" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/ad3126c0-7b0d-4eae-a925-2779bada8671" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/9c490919-8454-492e-90bf-343b7897ac33" height="80%" width="80%" alt=/>
<br />
<br />

<h2>Wireshark, Network Security Groups, and Protocals:</h2>

Now we will go back into VM 1 and open the wireshark application we downloaded. Once open, we will click the blue icon in the top left corner of the screen.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/de3905d0-5b6a-4b44-8e45-8e5deebda850" height="80%" width="80%" alt=/>
<br />
<br />
You will now see the live traffic that is happening on our VM. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/3aae714c-dcad-406f-9bd0-374f9bd048aa" height="80%" width="80%" alt=/>
<br />
<br />
To filter the traffic that is coming through in the search bar, we will type icmp and hit enter. ICMP (Internet Control Messaging Protocal) is a protocal that Ping uses. Ping is used to test the connectivity between different hosts on the network or internet. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/3e90ac7e-d58b-47b7-a4df-421084c3242b" height="80%" width="80%" alt=/>
<br />
<br />
Next, quickly go back to our Azure portal and make note of the private IP address of our VM2. Proceed back into VM1, and open the command prompt using the start menu. Open it as an administrator. Once open, we will ping our VM2 using the private IP address we copied, as shown in the image below. Right away, you'll see the live ICMP traffic on Wireshark. You'll see the request and reply traffic that is generated from both machines. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/7005cf49-d3e5-4387-8297-ab8ce93daa75" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/447b28b6-b923-49ae-a6d5-113c8ff56b9d" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/3a6fe906-40d6-4fdc-8f33-99b8fa83dded" height="80%" width="80%" alt=/>
<br />
<br />
Now ping apple.com, and once again, we see the traffic that is generated in Wireshark. After that, type in the command prompt ping -t 10.0.0.5. In your case, this will be the private IP address of your VM2. This will generate a continuous ping in the command prompt, which you will see in wireshark. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/a5dd5e74-a55f-45a2-a64b-e27cad338ea7" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/VUbjVP5.png" height="80%" width="80%" alt=/>
<br />
<br />
What we will do now is go into our Azure portal and change the firewall in our VM2 to not allow ICMP traffic to come through. When we do that, this should interrupt the traffic coming through our ping request in the command prompt. Essentially, what it'll do is prevent our VM1 from receiving reply messages from our VM2. To do this, we will go to the network security group in our Azure portal, select VM2, head to inbound security rules, and add a new rule. Follow along below.
<br /><img src="https://imgur.com/VUbjVP5.png" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/7ecd66d5-7adc-41d4-9f6a-3ffbce8c19f2" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://imgur.com/EhqRzVz.png" height="80%" width="80%" alt=/>
<br />
<br />
Fill in the following below and hit add. If at any time you are confused about exactly what we are doing, you can click the i icon next to each rule.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/f4a007ba-b340-4478-a007-a73a9b71c0d3" height="80%" width="80%" alt=/>
<br />
<br />
The rule will be added upon successful completion.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/f15ee35e-efd3-417f-98d5-393d601eb129" height="80%" width="80%" alt=/>
<br />
<br />
Give your VM1 some time, and you should see the ping request start to time out in the command prompt. You'll also notice in wireshark that VM1 is requesting but receiving no reply from VM2. This is because it is getting blocked by VM2's firewall.  
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/954b7f5d-fe68-44b1-a3c1-4cfcb2d85093" height="80%" width="80%" alt=/>
<br />
<br />
Let's delete the rule now, and everything should go back to normal.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/161199b6-a720-4209-9362-9ca5f1c48a18" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/795d37d0-1108-4317-85a6-38b7f7163756" height="80%" width="80%" alt=/>
<br />
<br />
Give wireshark and the command prompt a moment, and you should start to see the ping request work like normal again. To stop the continous ping just hit Ctrl C on your keyboard.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/ec27fb55-37bc-4f75-b9ae-e1f73c51ad9a" height="80%" width="80%" alt=/>
<br />
<br />
Next, we will explore SSH traffic on Wireshark. SSH (Secure Shell Protocal) is like a remote desktop connection, except it only gives us access to the other computer's command line. Once again, type in ssh in the wireshark search bar and hit enter. We are now filtering through ssh traffic.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/cbecf10d-e5c8-49bc-8187-c083bef0c825" height="80%" width="80%" alt=/>
<br />
<br />
Now to ssh into our VM2, we will type in the command prompt: ssh username@private IP address VMs. In my case, that will be ssh cclabusers@10.0.0.5. We will be presented with yes or no; type in yes, then type in your VM2's password. You will not be able to see the password you type in on your screen, so if you get it wrong, just keep trying until you type it in correctly. As we are trying to ssh into our VM2 you will see the ssh traffic generating in wireshark.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/e299ba7e-5093-4ce7-88b6-0568eee98d8a" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/4d7b1b8f-c0ad-44ed-8bdd-bc3a8eeeef93" height="80%" width="80%" alt=/>
<br />
<br />
Anytime we type in a command in the terminal of VM2 you will see it generate traffic in wireshark. To get out of the ssh we just type in exit and it returns us to our VM1 terminal.
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/9a992b5a-3699-4135-ac2c-ba79f8d93cba" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/df05dc33-7cb0-4546-8f68-5e1a18a497ee" height="80%" width="80%" alt=/>
<br />
<br />
Now we will filter traffic for dhcp. DHCP(Dynamic Host Configuration Protocal) is used to automatically assign an IP address to a host. To trigger dhcp traffic lets type in the terminal ipconfig /renew. This command is used to automatically  assign our IP address to a host. 
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/1485ee53-87ce-4a84-9ca4-413c9c7067c5" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/1b090971-0b91-4dc5-8400-c6e840a45ad7" height="80%" width="80%" alt=/>
<br />
<br />
<br /><img src="https://github.com/alibashir7/Network-Activities/assets/165006117/d233b35d-f477-42fc-ae35-08a806b73b82" height="80%" width="80%" alt=/>
<br />
<br />

<h2> Conclusion </h2>
