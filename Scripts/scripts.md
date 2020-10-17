# Automation all the things 

Automation as a philosophy and approach to work is in full effect in our society period. Lets just consider what Andressen Horrowitz wrote in his essay titled "Software is eating the world.". We can look at the world now and see that software indeed has eaten the world. Remember when we used to walk into a store that existed soley for so that we could borrow movies and video games. Well now all of this has been virtualized and automated. All we have to do is pay a small percentage a month for access to unlimited libraries of movies, shows and video games. 


# Cisco IOS Device Base Line Configurations

## Router Configurations

``` 
    en
    conf t
    hostname R1
    enable secret Cisco
    service password-encryption
    banner motd $ Unauthorized access is strictly prohibited. $
    line con 0 
    logg sync
    login local
    exec-timeout 60
    line vty 0 15
    logg sync 
    login local 
    transport input ssh 
    transport output ssh
    exit 
    ip domain-name Bob.net
    username Bob password Cisco
    crypto key generate rsa 
    2048
    ip ssh version 2
    int g0/0.10
    description Link to Administration
    encap dot1q 10 
    ip add 192.168.10.1 255.255.255.0
    no shut
    int g0/0.20
    description Link to IT VLAN
    encap dot1q 20 
    ip add 192.168.20.1 255.255.255.0
    no shut
    int g0/0.30
    description Link to HR VLAN
    encap dot1q 30 
    ip add 192.168.30.1 255.255.255.0
    no shut
    int g0/0.40
    description Link to ENG VLAN
    encap dot1q 40 
    ip add 192.168.40.1 255.255.255.0
    no shut
    int g0/0
    no shut
    int g0/1
    description Link to Building A
    ip add 10.0.0.1 255.255.255.252
    no shut
    int g0/2 
    description Link to ISP
    ip add 200.0.0.1 255.255.255.252
    no shut
    exit
    ip dhcp excluded-address 192.168.10.1 192.168.10.20
    ip dhcp excluded-address 192.168.20.1 192.168.20.20
    ip dhcp excluded-address 192.168.30.1 192.168.30.20
    ip dhcp excluded-address 192.168.40.1 192.168.40.20
    ip dhcp pool Admin
    network 192.168.10.0 255.255.255.0
    default-router 192.168.10.1
    dns-server 1.1.1.1
    ip dhcp pool IT
    network 192.168.20.0 255.255.255.0
    default-router 192.168.20.1
    dns-server 1.1.1.1
    ip dhcp pool HR
    network 192.168.30.0 255.255.255.0
    default-router 192.168.30.1
    dns-server 1.1.1.1
    ip dhcp pool ENG
    network 192.168.40.0 255.255.255.0
    default-router 192.168.40.1
    dns-server 1.1.1.1
```
## Switch Configurations
``` 
    en    
    conf t
    hostname S1
    enable secret Cisco
    service password-encryption
    banner motd $ Unauthorized access is strictly prohibited. $
    line con 0 
    logg sync
    login local
    exec-timeout 60
    line vty 0 15
    logg sync 
    login local 
    transport input ssh 
    transport output ssh
    exit 
    ip domain-name Bob.net
    username Bob password Cisco
    crypto key generate rsa 
    2048
    ip ssh version 2
    vlan 10 
    name Admin
    vlan 20
    name IT 
    no shut
    vlan 30 
    name HR
    vlan 40 
    name ENG
    exit
    int vlan 20 
    ip add 192.168.20.2 255.255.255.0
    no shut 
```
