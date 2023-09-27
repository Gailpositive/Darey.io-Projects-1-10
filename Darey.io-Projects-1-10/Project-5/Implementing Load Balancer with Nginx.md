# INTRODUCTION TO LOAD BALANCING AND NGINX
# IMPLEMENTING LOAD BALANCERS WITH NGINX

## Pre-requites: I will be spinning three EC2 instances running ubuntu: Two for APACHE2 webservers and One for NGINX load balancer. My terminal of choice is Termius

# Step 1: 

* Spinning of Three instances
<img width="805" alt="three ec2 instances running" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/acf5e690-92a9-4d84-8c16-9f0f95427984">


# Step 2: Create security group and Editing inbound rules

* Apache2 Webserver 1 running on TCP port 8000
<img width="746" alt="both securities ported" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/33d14bbd-d762-484c-8120-c7d07aee57fe">

* Apache2 Webserver 2 running on TCP port 8000
<img width="745" alt="webserver 2 port 8000" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8ea025f3-f008-4f0e-b648-1c15c43d4b4f">

* Nginx Load balancer server on TCP port 80
<img width="759" alt="security port 80 load balancer" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/ee702148-9dd6-4f55-8f38-6a70b2a02cc4">


# Step 3 : SSH webserver and install apache2
* Apache2 Webserver 1: On my terminal, I ssh webserver 1 EC2 instance public Ip 
* Updating and installing apache 2 using the double ampersand operator
* I execute "sudo apt update -y && sudo systemctl install apache2 -y"
<img width="868" alt="apache install on webserver" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1402d756-9256-49e3-9776-1bc9b7bb6b5a">

* Apache2  Webserver 1: To comfirm Apache 2 is active and running,
* I execute the command "sudo systemctl status apache2
<img width="608" alt="updated apache2 active and running" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/838c4ff9-0633-4921-9434-08c3b878a124">


* Apache2 Webserver 2: On my terminal, I ssh webserver 2 EC2 instance public Ip 
* Updating and installing apache 2 using the double ampersand operator
* I execute "sudo apt update -y  && sudo systemctl install apache2 -y"
<img width="767" alt="apt update   apache2 install on webserver 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e91ffdb7-ddeb-4a73-a1d4-17352ed23e97">


* Apache2 Webserver 2: To comfirm Apache2 is active and running,
* I execute the command "sudo systemctl status apache2
<img width="607" alt="apache 2 running on server 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e6c9c31a-f370-4069-9f4a-016c3dc36e6b">


# Step 4 :I Config Apache2 to serve content on port 8000
* On Apache2 webserver 1, 
* I execute the following command on vi
* "sudo vi /etc/apache2/ports.conf"
* Then edit the block of codes by adding a new a listening "Listen 8000"
* <img width="623" alt="add a new listening 8000" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/5a915ff6-1353-42e8-bb02-e2f73a2d37c3">


* On Apache2 webserver 2, I Config Apache2 to serve content on port 8000
* I execute the following command on vi
* "sudo vi /etc/apache2/ports.conf"
* Then edit the block of codes by adding a new a listening "Listen 8000"
* <img width="683" alt="sudo config port 8000 on webserver 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/30a2fc3d-6927-48f5-8ac3-dc83d2198142">


* On Apache2 webserver 1, I  change port 80 to 8000 on virtualhost
* I open the file and execute the command "sudo vi /etc/apache2/sites-available/000-default.conf"
* <img width="830" alt="vi change to port 8000" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c62134c5-add9-4e25-a6b9-94adfd766ee5">
* Then execute the command "sudo systemctl restart apache2" to restart apache2



* On Apache2 webserver 2, I  change port 80 to 8000 on virtualhost
* I open the file and execute the command "sudo vi /etc/apache2/sites-available/000-default.conf"
* <img width="869" alt="sudo vi config 8000 on webserver 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/906b0809-7cbc-4060-9d33-9ea7497cd28f">
* And run the command "sudo systemctl restart apache2" to restart apache2

# Step 5: Create a new html file
* On Apache2 webserver 1,
* To open the html file 
* I switch to the vi editor of the file with the command "sudo vi index.html"
* Paste  some blocks of code
* Replace the paceholder text with webserver 1 public IP address
* <img width="496" alt="server 2 IP address" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/fcecaad9-a023-45d8-85c6-4e1f2ec4455c">


* On Apache2 webserver 2,
* To open the html file 
* I switch to the vi editor of the file with the command "sudo vi index.html"
* Paste  some blocks of code
* Replace the paceholder text with webserver 2 public IP address
<img width="565" alt="vi html file adding EC2 IP" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/09fc12df-2b17-4429-8c37-f092e05edc9d">


# step 6: Change file ownership of the index.html file
* On webserver 1, To change the file ownership, I execute the command: 'sudo chown www-data:www-data ./index.html"
* To override the default html file of apache2 webserver with the new html file,
* I execute the command "sudo cp -f ./index.html /var/www/html/index.html"
* I restart the webserver to load the new config with the command "sudo systemctl restart apache2"
* I enter the public IP address and the TCP port 8000 on my browser
* <img width="750" alt="web browser listening at port 8000" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/104cd282-58be-40ce-a133-85fb81f33591">
* Web browser is listening on port 8000


* On webserver 2, To change the file ownership, I execute the command: 'sudo chown www-data:www-data ./index.html"
* To override the default html file of apache2 webserver with the new html file,
* I execute the command "sudo cp -f ./index.html /var/www/html/index.html"
* I restart the webserver to load the new config with the command "sudo systemctl restart apache2"
* I enter the public IP address and the TCP port 8000 on my browser
* <img width="564" alt="2 webserver listnenin on port 8000" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d49a6bd5-57b4-4a33-8f36-042dcc50ec3f">
* Web browser is listening on port 8000



