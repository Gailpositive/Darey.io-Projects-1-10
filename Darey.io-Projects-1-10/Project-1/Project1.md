
# LAMP-STACK IMPLEMENTATION.

" Attempting to experiment with different terminals to observe their individual functionalities and behavious, I initially performed a git clone operation into my github account on ubuntu virtualbox terminal"

<img width="407" alt="git-clone-in vbox" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/f008da7f-03b1-47e7-9923-2727dba88432">



" Git cloned into my github account on virtual studio code (vsc) terminal"

<img width="726" alt="git-clone-in-vscode" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/6e660436-8c50-4d2c-90a6-4efb831e9ddc">


" Git cloned into my github account on windows powershell terminal"

<img width="868" alt="git-clone-in-Wpowershell" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/952e577a-75db-43b6-a68a-2c9970bc9b96">



To get started,I had previously set-up my AWS account , on a default port 80 TCP, and provisioned an ubuntu server, I just logged into my AWS ec2 instance.

<img width="838" alt="Captureec2 instance" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/e0d34487-0618-40c1-8790-28496622ed27">

   "Port 80 TCP protocol"
<img width="925" alt="port 80" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/8573defb-ba9f-4b42-b9b6-f211806f0da4">


Next, Is the Installing of apache2 and updating the fire wall!
" To execute this command, I "sudo apt install" on my terminal to update my apache2 package before installation, and afterwards, executing the commands "sudo apt install apache2", to install apache2 package on my termuis terminal

<img width="960" alt="apt installed on termuis" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/c5f861e0-c0bb-4495-ae5b-0557b4425aa4">

  " Running the command "sudo systemctl status apache2" on my ubuntu virtualbox , to verify that apache2 is runing as a service on my operating system"
<img width="399" alt="lamp-stack-4" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/b9f12b11-5371-41c0-99bf-c322382685b0">

"Apache2 web server sucessfully installed and accessible through firewall "

<img width="833" alt="apt page defualt 2" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/59d68cb0-4b97-46dc-94cd-cd7ad0afd07f">

 "Apache2 web server located in an index.html file. To locate this file in ubuntu ec2 instance, I changed directory to /var/www/htm. To display the content of the index.file, I used the cat command (cat index.html). To change  the files inside index.html, I used the vi editor and input "This is my first ever amazing webserver experience"

<img width="926" alt="cat file" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/6fc89372-d015-4ed2-b1d7-a156371690d7">

Running the following "curl" commands through the Domain name server (DNS) "curl http://localhost:80", through the Ip server "curl http://127.0.0.1:80" or just simply without the port 80 protocol; "curl http://localhost" to request Apache2 http server port 80 on my local machine.

 <img width="902" alt="curl localhost" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/350b79e7-c4b3-4f44-af8e-44e8c9925342">

 In order to assess the responsiveness of my Apache2 webserver on a browser, I executed the IP command http://<Public-IP-Address>:80

<img width="633" alt="first webserver" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/5baac9b4-a7ac-4837-abcd-9026af126731">


My webserver is up and running. Next, is to MYSQL Installation

I executed the command "sudo apt install mysql-server" to install mysql

<img width="952" alt="mysql-server installed" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/d4bab7c8-0d51-46cb-bb1a-a90398b4b548">


  "and logged into the console using the follow command "sudo mysql"

<img width="702" alt="mysql pwd inputted" src="https://github.com/Gailpositive/Darey.io-Projects-1-10/assets/111061512/7c19e2f2-5f0f-4283-9adc-7f4c5012ee3a">

