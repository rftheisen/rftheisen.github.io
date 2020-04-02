# LTN_Bob

# Learning Goals for the rest of 2020
    1. Pass CEH by May 15th *Scheduled* 
    2. Pass OSCP by August 20th 
    3. Finish Cisco CCNA video series on YouTube by June 1st 
    4. Pass CCNP Enterprise Core by December 11th 
    5. Obtain my BSIT Degree by the end of Fall semester 



# Goal Accomplishment Strategy 
    1. Doing HacktheBox, Tryhackme challenges, reading Mike Walkers book, and completing Practical Ethical Hacking Course 
    2. Find funding to purchase, go through training course on Offensive Security's site, practice bash and powershell skills,
        and use platforms from first goal.
    3. Schedule time in the week to work on recording the content
    4. Complete CBTNuggets course, Read Cisco Press CCNP book, and setup GNS3 lab in VMware esxi and upgrade server memory
    5. Take summer courses and keep doing well in class

# Accomplished:

-  Build hyperconverged home lab by March 20th 
-  Build remote access lab functionality for classes by March 20th



# Breaking into Starting Point

## Trying to break into Traceback on HacktheBox

Learning Objectives: 

1. Using OpenVPN in Kali to connect to a remote network 
- Must have a vpn profile configuration file. This can be downloaded from the Hackthebox site once you have an account
- Must run sudo openvpn "config file name" from within the directory the file is in

2. Getting familiar interface,tools and methodology
- practice with nmap from the command line
- learn how to use Burp suite
- Metasploit has various modules that allow you to exploit different threat vectors
    - Requires parameters to be set in order to launch an attack module. Some parameters include: 
    * Set RHost equal to the target device 
    * Set USRPASSWORD file equal to password files to allow metasploit to guess 
    * Set Verbose 
    * May want to try this recon framework: https://github.com/r3p3r/fsociety
    * Heres how to setup: https://www.youtube.com/watch?v=t3uYpMrK2EU
- Use searchsploit to find vulnerable and unpatched programs
- Reference https://osintframework.com/ as you think through the attack and defend process

3. Get proficient at using VMware Esxi interface to create and use VMs 

4. Develop a solid Scanning & Enumeration methodology 
- look into evil-win rm 
- look into mount.cifs 
- Impacket must be installed using pip because it is written in python 
- Must be in the impacket directory to run mssqlclient.py module 
- Must have python-pip to install impacket and use the modules
- Stuck at reverse shell step 
    - Should this be left on the Windows box or Kali, how come the command isn't working in Powershell
- Look into smbmap
- the pip install got interuppted because I switched from wireless nic to physical nic in the middle of installing pip so we needed to fix using 
- Started using tmux to eliminate distractions and increase productivity 
- We started a python web server and included a powershell script to get a reverse shell from Windows box to Kali system 
- We used psexec to establish a persistent shell and get local admin rights
- Used type command from within windows cmd to view the contents of the txt file


# Breaking into lame 
Network: Starting Point 
IP address: 10.10.10.3

Nmap skills: 


# Breaking into Traceback

Still Trying to break into Traceback 
Learning Objectives: 

Same as March 21st 

Host info 
* IP add 10.10.10.181 
* Operating Sytem Ubuntu 
* Ports open SSH (22) & HTTP (80)
* Running Apache 2.4.29

- Entered Smevk.php in directory path of url for on the web server which allowed me to reach a web admin portal with admin admin 
as the credentials

- Metaspoit is an attack framework that has some great attack tools and modules based on threat vector 
Here are the commands for an ssh bruteforce module: 

``` Setting parameters in Metasploit for the ssh_login auxilliary module 
search ssh 
use auxillary/scanner/ssh/ssh_login
show options 
set RHOSTS *ip address*
set PASS_FILE *directory to passwords list*
set USER_FILE *full path to file with users list*
run 
sessions -i "pick session number" 
```

# Network Virtualization with GNS3 

## Setup process in VMware esxi: 
- Used: https://docs.gns3.com/1hEoK0rmtdBRnMaUaVoMHUbYwtDAltXYShiMJUp1GMxk/index.html
- Memory accolation recommendations: https://www.rogerperkin.co.uk/ccie/ccie-virtual-rack-csr-1000v-routers/
- Generally you are going to need more memory as your environments grow in complexity

- Building our own Hackthebox type infrastructure for Pentest practice and improving Network/Sys Admin skills 
- History of virutalzation: https://www.networkworld.com/article/2254433/with-long-history-of-virtualization-behind-it--ibm-looks-to-the-future.html

## Setting up and testing Ubuntu Client in GNS3 with nested virtualization: 

- Must upload a VMDK file from client to server when creating the appliance 
    https://www.osboxes.org/ubuntu/#ubuntu-19-04-vmware
- Then you must specify the ISO that is going to be used to book the VM into Ubuntu
- GNS3 has tightvnc integrated for graphical terminal access to the OS
- When using ssh to connect to the router Ubuntu returns an error that indicates an older cipher suite is being used on the router, this prevents successful connection
- Trying telnet worked, we will comeback to the ssh
    https://www.openssh.com/legacy.html
- dsqst found that we needed to use a less secure cipther to connect via Ubuntu so we used this command: 

    ``` ssh -c aes128-cbc ltn@192.168.0.1 ```
- In the industry it would recommended that we upgrade the IOS image on the device to an images with up to date ciphers and methods with SSH 

