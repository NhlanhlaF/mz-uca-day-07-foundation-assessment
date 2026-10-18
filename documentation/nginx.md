#DEPLOY NGINX
##Is Nginx installed?
Install nginx uses the following commands:
-sudo apt update 
-sudo apt install nginx -y
![Install nginx](screenshots/Part_D_Deploy_Nginx_Install_Nginx_[1].png) 
##Is Nginx running?
Nginx service is checked by the command: sudo systemctl status nginx. The output should indictate active(running) to confirm that Nginx is running.
![Nginx Running](screenshots/Part_D_Deploy_Nginx_Nginx_Running_[2].png)
##Is Nginx enabled?
Nginx is enable by the commands:
-sudo systemctl start nginx
-sudo systemctl enable nginx
![Enable Nginx](screenshots/Part_D_Deploy_Nginx_Nginx_Enabled_[3].png)
##Where are its configuration files?
To determine the path of the configuration files the following command is used:
-nginx -t
![Configursation Files](screenshots/Part_D_Deploy_Nginx_Configuration_Files_[4].png)
##Where is the web content located?
To identify the web content the following command is used:
-sudo grep -R “root” /etc/nginx/
![Web Content](screenshots/Part_D_Deploy_Nginx_Web_Content_[5].png)
##Which port is Nginx listening on?
To identify which ports nginx is listening on, you use the following commands:
-sudo ss -tulpn | grep nginx
-sudo lsof -I -P -n | grep nginx 
Nginx is listening on TCP port 80.
![Listening Ports](screenshots/Part_D_Deploy_Nginx_Nginx_Listening_Ports_[6].png)
##How can you verify that Nginx is responding?
The following commands are used to verify that Nginx is responding:
-curl localhost 
-curl -I http://localhost
-sudo systemctl status nginx 
The output should demonstrate custom web page and the status should indicate whether the nginx is active(running) or inactive(dead).
![Listening Ports](screenshots/Part_D_Deploy_Nginx_Verify_Nginx_[6][1].png)
![Listening Ports](screenshots/Part_D_Deploy_Nginx_Verify_Nginx_[6][2].png)
##QUESTION 01
What is the difference between installed and running?
###Installed
The Nginx software is downloaded and registered on the operating system’s hard drive. The server can use Nginx but it is not active to use the system’s RAM and CPU yet. In some instances, it might automatically start and enable itself on boot or might wait on the disk to be activated. 
###Running
The Nginx processes are actively loaded into computer’s memory (RAM), the running nginx actively listens on port 80 or 443 which accepts incoming web traffic, processes requests and serves web pages or proxies connections. The nginx is actively listening for requests. 
##QUESTION 02
What is the difference between running and enabled?
###Running 
When the Nginx service is active (running) it is able to process web requests in real time. Users are able to load websites successfully. To activate the system, the following command is run sudo systemctl start nginx.
###Enabled
When the operating system reboots or is powered on, the Nginx service is configured to start automatically. Command such as sudo systemctl enable nginx is used to enable the nginx service. 
##QUESTION 03
Why might a service work today but fail to start after a server reboot?
The service might try to connect to the server before the system’s network interface assigns IP addresses.
The service might try accessing server before the DNS service is active and running, therefore, the service will fail.
When two services are attempting to access the same port, it will result in failure. For example, Apache is configured to access port 80 at the boot before the Nginx service, when the Nginx  Do not copy definitions. Explain them in your own words.
