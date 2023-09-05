# LEMP-STACK IMPLEMENTATION IN AWS.

## (Linux OS, Nginx Webserver, Mysql Database, PHP Language Script)

 ## Prerequisites: In order to complete this project, I will be spinning up an AWS EC2 instance and a virtual server with ubuntu server operating system. My preferred choice terminal is Termius.

    "AWS EC2 instance is active and running"
<img width="950" alt="ec2 instance" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/2eb423a1-a523-4377-9c66-391fcc3d95bf">

    "My Termuis terminal was hosted and launched on my AWS EC2 instance using my public IP address, and the key was configured with my private IP"
<img width="838" alt="termuis" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/5d27a6fd-1f3a-4d57-b771-a29990674c85">


   ## Step 1: INSTALLING THE NGINX WEBSERVER.
   
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


## Step 2: INSTALLING MYSQL DATABASE

"Running the command  "sudo apt install mysql-server" to install mysql database management system"
<img width="909" alt="sudo apt install mysql-server" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/f02ee3aa-c205-46ac-b5a3-8349a62a35a1">

  "Logged into mysql console via the "sudo mysql command"
<img width="810" alt="sudo mysql" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/c977a814-dd5c-41f1-bc47-5cec683448a6">


"Before running the pre-installed MYSQL security script, which is designed to eliminate any insecure default settings and secure access to my database system, I will first set a root user password and afterwards, Exiting the console"
<img width="793" alt="security script and exit" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/a581bfa7-5f50-4e42-b551-1a4137a69753">

  "To initiate the interactive script, I executed the "sudo mysql_secure_installation" command , which requested validation of the password plugin"

<img width="944" alt="secure password plugging 1" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/a49dfe7a-47a5-451b-8380-339594272782">

 "A continuation and finished process of the interactive script"
<img width="946" alt="secure password pluggings 2" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/48eb67ed-ca6d-4e68-b573-7b1e8b7632fc">

"To logged into my MYSQL console as a root user with the command "sudo mysql -p" , enter my password and exited the console".

<img width="470" alt="sudo mysql -p" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/46675b97-5991-42fb-99fd-c4e3ed0a7ae5">


## Step 3: Installing PHP process codes.

## "Nginx differs from Apache in how it handles PHP. Nginx requires the setup of an external program called "php-fpm" to be able to process PHP processor , which enhances it performance. While PHP on the other hand, also requires the installation of a program called  "php-mysql" to establish communicate with MySQL databases. These core PHP packages installed automatically as dependencies  with the command "sudo apt install php-fpm php-mysql"

<img width="954" alt="installing php" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/70828d21-5632-437c-b605-ad385b2ffbf2">


## Step 4: Configuring Nginx to use PHP processor.

 ## Nginx can use server blocks (similar to Apache's virtual hosts) to manage multiple domains on a single server. Ubuntu 20.04's default Nginx setup serves content from /var/www/html, but for multiple sites. I  created a separate directory structure within /var/www/ for each site, leaving /var/www/html as the default for unmatched requests.

* "First, I run the "sudo mkdir /var/www/mydomainname" to create a root web directory for my domain name".
*  "Next, I run the command " sudo chown -R $USER:$USER /var/www/mydomainname" to allocate ownership of the directory using $USER environment variable, which points to my present system user. (Image was lost)"
* "Created a new configuration file within the nginx directory with the nano editor and pasted the bare bone configuration in the image below"
* I enabled my configuration by linking to the config file from nginx sites enable directory using the command "sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/".
* "Tested my systax for system error with the command "sudo nginx -t", systax is ok."
*  "I disabled default nginx host currently configured to listen to port 80 with the command "sudo unlink /etc/nginx/sites-enabled/default"
*  "Reloaded nginx again to apply the changes made with the command "sudo systemctl reload nginx"
   
<img width="959" alt="config nginx updated" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/31714eb8-0ab5-464b-bc6f-7856f8628102">

"Bare-bone configuration in nano editor"
<img width="954" alt="nano mydomainname" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/3894505a-5fc8-47fc-9b0d-5c58337f5264">


  "My new website is up and running, but the web root directory at /var/www/mydomainname remains devoid of content. To address this, I generated an index.html file at that location with the command "sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/mydomainname/index.html, allowing me to verify the functionality of my new server block.
* I enter the command "http://<Public-IP-Address>" to access my website on a browser"
* My lemp stack is now fully configured!
   
<img width="917" alt="lemp activated on browser" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/219ba1a1-9266-4e66-9a2a-b00db751a397">


## Step 5: Testing PHP with Nginx.

## "To validate that nginx can correctly handle .php file off to my php processor, I created a test php file within my document root in my nano editor with the command "nano /var/www/mydomainname/info.php" 
* And pasted a valid php code to return infomation about my server:
  "<?php
  phpinfo();"
<img width="938" alt="valid php code" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/74609c23-a527-4fc1-84be-e84c57bac653">


"My PHP file with detailed infomation about my server is now accessible on the web browser through this code "http://`my public IP address`/info.php"

<img width="920" alt="php page on browser" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/783f45b3-352f-4707-aa52-a241eb2f3bb2">


"After checking relevant info about my php page, I deleted the php page from the web for security reasons using the command "sudo rm /var/www/mydomainname/info.php"
*  It can alway be access whenever require"

<img width="893" alt="nginx removed" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/23bb553b-4765-4eca-8f36-2261401e2409">


## Step 6: Retrieving data from MYSQL database with PHP
 
## I'll set up a test database containing a single "To-do list" and configure access to it, enabling the nginx website to retrieve data from the database and present it.

* "First,I login to mysql console as a root user, with the command "sudo mysql -p".
* "Created a database user with a password with the command "CREATE USER 'gail_user'@'%' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';"
* " Granted the user permission over the database just created with the command "mysql> GRANT ALL ON example_database.* TO 'example_user'@'%';"
* Exited mysql console

<img width="827" alt="retrieving data from mysql database in php" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/2d774955-f468-4480-9737-cb763d9587d1">


* "Testing to verify successful permission of the new user, I logged in to mysql console as a the new user  with this command "mysql -u example_user -p"
* I access the database with the command "SHOW DATABASES;"
  * Next, I created a "Todo_list"  with the statement "CREATE TABLE gail_database.todo_list (item_id INT AUTO_INCREMENT,content VARCHAR(255),PRIMARY KEY(item_id));"
  * I inserted a few rows of content in the test table with the command INSERT INTO gail_database.todo_list (content) VALUES ("My first important item"), "(household items)" ect as seen in the below database table .
 * To verify the data was successfuly saved, I run the command "SELECT * FROM gail_database.todo_list;"
  * "And got the following output"

<img width="956" alt="create my database and create database to do list and exit" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/edf9cf38-4e1f-41cd-b2f9-aebf40f0bc64">
* Upon validating my data in the table"
*I exited mysql console with the exit command"

## "Now, its time to create a PHP script that connects to mysql and querry my content. 
* To create this script, I create a PHP file in my root directory using the nana editor" usint the code "nano /var/www/mydomainname/todo_list.php
* And deleted the todo_list.PHP file from the web browser afterwards for security reasons"

<img width="779" alt="nano into info php   sudo rm from web browser" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/15aa568e-4f05-43e1-81b2-e1d08cc19230">

* "And paste the below script into my todo_list.php on my nano editor"
*  "Save and close nano editor"

  <img width="882" alt="vi php scripts connecting to mysql database 2" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/8e295261-4ac3-4e38-b55c-cf94772d70ab">


* To access my todo_list.php on my browser, I executed the command "http://my Public IP/todo_list.php"

   <img width="596" alt="access my todo list php on web browser" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/6865627d-50e8-4722-8ae5-843a26d2848c">


