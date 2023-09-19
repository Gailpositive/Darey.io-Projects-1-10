# SHELL SCRIPTING CRASH COURSE


* echo $SHELL to display my current shell
* cat /etc/shells displays list of available shells
* I can install any shell of choice that is not available eg:sudo apt install csh -y
  <img width="752" alt="practice shell 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9129cece-69f9-4027-8331-4fccc4710ad9">

##:
* cat /etc/shells, to display shells created
* chsh -s to cd into it, if I want to use it but in this case, we will go with the defualt bash shell

<img width="725" alt="shell 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/aac7c936-0494-4193-a187-31fb915bf694">

##:
*cd into root with the command "cd /"
* List directory witht he command "ls"
* All commands has their locations. for example "which mkdir" is found inthe command part /usr/bin/mkdir
* whereis mkdir", will display the full part whee I can find the "mkdir" directory
* I can delete and mkdir eg: sudo apt install mkdir -y((but DON NOT DELETE ANY FILE))
* cd bin 
* ls just to see other folders there  
* <img width="679" alt="shell 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/fa0a09d4-e10d-46a4-b588-606cc8269b52">

##:
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


##
* echo welcome to darey.io, will print  welcome to darey.io
* echo welcome to darey.io > welcome.txt, will create and redirect the argument to welcome.txt
* echo welcome to darey.io >> welcome.txt, will create, redirect and append the argument to welcome.txt (to append means to add it with deleting previous infomation)
* cat welcome.txt, to display file content
<img width="626" alt="shell 6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/138a90d6-0bcc-49c9-89cc-47634aaebef7">


## Chain of command 
## TO REDIRECT A SCRIPT TO A FILE CAN ALSO BE CALLED TO CHAIN THE SCRIPT TO THE FILE
## SOME SHORT SCRIPT FILES ENDS WITH .SH


## THIS IS A SHORTER CUT TO CREATING A SCRIPT, RATHER THAN USING TOUCH FILE TO CREATE FILE AND VI INTO THE FILE TO WRITE CONTENT.
* echo welcome to class five >> welcome.txt | cat welcome.txt, to print welcome to class five, append/push it to welcome.txt file and read the file
* If I repeat the last echo command, it will print incresing the last line command as seen in the image below
*
<img width="646" alt="shell 7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/ae8d72fc-5d64-4545-9910-6dd0f23a5791">


## NOTE: ~ IS USED TO DENOTE HOME DIRECTORY. / DENOTES ROOT DIRECTORY
## eg: cd ~ .   cd /

## A MORE COMPREHENSIVE STEPS TO CREATING A SCRIPT AND INTERPRETING IT
*First, mkdir with a .sh extension
cd into the directory
* Next, touch command to create a file with .txt extension
* vi into the file to write my script
* back to my terminal

* Execute my script: ./ script.txt
* To execute the file: chmod u+x ./script.txt
* If it is a long script, take it step by step, adding a #comment to for annotation. Do not write all the script once.
<img width="617" alt="shell 8" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/3708a81a-9f5f-4de9-bc26-a8dc2e60cf51">


* Enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* Write my script starting with the echo command
<img width="678" alt="shell 9" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/57fed460-fb60-4346-938e-595bb1bb592f">

## Using the nano editor
* Mkdir to create a directory "practice.code"
* cd into the directory "practice.code"
* touch command to cretae file "script.sh"
* ls to list
* nano script.sh and back to shell
* cat to read script

<img width="733" alt="shell 10" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/ed54b270-183b-43f7-af8c-a6d30c04d512">

* On my nano editor, Enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation: # (briefly explain what Im doing)
  
<img width="720" alt="shell 11" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/4cc6f6e4-f967-45d7-95b4-7fb462c2e8ef">

## I have to execute the file
* nano script.sh
* ls -ltr to list script
* chmod u+x script.sh , to make script executable 
* ls -ltr again to view executable script
* execute the script ./script.sh
<img width="618" alt="shell 11" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/7ed5e9b2-6205-48f1-be5a-64fdce605d05">


## Asking user to input their info

* nano script.sh to write script and back to shell
* ./script.sh
* Input my name
* input name of my school
* input my student position
* <img width="443" alt="bahah" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8b391ebe-19b5-4d9f-8262-339281a9b8df">

* On my nano editor, enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* echo command to print statement
* 
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* read command to read name
* 
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* echo command to print statement

* 
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* read command to read name

*  
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* echo command to print statement
<img width="691" alt="olkl" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/ccfec6c9-c02e-4cdb-aa7d-6107018ba615">

* 
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* read command to read name
* 
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* sleep 3 : sleep command delays the responds after 3 mins
* date command, add date to the script
* 
<img width="481" alt="zdf" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/bf9c7097-d58b-4e59-98e1-35095a996b01">


* Mkdir practice.code
* cd into practice.code
* touch shell.sh to create file
* nano shell.sh to write code and back to terminal
* run script ./shell.sh
* change mode: chmod u+x shell.sh
* run script again "./shell.sh"
* Enter my name
  
<img width="603" alt="009" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e32a80ac-145d-466c-bc55-02b41f91142a">


* On my nano editor, enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation: # (briefly explain what Im doing)
* echo to print

* Insert a non executable comment annotation: # (briefly explain what Im doing)
* read username

*  Insert a non executable comment annotation: # (briefly explain what Im doing)
* echo to print $username
* sleep 3
* date
* Login sucessful...
<img width="628" alt="bgq" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/710f4ec7-0eee-489c-a146-61e1e366d801">


