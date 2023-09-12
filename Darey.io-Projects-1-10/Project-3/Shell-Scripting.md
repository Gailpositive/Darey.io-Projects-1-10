# INTRODUCTION TO SHELL SCRIPTING AND USER INPUT
## "Prerequisites: I'll be using my Git Bash Terminal, Ubuntu Virtual Box and VS-code Terminal"

## My First Shell Script
* First, I mkdir 'shell-scripting and cd into the directory. 
* Created a file called 'user-input.sh with the 'touch' command.
* I executed the code 'code .'  to navigate to vscode terminal to input some block of codes. then back to my powershell.
* I execute './shell-scripting' to get the output in the image below.
* In addition, I run the command 'ls -al' to list the files to ensure it is executable. 

<img width="459" alt="shell scripting 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b3d93aa4-5a4c-40f6-b0fc-24daa3a0d9b0">


* On my vscode terminal, I executed a block of code.
* I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation: # promt the user for thier name.
* Enter the 'echo' command  to print the statement 'Enter your name'.
* Use the 'read' command to take input from my keyboard and assign it to a variable.
* Inserted another line of non executable annotation
* Use the 'echo' command to print 'Hello, follow with the  $name! user variable, nice to meet you'
* Save and exit
<img width="728" alt="code   2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b658a733-dbc5-4bc3-9e89-ce0291305ebb">


## Directory Manipulation And Navigation

* With the 'touch' command, I created another file 'navigating-linux-filesystem.sh'
* Navigate to my vscode with the command 'code.' to executed some blocks of codes and back to my powershell.
* Execute the file command './navigating-linux-filesystem.sh'
* Display my current file directory 'shell-scripting'
*  Created new directory 'my_directory'
* Cd into a new directory called 'my_directory'
* Created two files, 'file1.txt, file2.txt' 
* Cd .. back to previous directory 'shell-scripting'
* rm command to remove  'my_directory' directory
* ls -al files in the current directory: 'navigating-linux-filesystem.com'
  
<img width="457" alt="shell scripting 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/6ef008b7-d8a0-4e08-a95e-b473554134a4">
 
* On my vscode, I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
*  Insert a non executable comment annotation, # display current directory.
*  Insert the 'echo' command to print my 'present working directory' follow by the $PWD system variable name
*  Insert a non executable comment annotation, # Create a new directory.
*  Use the 'echo' command to print 'Creating a new dicrectory...
*  Create a new directory with the command 'mkdir my_directory'
*  Print 'new directory created' with 'echo' command
*  Insert a non executable comment annotation, # Change to the new directory
*  Print change to the new directory with the 'echo' command
*  cd into 'my_directory'
*  Use the 'echo' command to print current directory follow with the $PWD system variable
*  Insert a non executable comment annotation, # Create some files
*  With the 'echo' command , print 'creating files...'
*  With the 'touch' command , create two saperate txt files 'file1.txt, file2.txt
*  Print 'files created' with the 'echo command
*  Insert a non executable comment annotation, # List the files in the current directory
*  With the 'echo' command, print files in the current directory
*  And list the files with the 'ls' command
*  Insert a non executable comment annotation, # Move one level up
*  With the 'echo' command, print Moving one level up
*  Cd .. to change directory to the previous directory 'shell scripting'
*  Print with the 'echo' command 'current directory using the $PWD system variable
*  Insert a non executable comment annotation, # Remove the new directory and its content
*  'Echo' to print 'Removing the new directory...'
*  Using the command flag 'rm -rf to remove 'my_directory" directory  recursively
*  'echo' to print 'Directory removed'
*  Insert a non executable comment annotation, # List the files in the current directory again
*  'Echo' to print  'files in the current directory'
*  List files with the 'ls' command
<img width="774" alt="shell scripting 4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b2372a5e-1893-43f6-8a74-377791bc35a5">

<img width="635" alt="shell scripting 5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/96377381-6353-4b90-9951-df9182cbc6b5">


## File Operation And Sorting

* Create a new file 'sorting.sh with the command 'touch'
* Navigate to my vscode with the command 'code.' to executed some blocks of codes and back to my powershell.
* On my vscode, I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* On powershell terminal, execute the command ./sorting.sh
* "echo to print 'creating files' without actually creating the file with the 'touch' command
* 'echo' to print  'file created'
* 'echo' to print all 'files in the shell-scripting in their current order:
* File1.txt, file3.txt, sorting.sh,  file2.txt, navigating-linux-filesystem.sh, user-input.sh
* 'echo' to print 'sorting files alphabetically...
* 'echo' to print 'files sorted'
* list of sorted files:file1.txt, file2.txt, file3.txt, navigating-linux-filesystem.sh, sorted_files.txt, sorting.sh, user-input.sh,
* 'echo' to print 'Remove original files'
* 'echo' to print  'Renamed sorted files'
* 'echo' to print 'files renamed'
*  Insert a non executable comment annotation, # Display the final sorted file
*  'echo to print 'final sorted files: file1.txt, files2.txt, file3.txt, navigating-linux-filesystem.sh, sorted_files.txt, sorting.sh, user-input.sh

<img width="459" alt="shell scripting 8" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9f03793c-2434-4d37-a681-1e357c893af1">

<img width="486" alt="shell scripting 9" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/50ecbbd7-6965-493d-ab37-e67903ff3160">


* On my vscode, I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation, # Create three files
* input 'echo' command to print 'Creating files...."
* 'echo' to print "This is file3." redirection operator '>' to "file3.txt"
* 'echo' to print "This is file1." redirection operation '>' to "file1.txt"
* 'echo' to print "This is file2." redirection operation '>' to  "file2.txt"
* 'echo' to print "Files created."

*  Insert a non executable comment annotation, # Display the file in their correct order
* 'echo' to print "Files in their current order"
* list the files with the 'ls' command

* Insert a non executable comment annotation, # Sort the files alphabetically
* 'echo command to print "sorting files alphabetically..." in stdout 
* The command "ls" first list the files, '|' the pipe character combines both listed files and the sort  it to sort
* echo command to print "Files sorted" in stdout

* Insert a non executable comment annotation, # Display the sorted files
* echo command to print "sorted files" in stdout
* cat sorted_files.txt to  read and display the data in the file

* Insert a non executable comment annotation, # Remove the original files
* echo command to print "removing original files..."
  

<img width="773" alt="shell scripting 6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/167cc803-eb30-4dbd-a385-c2c02650a10b">

<img width="768" alt="shell scripting 7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/373e48e0-9dbf-4898-8810-ed65e805c12c">



