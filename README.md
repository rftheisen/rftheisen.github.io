# Welcome to Love Thy Neighbor

Welcome to my ever changing website! You'll find that this site is built for learning, exploration and empowerment. You should find something here that will do all three for you. I'm Bob, the author of this site and I am called to empower others through innovative educational experiences. I believe that we are not talking enough about the quality of education. Seeking an education can be one of the most empowering things. It can lift you into realms you never dreamed of. Whether you are seeking informal educational pathways or enrolled in college you should demand a quality experience. The journey towards a credential should be full of enriching experiences. In technology the experiences should lead to relevant & highly sought after skills and unique opportunities. Too many colleges are teaching out-of-date curriculum. This is unacceptable for the cost to be so high, at least thats the case here in the USA. My calling is to change this by partnering with institutions and individuals to address the skills gap im tech.  The fact that you are here is an indicator that you are interested in learning more about Cybersecurity, Networking and or Systems administration. Perhaps even, my Twitch show Hack&Secure, YouTube channel, Linkedin or one of my friends steered you in this direction. I believe it could've been something deeper that lead you here. Are you ready to get started? Start below by clicking a link that interests you:  


[My teaching philosophy](https://rftheisen.github.io/teaching-philosophy/philosophy)
[Build a home lab and enter boundless learning territory](https://rftheisen.github.io/HomeLab/homelabs)


# Learning Goals for the rest of 2020
    1. Pass CEH by May 15th *Scheduled* 
    2. Pass OSCP by August 20th 
    3. Finish Cisco CCNA video series on YouTube by July 1st 
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

