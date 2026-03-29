Lab 01- Azure Virtual Machine
Name: Aadil Hussain
Date Started: 27 March 2026
Status-🔄 In Progress

## Phase 1 - Resource Group ✅ COMPLETED

# What I Did
- Opened Azure Portal at portal.azure.com
- Typed Resource Groups in the top search bar
- Clicked the blue + Create button
- Filled in the form with the settings below
- Clicked Review + create then clicked Create
- Saw the green notification confirming resource group was created

# Settings I Used
Subscription (Azure subscription 1)
Resource group name (rg-lab-vm-01)
Region (Europe) West Europe

# Why I Chose West Europe
UAE North region is not available on the Azure free subscription.
West Europe is the closest available and reliable region.

# What a Resource Group 
A Resource Group is like a project folder in Azure. It keeps all 
related resources like virtual machines, networks, and disks grouped 
together in one place. When I delete the resource group at the end 
of the lab, everything inside gets deleted automatically at once.

# Time Taken
Approximately 5 minutes

# Screenshot
[Resource Group Created](screenshots/01-resource-group-created.png)

## Phase 2 — Virtual Machine ✅ COMPLETED

# What I Did
- Navigated to Virtual Machines in Azure Portal
- Clicked Create then Azure virtual machine
- Filled in all settings on the Basics tab
- Left all other tabs as default
- Clicked Review + create and saw Validation passed
- Clicked Create button
- Downloaded vm-lab-01-key.pem immediately and saved to lab folder
- Waited 3 minutes for deployment to complete
- Went to VM overview and noted the Public IP address

# Settings Used
Resource group (rg-lab-vm-01)
VM name (vm-lab-01)
Region: East asia (West Europe did not have B2s free tier size available)
Image (Ubuntu Server 24.04 LTS x64 Gen2)
Size (Standard_B2s)
Auth type (SSH public key)
Username (azureuser)
Key pair name (vm-lab-01-key)
Inbound port (SSH 22)

# My VM Public IP Address
52.184.18.137

# What I Learned
- A VM is a computer running inside Microsoft's data centre
- Standard_B2s means burstable tier, 1 vCPU, small memory
- SSH key pair is more secure than password authentication
- Azure auto creates a VNet, subnet, NSG and Public IP with every VM
- The .pem file is my private key — Azure never shows it again
- Deployment takes 2 to 3 minutes to complete

# Screenshots
[VM Basics Filled] (screenshots/02-vm-basics-filled.png)01
[VM Basics Filled] (screenshots/02-vm-basics-filled.png)02
[VM Basics Filled] (screenshots/02-vm-basics-filled.png)03
[VM Basics Filled] (screenshots/02-vm-basics-filled.png)04
[Validation Passed] (screenshots/03-vm-validation-passed.png)
[Key Pair Popup] (screenshots/04-key-pair-popup.png)
[Deployment Complete] (screenshots/05-vm-deployment-complete.png)
[VM Overview with IP] (screenshots/06-vm-overview-public-ip.png)

## Phase 3  SSH Connection ✅ COMPLETED

# What I Did
- Opened VS Code terminal with Ctrl and backtick
- Navigated to Lab01-VirtualMachine folder
- Confirmed vm-lab-01-key.pem was in the folder using Get-ChildItem
- Ran SSH command to connect to VM using public IP 52.184.18.137
- Typed yes to accept host fingerprint warning on first connection
- Got Permission denied error first time (key file path had spaces)
- Fixed by copying key file to C:\Users\User\ with no spaces in path
- Ran SSH command again with simple path and connected successfully
- Terminal prompt changed to azureuser@vm-lab-01:~$
- Ran whoami, hostname and uname commands to verify connection

# Problem I Faced and How I Fixed It
SSH could not find the .pem key file because the folder path
contained an apostrophe in "Aadil's Azure Labs" which confused SSH.

Fixed by copying the key file to a exact path:
C:\Users\User\Desktop\Aadil's Azure Labs\Aadil's Lab01-VirtualMachine\vm-lab-01-key_pem

Then ran SSH with the full path and it worked immediately.

# Commands    Used

Command  (What It Does)
Get-ChildItem  (Lists all files in current folder)
ssh -i key.pem azureuser@IP  (Connects to VM using SSH key)
whoami (Shows current logged in username)
hostname (Shows the name of the computer)
uname -a (Shows OS and kernel version)

# SSH Command That Worked
ssh -i " C:\Users\User\Desktop\Aadil's Azure Labs\Aadil's Lab01-VirtualMachine\vm-lab-01-key_pem azureuser@52.184.18.137


# What I Saw After Connecting
whoami → azureuser
hostname → vm-lab-01
uname -a → Linux vm-lab-01 Ubuntu

# What I Learned
- SSH stands for Secure Shell — encrypted remote connection
- Port 22 must be open in NSG for SSH to work
- The .pem file is my private key to authenticate without a password
- File paths with spaces or apostrophes can break SSH on Windows
- The tilde symbol means I am in the home directory of the VM
- The dollar symbol means the terminal is ready for commands
- I am now controlling a computer in Microsoft's data center
  from my PC in Doha Qatar
- First connection always shows a fingerprint warning — type yes

# My VM Details
- Public IP Address: 52.184.18.137
- Username: azureuser
- VM Name: vm-lab-01
- OS: Ubuntu Server 24.04 LTS

# Screenshots
![SSH Connected](screenshots/08-ssh-connected.png)
![VM Verified](screenshots/09-vm-verified.png)

## Phase 4 — Configure VM and Install Nginx ✅ COMPLETED

# What I Did
- Confirmed I was inside the VM showing azureuser@vm-lab-01
- Checked VM resources using uname, free, nproc and df commands
- Updated system packages using apt update and apt upgrade
- Installed Nginx web server using apt install command
- Started Nginx service and enabled auto start on reboot
- Verified Nginx was running showing active running in green
- Opened index.html file using nano text editor
- Deleted default Nginx content
- Pasted custom HTML page with my name and lab details
- Verified page saved correctly using cat command

# Commands I Ran 
(Command) What It Does
(uname -a) Shows OS and kernel version 
(free -h) Shows RAM usage in readable format 
(nproc) Shows number of CPU cores
(df -h) Shows disk space usage 
(sudo apt update) Updates list of available packages
(sudo apt upgrade -y) Installs all available updates
(sudo apt install nginx -y) Installs Nginx web server
(sudo systemctl start nginx) Starts Nginx service right now
(sudo systemctl enable nginx) Auto starts Nginx on every reboot
(sudo systemctl status nginx) Checks if Nginx is running
(sudo nano /var/www/html/index.html) Opens web page file for editing
(cat /var/www/html/index.html) Displays content of web page file

# What I Learned
- sudo means run as administrator on Linux
- apt is Ubuntu's package manager like an app store for terminal
- Always run apt update before installing anything on a new server
- systemctl manages Linux services — start stop enable disable status
- enable makes a service start automatically after every reboot
- No output after a command on Linux usually means success
- nano is a simple text editor built into Linux terminal
- Ctrl X then Y then Enter saves and exits nano editor
- Web pages served by Nginx are stored in /var/www/html/ folder
- index.html is the default page Nginx serves to visitors
- cat command displays the contents of any file in terminal

# My Custom Page Details
- Page title: Aadil's Azure VM Lab
- Deployed by: Aadil Hussain
- VM: Ubuntu Server 24.04 LTS
- Region: North Europe
- Lab: Azure 30-Day Challenge

# Screenshots
![VM Resources](screenshots/10-vm-resources.png)
![System Updated](screenshots/11-system-updated.png)
![Nginx Running](screenshots/12-nginx-running.png)
![Custom Page Saved](screenshots/13-custom-page-saved.png)


## Phase 5 — Open Website
🔄 Not started yet

## Phase 6 — Cleanup
🔄 Not started yet 
