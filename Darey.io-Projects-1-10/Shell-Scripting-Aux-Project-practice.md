

* echo $SHELL to display my current shell
* cat /etc/shells displays list of available shells
* I can install any shell of choice that is not available eg:sudo apt install csh -y

  <img width="752" alt="practice shell 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9129cece-69f9-4027-8331-4fccc4710ad9">


* cat /etc/shells, to display shells created
* chsh -s to cd into it, if I want to use it but in this case, we will go with the defualt bash shell

<img width="725" alt="shell 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/aac7c936-0494-4193-a187-31fb915bf694">

*cd into root with the command "cd /"
* List directory witht he command "ls"
* All commands has their locations. for example "which mkdir" is found inthe command part /usr/bin/mkdir
* whereis mkdir", will display the full part whee I can find the "mkdir" directory
* I can delete and mkdir eg: sudo apt install mkdir -y((but DON NOT DELETE ANY FILE))
* cd bin 
* ls just to see other folders there  
* <img width="679" alt="shell 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/fa0a09d4-e10d-46a4-b588-606cc8269b52">

* ls | grep mkdir: with the grep command, I can search for specific command or utility
* whoami, tells me my pwd
* curl https://www.google.com: checks if a google server is up or on, that is online or offline. It works for any website
* I can also use ping https://facebook.com
<img width="751" alt="shell 4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/75616fd8-924a-4969-a6c9-eac57542dcb6">

## Using the echo command, what ever I type afterwards, is returned back to me . see exampls below:
*  echo 5, response back 5
* echo Hi Abigail
Hi Abigail
* echo My Name is Abigail
My Name is Abigail
* For calculation, I had to put a double open and close braces for it to work
* echo 7+10 returns it exactly how i input it
* NOTE: ($ ,TWO BRACES ,VALUES)
* NOTE: EVERYTHING THAT COMES AFTER $ IS AN ARGUMENT OR COMMAND 

<img width="710" alt="shell 5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/71ef86a5-413c-4747-8f1b-fe03f889511d">
