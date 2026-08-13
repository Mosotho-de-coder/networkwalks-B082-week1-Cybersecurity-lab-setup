# networkwalks-B082-week1-Cybersecurity-lab-setup
Cybersecurity lab setup

# Project Overview
This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.
The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.
The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

# Objectives
Here are the main objectives of this project:
* Install and configure VirtualBox.
* Install/import Kali Linux as a virtual machine.
* Create a private NAT Network for the cybersecurity lab.
* Configure network connectivity for Kali Linux.
* Assign a consistent IP address to the Kali VM.
* Verify network connectivity and DNS resolution.
* Take a clean VM snapshot for recovery.
* Document the complete setup process.
* Prepare the environment for future cybersecurity projects.

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
# Step 1. Download & install 7-zip:
7-Zip was installed and was used to extract Kali Linux virtual-machine package, which may be distributed as a .7z archive.
Tool: 7-Zip
# Step 2. Install VirtualBox
VirtualBox was installed and used as the hypervisor.
# Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.
Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled
<img width="1916" height="1022" alt="image" src="https://github.com/user-attachments/assets/b65528ce-b25e-4348-af96-006d87caf888" />
A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.
This will allow future attacker and target VMs to communicate within the lab.

# Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.
The VM network adapter was configured as follows:
<img width="976" height="650" alt="image" src="https://github.com/user-attachments/assets/e8c98b5b-0f73-4f09-a39f-26270f372953" />

The virtual machine was allocated:
<img width="977" height="647" alt="image" src="https://github.com/user-attachments/assets/924b2da8-0314-4dd9-a2f4-723691d820a1" />
Running imported Kali from VirtualBox:
<img width="1917" height="926" alt="image" src="https://github.com/user-attachments/assets/cfc59892-8bab-4bd4-a274-46c3c9f556f3" />
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

# Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.
A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.
<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/1583296e-c25e-4e61-9677-963ea2bdfd38" />

# Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.
here is the snapshot of Kali Linux VM:
<img width="1918" height="955" alt="image" src="https://github.com/user-attachments/assets/16cc2da8-05da-421d-87b9-e0ebfb035bda" />
The snapshot represents the clean baseline of the laboratory.
If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

# Lab Verification

