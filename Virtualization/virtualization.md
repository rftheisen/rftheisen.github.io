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

