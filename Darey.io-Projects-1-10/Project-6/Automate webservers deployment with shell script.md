# AUTOMATING LOAD BALANCER WITH SHELL SCRIPTING

## IN PROJECT 5, THREE BACK-END SERVERS WERE CONFIGURED AND DEPLOYED MANUALLY. IN THIS PROJECT, I WILL BE AUTOMATING THE DEPLOYMENT OF BACKEND-SERVERS.

## To get started, I will be configing and deploying three back-end servers on the  AWS EC2 Instance runnung ubuntu: Two loadbalancer server and one Nginx server, open on port 8000, 8000 and 80 respectively .


* I Connect to two separate apache2 load balancer webservers, via my termius terminal using SSH client
* With the "touch" command, I create two files: "config-apache1.sh" and "config-apache2.sh on the two separate terminals
* I sudo vi into both files with the command "sudo vi config-apache1.sh" and "sudo vi config-apache2.sh" on two saperate terminals
* To edit the top comment of the script, I call the first script and pass in its  EC2 instance IP address
*  Save and exit vi
*  To make the first script executable, I run the command "chmod u+x config-apach1.sh"
* I  execute the script with following command including the IP address, "./config-apache1.sh 16.171.241.41"
* <img width="873" alt="sudo vi apache1 updated" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b81b3410-bf7f-4fb5-aa25-37cea2ec964f">

* To edit the first comment of the script, I call the second script and pass in its  EC2 instance IP address
* Save and exit vi
* To make the second script executable, I run the command"chmod u+x config-apach2.sh"
* I execute the script with following command with its IP address, "./config-apache2.sh 16.171.234.100"
<img width="826" alt="sudo vi server 2 apache script" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/052bf10e-0d6f-475d-89f7-1cbea880397b">

