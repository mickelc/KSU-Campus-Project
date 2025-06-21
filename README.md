# Campus Network Simulation
This project is a Cisco Packet Tracer lab that simulates a multi-site campus network (similar to my alma mater) with a Main Campus, a Branch Campus, and a Cloud Network. It includes VLAN segmentation, inter-VLAN routing, DHCP services, RIP version 2 for routing between campuses, and connectivity tests across departments and locations.

# Network Topology
![image](https://github.com/user-attachments/assets/376f1e3e-003a-417b-b270-17e7c125cdc1)

* The Main Campus connects to 8 Layer 2 department switches via a Layer 3 switch, which links to the Main Campus Router.

* The Branch Campus connects 2 Layer 2 switches via a Layer 3 switch, which connects to the Branch Router.

* A Cloud Router is connected to an Email Server.

# Router Configuration
After setting up each department and connecting their devices to the appropriate switches, I accessed all three routers and brought their interfaces to the operational (up) state.

![image](https://github.com/user-attachments/assets/b3a3b46b-fe22-426c-aed4-1bca26df6a66)
![image](https://github.com/user-attachments/assets/0b36542e-18f7-4e02-96b8-de094a22c852)
![image](https://github.com/user-attachments/assets/836a46f5-9d3f-4b72-8d9b-1f124349f097)

# Switch Configuration
I configured all Layer 2 switches across both the main and branch campuses (access layer) by assigning the appropriate VLANs to each port based on departmental requirements.

### The following configuration was applied to the Human Resources Department. A similar setup was implemented for each of the other departments as well. 
![image](https://github.com/user-attachments/assets/c51cf244-f5be-482c-82bf-6f724b317903)

# Layer 3 Switch Configuration
Next was to move up the layer 3 swtiches on both branches (the distribution layer) and set each switch ports to access mode.

### Below was done on the main campus L3 switch. This process was repeated for each VLAN
![image](https://github.com/user-attachments/assets/17eb97fe-8407-4e72-8fdd-c7ca09561328)

# Subinterface Creation and VLAN Tagging
The configuration shown below was applied on the branch router to enable inter-VLAN communication between devices on VLAN 90 and VLAN 100. The same procedure was done on the main campus router to support communication across all eight VLANs.
![image](https://github.com/user-attachments/assets/a167951d-548a-4c1a-aa1a-92e6af32708b)

# DHCP Configuration
Configured DHCP services on both the branch and main campus routers to ensure all devices received their IPv4 addresses dynamically.

### Main Campus Router:
![image](https://github.com/user-attachments/assets/5cc04832-3e44-4d27-8f6d-a317e9fbb486)

### Branch Campus Router:
![image](https://github.com/user-attachments/assets/5a9e5e56-bff8-4c9d-940b-aee4e2a03430)

# Routing Configurations
To allow the router to dynamically share and learn routes, I used RIP v2 instead of relying on static routes. Below is the commands entered on all three routers

### Main Campus Router:
![image](https://github.com/user-attachments/assets/432382ac-eef7-478d-9777-0b288a56739b)

### Branch Campus Router:
![image](https://github.com/user-attachments/assets/e25391aa-b7d8-49e2-8476-d917440fd081)

### Cloud Router:
![image](https://github.com/user-attachments/assets/cb5c7839-0177-45cf-bda1-91c12ef9408b)

# Connectivity Tests
### Ping Tests Conducted:
Admin PC (Main Campus) to Student Lab PC (Branch Campus)
![image](https://github.com/user-attachments/assets/c20964c3-adfb-4907-98e2-7c913b42684b)

Staff PC (Branch Campus) to Business PC (Main Campus)
![image](https://github.com/user-attachments/assets/9f354895-088b-4b3a-b7cb-a543aef0cf49)

IT PC (Main Campus) to Email Server (Cloud Network)
![image](https://github.com/user-attachments/assets/62d98007-a2f4-41c5-a0e7-f2077870535a)

### All pings were successful, verifying end-to-end connectivity and proper configuration of inter-VLAN routing, DHCP, and RIPv2.

# Summary & Takeaways
### Through this project, I strengthened my skills in:

* Designing scalable campus-wide network architectures
* VLAN creation and trunking across complex multi-switch environments
* Configuring inter-VLAN routing on multiple routers
* Implementing DHCP services across VLANs
* Setting up RIP version 2 for multi-site routing
* Troubleshooting and verifying routing tables and device connectivity

See packet tracer file in repository for the Campus file
