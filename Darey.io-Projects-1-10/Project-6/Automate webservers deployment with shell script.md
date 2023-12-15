# AUTOMATING LOAD BALANCER WITH SHELL SCRIPTING

## IN PROJECT 5, THREE BACK-END SERVERS WERE CONFIGURED AND DEPLOYED MANUALLY. IN THIS PROJECT, I WILL BE AUTOMATING THE DEPLOYMENT OF BACKEND-SERVERS.

## To get started, I will be configing and deploying three back-end servers on the  AWS EC2 Instance running ubuntu: Two loadbalancer servers and one Nginx server, open on port 8000, 8000 and 80 respectively .

<img width="673" alt="3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/55b01625-6690-482d-9c57-79fd4ee68668">


# Step 1: Configure Apache2 As A Loadbalancer
* I Connect to two separate apache2 load balancer webservers, via my termius terminal using SSH client
* With the "touch" command, I create two files: "config-apache1.sh" and "config-apache2.sh on the two separate terminals
* I sudo vi into both files with the command "sudo vi config-apache1.sh" and "sudo vi config-apache2.sh" on two saperate terminals
* To pass the first argument of the script, I call the first script and pass in its  EC2 instance IP address
*  Save and exit vi
*  To make the first script executable, I run the command "chmod u+x config-apach1.sh"
* I  execute the script with following command including the IP address, "./config-apache1.sh 16.171.241.41"
* <img width="873" alt="sudo vi apache1 updated" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b81b3410-bf7f-4fb5-aa25-37cea2ec964f">

# Step 2
* On my web browser, I enter the IP address and port 8000 is listening
<img width="586" alt="web browser server 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/bb47478e-576b-4939-9ee0-d24f603c2f98">

# Step 3
* To pass the first argument of the script, I call the second script and pass in its  EC2 instance IP address
* Save and exit vi
* To make the second script executable, I run the command"chmod u+x config-apach2.sh"
* I execute the script with following command with its IP address, "./config-apache2.sh 16.171.234.100"
<img width="826" alt="sudo vi server 2 apache script" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/052bf10e-0d6f-475d-89f7-1cbea880397b">

# Step 4
*On my web browser, I enter the IP address and port 8000 is listening
* <img width="572" alt="web browser server 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/4827e7bb-b25e-4365-9b46-872d474cf358">


# Step 5
## "DEPLOYING AND CONFIGING NGINX LOAD BALANCER"

* I Connect to the Nginx webserver , via my termius terminal using SSH client
* With the "touch" command, I create a file: "config-nginx.sh"
* I sudo vi into the file with the command "sudo vi config-nginx.sh" 
* To pass the first argument of the script, I call both the two apache2 load balancer scripts ,pass both EC2 instance IP addresses and both ports security groups 
*  Save and exit vi
*  To make the first script executable, I run the command "chmod u+x config-nginx.sh"
* I  execute nginx script and the three IP addresses with following command, "./config-nginx.sh" 16.16.183.106  16.171.241.41 16.171.234.100
* <img width="844" alt="sudo vi nginx codes" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e157343a-43bb-4ccf-bd7f-eccdee715163">

* Nginx server is active and enabled
<img width="898" alt="nginx server active and running" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9c486040-0ba9-4d9b-bd73-880f6b434fbb">

* Syntax is successful
<img width="557" alt="nginx sytax is ok,this is will come after system active and running" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/cdb766bb-0df4-4b33-b525-50a7428cde62">

# Step 6

<img width="708" alt="4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/5a68e74f-b577-44fa-b9eb-94cc4329010a">

<img width="713" alt="5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8d906d00-39e8-4c79-b5d3-632f373339fc">

<img width="750" alt="6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e98fe686-d886-455a-a45f-dc80345d349f">
