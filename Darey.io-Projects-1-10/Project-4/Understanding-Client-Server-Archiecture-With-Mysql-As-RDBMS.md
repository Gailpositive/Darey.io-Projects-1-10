# UNDERSTANDING CLIENT SERVER ARCHITECTURE WITH MYSQL AS RDBMS. 

# Prerequisites: I spinned up two AWS EC2 instances. One as a client server and the other as a webserver, and loggin through the IP address on my termius terminal.


## Implementing A Client Server Architecture Usng Mysql Database Mnagement System (DBMS)

* First, I spinned up and configure two-Linux based virtual servers (EC2 instances in AWS)
* Server-A-db and Server-B-Client
<img width="797" alt="0" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/233ed532-eda2-4fc6-ae97-6c79174df0f8">


* I openned my termius terminal and ssh Server-A-db IP address 
<img width="656" alt="4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/dd39b364-2cce-46b4-bc23-9e0554f07035">


* I 'sudo apt update" to update the package lists on my Linux system
<img width="611" alt="5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/bae04657-2657-44ad-8b7a-94e90d3e8c33">

* I installed mysql server with the command "sudo apt install mysql-server'
<img width="772" alt="6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/2554acd9-c915-49e1-9e26-a8c42831829e">

* I execute the command "sudo systemctl status mysql' to comfirm that my mysql-service is currently running and enabled
<img width="762" alt="7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d21bba74-2210-4546-872c-0bc401c7666a">


* I openned my termius and ssh Server-B-Client IP address 
* I 'sudo apt update" to update the package lists on my Linux system
* I 'sudo apt install mysql-client'
  
  <img width="859" alt="sudo mysql update and mysql client" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8d7522c8-6643-4d51-8226-14498d58bc28">


* Server-A-db uses TCP port 3306 by default, so I openned a new entry in "inbound rules" in Server-A-db  security groups
  <img width="747" alt="connecting mysql server to mysql client" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c238f2c7-852f-4543-8989-cf3d93883064">

Then remotely  connected 'Server-A-db' local IP address as the user to  'Server-B-Client' as the host.
<img width="732" alt="client connected to server updated" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d4dd8aa5-35eb-45cc-915a-01c71c0334e1">


* To configure 'Server-A-db' to allow connection from remote host,
* I execute the command "sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf"
* And change the binding address to 0.0.0.0
<img width="906" alt="vi mysql server" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/84135664-61b9-4a6d-b5fd-79464b6713fc">
