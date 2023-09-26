# INTRODUCTION TO LOAD BALANCING AND NGINX
# IMPLEMENTING LOAD BALANCERS WITH NGINX

## Pre-requites: I will be spinning three EC2 instances running ubuntu: Two for webservers and One for NGINX load balancer. My terminal of choice is Termius

# Step 1

* Spinning of Three instances
<img width="805" alt="three ec2 instances running" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/acf5e690-92a9-4d84-8c16-9f0f95427984">


* Webserver 1 on TCP port 8000
<img width="746" alt="both securities ported" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/33d14bbd-d762-484c-8120-c7d07aee57fe">

* Webserver 2 running on TCP port 8000
<img width="745" alt="webserver 2 port 8000" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8ea025f3-f008-4f0e-b648-1c15c43d4b4f">

* Nginx Load balancer server on TCP port 80
<img width="759" alt="security port 80 load balancer" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/ee702148-9dd6-4f55-8f38-6a70b2a02cc4">


* Webserver 1: On my terminal, I ssh webserver 1 EC2 instance public Ip 
* Updating and installing apache 2 using the double ampersand operator
* I execute "sudo apt update -y && sudo systemctl install apache2 -y"
<img width="868" alt="apache install on webserver" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1402d756-9256-49e3-9776-1bc9b7bb6b5a">

* Webserver 1: To comfirm Apache 2 is active and running,
* I execute the command "sudo systemctl status apache2
<img width="608" alt="updated apache2 active and running" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/838c4ff9-0633-4921-9434-08c3b878a124">


* Webserver 2: On my terminal, I ssh webserver 2 EC2 instance public Ip 
* Updating and installing apache 2 using the double ampersand operator
* I execute "sudo apt update -y  && sudo systemctl install apache2 -y"
<img width="767" alt="apt update   apache2 install on webserver 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e91ffdb7-ddeb-4a73-a1d4-17352ed23e97">


* Webserver 2: To comfirm Apache 2 is active and running,
* I execute the command "sudo systemctl status apache2
<img width="607" alt="apache 2 running on server 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e6c9c31a-f370-4069-9f4a-016c3dc36e6b">
