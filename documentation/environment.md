#Environment

##Current user
Current user is the active account that has access to run commands, shell session or process on the terminal window.
-whoami 
-id -un
-echo $USER
![Current user](screenshots/Part_A_know_Your_Machine_Current_User_[1].png) 
##Hostname
Hostname is a label given to a server so that it can be identified on the network without using its IP address.
-hostname
-uname -a
-uname -n
-cat /etc/hostname
![hostname](screenshots/Part_A_know_Your_Machine_Hostname_[2].png)
##Operating system
Operating system is the main software that controls the hardware server that involves handling network services and managing applications such databases and web servers.
-cat /etc/os-release
-hostnamectl
![Operating System](screenshots/Part_A_know_Your_Machine_Operating_System_[3].png)
![Operating System](screenshots/Part_A_know_Your_Machine_Operating_System_[3][2])
##Kernel version
Kernel version is the exact number released to an operating system that is responsible for hardware resources, memory, process execution and device drivers on a server.
-uname -a
-uname -r
![kernerl version](Part_A_know_Your_Machine_Kernel_Version_[4].png)
![Kernel Version](
Part_A_know_Your_Machine_Kernel_Version_[4][2])
##IP / network information
IP/network information refers to interface settings, routing rules, hardware identifiers, and distinctive numerical addresses that are used by operating system to receive and send data over a network.  
-ip addr
-hostname -I
 ![Network Information](screenshots/Part_Your_Machine_IP_Network_Unfirmation_[5].png)
##Memory
Memory is a quick, short-term workspace (RAM) and virtual storage the operating system uses to run programs, cache files and handles data.
-free -h
![Memory](screenshots/Part_A_know_Your_Machine_Memory_[6].png)
##Disk space
Disk space is the available storage capacity on physical or virtual storage devices (such as Hard Disk Drives [HDDs], Solid State Drives [SSDs], or cloud volumes) to retain the operating system, logs, applications, user files, and databases. 
-df -h
![Disk Space](screenshopts/Part_A_know_Your_Machine_Disk_Space_[7].png)
##Running processes
A process is an activated, running instance of an application. It is usually activated by running command(s), starting a program or launching a background service.
-ps aux
![Running processes](screenshots/Part_A_know_Your_Machine_Running_Processes_[8].png)
![Running processes](screenshots/Part_A_know_Your_Machine_Running_Processes_[8][2].png)
##Running services
Running services are background processes, known as daemons (they often end in d, for example, httpd or sshd), they are running continuously without user interface to manage tasks or network demands.
-systemctl list-units –type=service –state=running
![Running Services](screenshots/Part_A_know_Your_Machine_Running_Services_[9].png)
##Listening network ports
Communication endpoints known as listening network ports are used by programs or services to wait for incoming data packets or network connections.
-sudo ss -tulpn
-sudo lsof -i -P -n | grep LISTEN
![Listening Network Ports](screenshots/Part_A_know_Your_Machine_Listening_Network_Ports_[10].png)
![Listening Network Ports](screenshots/Part_A_know_Your_Machine_Listening_Network_Ports_[10][2].png)
##ENGINEERING QUESTION
Why should an engineer inspect an unfamiliar server before making changes?
It is a way to prevent catastrophic downtime, remove security risks, and ensuring that rollback path is achievable. Moving into an undocumented or unfamiliar environment blindly may result in system failure. Inspection assists the cloud engineers to identify underlying issues and misconfigurations, such as pre-existing software misconfigurations, running diagnostics to check if the system is stable to undergo updates, helps detect unauthorized modifications, active security vulnerabilities and if a server has hardware flaws. 
