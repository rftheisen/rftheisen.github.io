# Exploring Drone Technology & Cybersecurity
## Hardware Explanation 

![TelloDroneImage](telloblueprint.png)

CPU: Intel 14 Core Processor
- This is the brains of the system and where the real magic happens.

5 Megapixel camera 
- Allowing for high quality images and videos
- 4 tiny propellors 
4 propellers guards 
- Crashing is inevitable! 
- battery charger port connected with micro usb
- x1 battery 
- Has WiFi enabled NIC with SSID Broadcast no security enabled



## Software & Networking Exploration
- Runs DHCP server that leases out 192.168.10.0/24 network
- [Fantastic demonstration of connecting to Tello Drone](https://www.youtube.com/watch?v=kcXN7CYgQ0g)
- The [DJI-SDK/Tello-python repo](https://github.com/dji-sdk/Tello-Python) is hosted on GitHub and has many nifty python kits to learn programming in a comprehensive way
- [NMAP](https://nmap.org/) scan shows: Running Abyss webserver port: 9999 
Requirements: 
- Computer Hardware  (Laptop, Desktop or Raspberry Pi) (tested with windows)
- WiFi 
- python
- 
 - This to a .py file that is a UDP client that should allow us to send commands to the drone

- Need to learn how to control drone with a graphical interface. Also need a way to connect to camera.
- 
