# Automate all the things 

Automation as a philosophy and approach to work is in full effect in our society. Lets just consider what Andressen Horrowitz wrote in his essay titled "Software is eating the world.". We can look at the world now and see that software indeed has eaten the world. Remember when we used to walk into a store that existed soley for the purpose of borrowing movies and video games. Well now all of this has been virtualized and automated. All we have to do is pay a small monthly fee for access to unlimited libraries of movies, shows, video games and music. Oh and those sites you use have incredible algortithms running to power custom tailored recommendations to help you as you explore this vast Internet we spend so much time on. Speaking of the Internet, Google automated the process of searching for websites and content on the web. In a way you could say they automated the process of finding what you want on the World Wide Web, they continue to dominate in the search engine business and I get the sneaky suspicion that they always will. Perhaps this ease of usability Google added to the Internet drove the wide spread adoption of the Internet as one of the most important inventions in human history. 

Soon we will be calling our cars to come pick us up using AI powered Digital Assistants. The command we issue will travel over high-speed networks to the car which will be driven to us by algortithms in the same way a pilot works alongside algorithms to fly a air-plane thousands of feet in the skies. Consider the work Tesla is doing as they continue to position their vehicle product line to receive updates over the Internet which will eventually lead to a rolling computer that can drive entirely on it's own. While I don't own a Tesla myself I've driven one and witnessed it's capabilities first hand. They are a glimpse of the future of autonomous systems, not just cars. Tesla's mission to accelerate the world's transition to sustainable energy is powered by automated systems working together in a beautiful symphony of orchestrated computer systems. 

Even the field of IT is continously interating towards automated systems to free up IT operations teams (Network & System admins, SOC analysts, Software developers, the list goes on...) to move organizations forward. I personally believe it is part of who we are to automate processes so we can do more. Some important books in human history declare that we are to be fruitful and multiple. We can examine reality and make a strong case that this is what tech moguls like Jeff Bezos and Elon Musk are doing as they break the mold in all they do. It's almost as if they have found an algorith in life that works at least as it relates to the economy and generating financial wealth. Speaking of Jeff Bezos, did you know his company Amazon has an IT Automation engine called AWS. Some shoot me strange looks when I say that AWS is IT automation, think about it for a bit. Here is this platform anyone can use to install, configure, manage and automate countless IT systems (client OSs, server OSs and entire network infrastructures) from anywhere in the world. This is including but not limited to being in your pajamas at home. 


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
