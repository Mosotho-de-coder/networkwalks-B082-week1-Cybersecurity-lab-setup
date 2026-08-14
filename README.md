# networkwalks-B082-week1-Cybersecurity-lab-setup
Cybersecurity lab setup

# Project Overview
This repository documents the setup I completed during Week 1 of the Networkwalks Ethical Hacking & Cybersecurity internship.
For this task, I created a virtual cybersecurity environment using VirtualBox and Kali Linux. The idea is to have a safe lab where I can practice the cybersecurity techniques covered during the training without interfering with real systems.
The lab will also serve as the foundation for the practical exercises that will follow in the coming weeks

# Week 1 Objectives
For this week's practical, I needed to:
* Set up 7-Zip for extracting the required VM files.
* Install VirtualBox on my computer.
* Create a 10.0.0.0/24 NAT Network.
* Import and configure the Kali Linux virtual machine.
* Configure Kali Linux with the required network settings.
* Check that the network connection was working properly.
* Save a clean snapshot of the configured Kali VM.
* Record my setup and results using screenshots.


# Lab Configuration
| 🧩Components | ⚙️Configurations |
| --- | --- |
| 🖥️ Host OS  | Windows 11 |
| 🧠 Host RAM | 8 GB |
| ⚡ Processor | Intel core i3 |
| 🧰 Hypervisor | VirtualBox 7.2.14|
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.120 |

# Lab Setup Procedure
## Step 1. Download & install 7-zip:
I installed 7-Zip on my Windows computer before working with the Kali Linux VM files.
I used it to extract the compressed Kali Linux virtual-machine package so that the files could be imported into VirtualBox.
## Step 2. Install VirtualBox
I installed VirtualBox and used it to create and manage the virtual machine for this cybersecurity lab.
Once VirtualBox was ready, I moved on to configuring the virtual network that would be used by Kali Linux.
## Step 3. Create the NAT Network
I created a NAT Network in VirtualBox and named it NatNetwork.
The network was configured with the following settings:
* Network: NatNetwork
* IPv4 Prefix: 10.0.0.0/24
* DHCP: Enabled
* IPv6: Disabled
<img width="1916" height="1022" alt="image" src="https://github.com/user-attachments/assets/b65528ce-b25e-4348-af96-006d87caf888" />
I chose this network because it gives the virtual machines their own network while still allowing them to access external networks. It also gives me a suitable network for adding other machines to the lab later.

## Step 4. Import Kali Linux
I downloaded the Kali Linux virtual machine and imported it into VirtualBox.
After importing it, I connected the VM's network adapter to the NatNetwork I created in the previous step:
<img width="976" height="650" alt="image" src="https://github.com/user-attachments/assets/e8c98b5b-0f73-4f09-a39f-26270f372953" />

I also checked the resources assigned to the virtual machine and allocated 2048 MB of RAM to Kali Linux:
<img width="977" height="647" alt="image" src="https://github.com/user-attachments/assets/924b2da8-0314-4dd9-a2f4-723691d820a1" />
After the configuration was complete, I started Kali Linux successfully from VirtualBox:
<img width="1917" height="926" alt="image" src="https://github.com/user-attachments/assets/cfc59892-8bab-4bd4-a274-46c3c9f556f3" />
I also configured a shared folder to make transferring files between my Windows host and Kali Linux easier.

## Step 5. Configure the Kali Linux Network
I configured the Kali Linux network settings so that the VM could use the address assigned for the lab.
My target configuration was:
* IP Address: 10.0.0.2/24
* Gateway: 10.0.0.1
* DNS: 8.8.8.8
<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/1583296e-c25e-4e61-9677-963ea2bdfd38" />

## Step 6. Create a Clean VM Snapshot
Once I was satisfied that the initial Kali setup was working, I created a snapshot of the virtual machine:
<img width="1918" height="955" alt="image" src="https://github.com/user-attachments/assets/16cc2da8-05da-421d-87b9-e0ebfb035bda" />
This gives me a working restore point. If I make changes during a future cybersecurity exercise and something goes wrong, I can return to 
this version instead of rebuilding the entire environment.

# Lab Verification
|✅ Test	|🧾 Command	|🎯 Expected Result|
| --- | --- | --- |
| 🌐 IP address |	ip a	| Confirmed the Kali IP address |
|📡 gateway connection	| ping 10.0.0.1 |	Checked communication with the gateway |
|🌍 Internet connection	| ping 8.8.8.8	| Checked external connectivity |
|🔎 DNS	 | nslookup networkwalks.com	| Checked that DNS resolution was working |
|🧰 Nmap	 | nmap --version	| Confirmed Nmap was available |
|🔄 Snapshot	 | Restore snapshot + ip a | Confirmed the saved configuration could be restored |

## Results
The checks were performed after configuring the Kali network. The results confirmed that the VM was using the expected network configuration and that the lab was ready for the next practical exercises.


# Problems Encountered & Solutions
## Kali Linux Network Connection
After configuring the static IPv4 settings, Kali Linux did not immediately connect through the expected network configuration.
To refresh the connection, I brought the eth0 interface down and then brought it back up from the Kali terminal.
sudo ifconfig eth0 down
After entering my password and waiting for the interface to disconnect, I brought it back online:
sudo ifconfig eth0 up
I then checked the network configuration and tested the connection again. After reconnecting the interface, Kali was communicating correctly and the network was working as expected.

# What I Learned
## Working With Virtual Networks
This exercise gave me more practical experience with how VirtualBox connects a virtual machine to a NAT Network and howthe network settings affect connectivity.
## Kali Linux Network Configuration
I practiced checking and configuring IP addresses, gateways, and DNS settings directly inside Kali Linux.
## Troubleshooting
The network issue gave me a chance to troubleshoot the connection from the terminal instead of simply restarting the whole virtual machine.
## Snapshots
I also understood the value of creating a clean snapshot before starting future cybersecurity exercises. It gives me a reliable point to return to if something goes wrong.
## Documentation
Finally, I learned the importance of recording the configuration, commands, screenshots, and troubleshooting steps as part of a technical cybersecurity project.

# Week 1 Status
## Lab setup completed successfully.
My Kali Linux environment is configured, the network connection has been tested, and a clean VM snapshot has been created. The lab is now ready for the upcoming Ethical Hacking & Cybersecurity practical exercises.
