# LEMP-STACK IMPLEMENTATION IN AWS.

## (Linux OS, Nginx Webserver, Mysql Database, PHP Language Script)
 ## Preparing Prerequisites: In order to complete this project, I will be spinning up an AWS EC2 instance and a virtual server with ubuntu server operating system. My preferred choice terminal is Termius.

    "AWS EC2 instance is active and running"
<img width="950" alt="ec2 instance" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/2eb423a1-a523-4377-9c66-391fcc3d95bf">

    "My Termuis terminal was hosted and launched on my AWS EC2 instance using my public IP address, and the key was configured with my private IP"
<img width="838" alt="termuis" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/5d27a6fd-1f3a-4d57-b771-a29990674c85">


   ## INSTALLING THE NGINX WEBSERVER.
   
      "To start up, I'll first update my server package index, using the " sudo apt update" command"   
   <img width="956" alt="sudo apt update my termuis terminal" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/1e714a8a-a9cc-4607-a90e-b251459cf10f">

   "I run Sudo apt install nginx" command to install nginx web-server"
<img width="954" alt="sudo apt install nginx" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/3af6852e-9852-4f09-80ee-ca7bc4fdc0dd">

   "I executed sudo systemctl status nginx" command to verify nginx webserver is active and running as a service on my ubuntu virtual machine"
<img width="955" alt="sudo systemctl status nginx" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/10707749-a36a-4a03-90d3-4c19bdd95a91">

   "Adding a rule on AWS EC2 configuration, to allow inbound access through the default port 80 TCP"
<img width="903" alt="port 80" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/efaacb7d-5b9e-4926-9892-52e94af959c3">

 "Requesting nginx server either through the domain name server (DNS) with the command "curl http://localhost:80 on my browser"
<img width="908" alt="localhost 80" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/7b7ac50d-3256-4572-abcc-b5e781508660">

 "Or through the IP address with the command "curl http://my public Ip address" on my browser"
<img width="896" alt="curl localhost through the IP Address" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/ddf6b4a1-f56d-4848-83f0-af6c5f0027a1">

 "Testing Nginx server response to request on the browser via the IP address, I executed the command "curl http://public Ip address" and yes, nginx is successfully installed and accessible through my firewall"
<img width="952" alt="nginx webserver up and running on the web" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/20c25292-327f-431c-ad73-456c6104af2a">
