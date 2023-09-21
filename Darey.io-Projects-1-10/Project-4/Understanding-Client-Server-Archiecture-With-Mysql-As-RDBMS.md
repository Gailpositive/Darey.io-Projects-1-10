# UNDERSTANDING CLIENT SERVER ARCHITECTURE WITH MYSQL AS RDBMS. 

# Prerequisites: I spinned up two AWS EC2 instances. One as a client server and the other as a webserver, and loggin through the IP address on my termius terminal.


## Implementing A Client Server Architecture Usng Mysql Database Mnagement System (DBMS)

* First, I spinned up and configure two-Linux based virtual servers (EC2 instances in AWS)
* Server-A-db and Server-B-Client
<img width="797" alt="0" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/233ed532-eda2-4fc6-ae97-6c79174df0f8">


* I opened my termius terminal and ssh the IP address into my instance
<img width="656" alt="4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/dd39b364-2cce-46b4-bc23-9e0554f07035">

* On Server-A-db,
* I 'sudo apt update" to update the package lists on my Linux system
<img width="611" alt="5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/bae04657-2657-44ad-8b7a-94e90d3e8c33">

* I installed mysql server with the command "sudo apt install mysql-server'
<img width="772" alt="6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/2554acd9-c915-49e1-9e26-a8c42831829e">

* I execute the command "sudo systemctl status mysql' to comfirm that my mysql-service is currently running and enabled
<img width="762" alt="7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d21bba74-2210-4546-872c-0bc401c7666a">
