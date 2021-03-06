# Exploring Drone Technology & Cybersecurity
## Hardware Explanation 

![TelloDroneImage](telloblueprint.png)

CPU: Intel 14 Core Processor
- This is the brains of the system and where the real magic happens.

5 Megapixel camera 
- Allowing for high quality images and videos - 4 tiny propellors 
- 4 propeller guards 
    - Crashing is inevitable! 
- 1 battery charger port connected with micro usb
- 1 1.1Ah/2.8 volt battery 
- Maybe one day Tesla will make a battery that can fit this and last longer in flight
- Has WiFi enabled NIC with SSID Broadcast no security enabled out-of-box.
![SSID](TelloSSID.png)



## Software & Networking Exploration
The Tello Drone runs a DHCP server that leases out IP addresses on the 192.168.10.0/24 network. 

Checking my ip address and sending a ping icmp echo-request message to my drone
![DroneNetworking](dronenetworking.gif)

- [Fantastic demonstration of connecting to Tello Drone](https://www.youtube.com/watch?v=kcXN7CYgQ0g)
- The [DJI-SDK/Tello-python repo](https://github.com/dji-sdk/Tello-Python) is hosted on GitHub and has many nifty python kits to learn programming in a comprehensive way
- [NMAP](https://nmap.org/) scan shows: 
Running Abyss webserver port: 9999 
![Scanning drone with NMAP](nmapscan.gif)

 
I was successful in connecting to the drone utilizing the [Drooone Windows app](https://www.microsoft.com/en-us/p/drooone/9n0z6wvt0w6n?activetab=pivot:regionofsystemrequirementstab) developed by Symmetry Soft. This allows us to pilot the drone from our Windows system. See below for a quick view of how this works. 
  

![ConnectingtoDroneThroughDrooone](connectionsuccess.gif)

When I first started experimenting with Drooone the application kept displaying an error message when I attempted to connect to the Tello SSID (wireless network name). After some troubleshooting I discovered that it was the Windows firewall denying the connection from the OS to the drone. Deactivating the firewall allowed it to work, following this I allowed UDP ports: 10001 & 10002 through the firewall. Leaving the entire Firewall turned off is not a best practice & can put your computer at risk. This is why you must learn what exactly is being blocked and allow that specific application or logical port through the firewall.