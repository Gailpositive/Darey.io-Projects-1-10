# INTRODUCTION TO SHELL SCRIPTING AND USER INPUT
## "Prerequisites: I'll be using my Git Bash Terminal, Ubuntu Virtual Box and VS-code Terminal"

## My First Shell Script
* First, I created a directory with the 'mkdir'  command 'shell-scripting and cd into the directory. 
* Created a file called 'user-input.sh' with the 'touch' command.
* I executed the code 'code .'  to navigate to vscode terminal to input some block of codes. then back to my powershell.
* I execute the script './shell-scripting' to get the stdout.
*  "Enter your name" , promt the user to enter their name 
* And prints a response 'Hello, User name, Nice to meet you'
* I run the command 'ls -al' to list the files in the directory to ensure it is executable else, I will use the command "chmod +x" to make it executable. 

<img width="459" alt="shell scripting 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b3d93aa4-5a4c-40f6-b0fc-24daa3a0d9b0">


* On my vscode terminal, I executed a block of code.
* I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation: # promt the user for their name.
* Enter the 'echo' command  to print the statement 'Enter your name'.
* The 'read' command takes input from my keyboard and assign it to a name variable.
* Inserted a line of non executable annotation # Display a greeting with the entered name
* The 'echo' command prints 'Hello, follow with the user variable "$name!", nice to meet you'
* Save and exit
<img width="728" alt="code   2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b658a733-dbc5-4bc3-9e89-ce0291305ebb">


## Directory Manipulation And Navigation

* With the 'touch' command, I created another file 'navigating-linux-filesystem.sh'
* Navigate to my vscode with the command 'code.' to executed some blocks of codes and back to my powershell.
* Execute the script './navigating-linux-filesystem.sh'
* Display my current directory 'shell-scripting'
* Creates a new directory
* Display new directory created 'my_directory'
* Cd into 'my_directory'
* Display present working directory "my_directory"
* Creates files
* files created
* Dsiplay files in the present working directory
* 'file1.txt, file2.txt' 
* Cd .. back to previous directory 'shell-scripting'
* 'my_drectory' directory was removed
* ls -al files in the current directory: 'navigating-linux-filesystem.com'
  
<img width="457" alt="shell scripting 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/6ef008b7-d8a0-4e08-a95e-b473554134a4">
 
* On my vscode, I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
*  Insert a non executable comment annotation, # display current directory.
*  Insert the 'echo' command to print my 'present working directory' follow by the $PWD system variable
*  A non executable comment annotation, # Create a new directory.
*  The 'echo' command to prints 'Creating a new directory...
*  Create "my_directory" with the command "mkdir" 
*  Print 'New directory created' with 'echo' command
*  Insert a non executable comment annotation, # Change to the new directory
*  Print "changing to the new directory..."  with the 'echo' command
*  cd into 'my_directory'
*  The 'echo' command prints "current directory" , follow with the $PWD system variable
*  Insert a non executable comment annotation, # Create some files
*  The 'echo' command  prints 'creating files...'
*  With the 'touch' command , creates two txt files 'file1.txt, file2.txt
*  Print 'files created' with the 'echo command
*  Insert a non executable comment annotation, # List the files in the current directory
*  The 'echo' command, prints "files in the current directory"
*  And list the files with the 'ls' command
*  Insert a non executable comment annotation, # Move one level up
*  The 'echo' command prints "Moving one level up..."
*  "Cd .." command to change directory to the last directory 'shell scripting'
*  The 'echo' command prints 'current directory using the $PWD system variable
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

* Create a new file 'sorting.sh with the 'touch' command 
* Navigate to my vscode with the command 'code.' to executed some blocks of codes and back to my powershell.
* I execute the script './sorting.sh'
* "echo' command to print 'creating files... 
* Files created.
* Files are created in their current order
* Displaying all files in in the shell-scripting directory in their current order: File1.txt, file3.txt, sorting.sh,  file2.txt, navigating-linux-filesystem.sh, user-input.sh
* 'sorting files alphabetically...
* Files sorted, piped and redirected to a new file "sorted_files.txt
* cat command to display data in the 'sorted files':  file1.txt, file2.txt, file3.txt, navigating-linux-filesystem.sh, sorted_files.txt, sorting.sh, user-input.sh,
* Remove original files..."
* Renamed sorted files.txt'to a more discriptive name "sorted_files_sorted_alphabetically.txt" 
* 'echo' to print 'files renamed'
*  Insert a non executable comment annotation, # Display the final sorted file
*  'echo to print 'final sorted files
*  cat "sorted_files_sorted_alphabetically.txt" : file1.txt, files2.txt, file3.txt, navigating-linux-filesystem.sh, sorted_files.txt, sorting.sh, user-input.sh

<img width="459" alt="shell scripting 8" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9f03793c-2434-4d37-a681-1e357c893af1">

<img width="486" alt="shell scripting 9" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/50ecbbd7-6965-493d-ab37-e67903ff3160">


* On my vscode, I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation, # Create three files
* 'echo' command to print 'Creating files...." in stdout
* 'echo' to print "This is file3." and redirect it to "file3.txt  using the redirection command '>'.
* 'echo' to print "This is file1." and redirect it to "file1.txt  using the redirection command '>'.
* 'echo' to print "This is file2." and redirect it to "file2.txt  using the redirection command '>'.
* 'echo' to print "Files created." in stdout
*  Insert a non executable comment annotation, # Display the file in their correct order
* 'echo' to print "Files in their current order" 
* Now, list the files in their current order with the 'ls' command in stdout
* Insert a non executable comment annotation, # Sort the files alphabetically
* 'echo command to print "sorting files alphabetically..." in stdout 
* The "ls" command list all the files in the PWD, The pipe "|" character combines the listed stdout and sort it orderly using the "sort" command and redirect it to a file called "sorted_files.txt
* echo command to print "Files sorted" in stdout
* Insert a non executable comment annotation, # Display the sorted files
* echo command prints "sorted files" in stdout
* "cat sorted_files.txt" command,  reads and display the data of the file in stdout
* Insert a non executable comment annotation, # Remove the original files
* echo command prints "removing original files..."
* 'rm' command removes file1.txt, file2.txt, file3.txt from PWD
* echo command prints "original files removed." in stdout.
* Insert a non executable comment annotation, # rename the sorted file to a more descriptive name
* echo to print "renaming sorted files..."
* mv command renames "sorted_files.txt to sorted_files_sorted_alphabetically.txt
* echo command to print "files renamed" in stdout
* Insert a non executable comment annotation, # Display the final sorted files
* echo to print "Final sorted files." in stdout
* cat sorted_files_sorted_alphabetically.txt to display content of the file
  

<img width="773" alt="shell scripting 6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/167cc803-eb30-4dbd-a385-c2c02650a10b">

<img width="768" alt="shell scripting 7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/373e48e0-9dbf-4898-8810-ed65e805c12c">


# WORKING WITH NUMBERS AND CALCULATORS

* Creates a "calculation.sh" file with "touch"command
* Navigate to my vscode with the command 'code.' to executed some blocks of codes and back to my powershell.
* I execute the script './calculation.sh'
* Defining two variables "name" with numeric values: "number1": 10, "number2" =5
* Finding the Sum (addition) of the variables values "number1": 10 and "number2" : 5" =15
* Finding the difference (substraction) of the variables values "number1" "number2" =5
* Finding the product (multiplication) of the variables values  "number1"  "number2"  =50
* Finding the quotient (division) of the variables values "number1"  "number2"=2
* Finding the remainder of the integer division of the variables values "number1" % "number2" =0
* Awk and CMD command manipulates and automates script line:1: "BEGIN {sqrt=5; print sqrt} and Prints systax error twice
* variable "Number1" : 10 (base) raise to power 2 (exponent)  = 100.  (10 to the power of 2 can be expressed as 10^2 = 10 × 10 = 100)
<img width="456" alt="shell scripting 11" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9f978479-c040-4da4-ba47-ca9de670f10e">


* On my vscode, I enter the first line of operation of the script, 'shebang '#!' follow by the interpreter '/bin/bash' command.
* Insert a non executable comment annotation, # Define two variables with numeric value"
* variable "num1"=10
* variable "num2"=5
* Insert a non executable comment annotation, # Perform basic arthemetic operations
* addition of the variables: sum=$((num1 + numb2))
* Subtraction of the variables: difference=$((num1 - numb2))
* Multiply the variables: product=$((num1 x numb2))
* Divide the variables: quotient=$((num1 / numb2))
* Remainder of  the variables:$((num1 % numb2))
* Insert a non executable comment annotation, # Display the result
* "echo" command prints "Number 1: $num1"
* "echo" command prints the  "Number 2: $num2"
* "echo" command prints "Sum: $sum"
* "echo" command prints "Difference: $difference"
* "echo" command prints "Product: $product"
* "echo" command prints "Quotient : $quotient"
* "echo" command prints "Remainder: $remainder"
* Insert a non executable comment annotation, # Perform some more complex calculation
* power_of_2=$((num 1 ** 2))
* square_root=$( awk "BEGIN {sqrt=num2; print sqrt}")
*  Insert a non executable comment annotation, # Display the result
*  "echo" command to print "Number 1 raised to the power of 2: $power_of_2"
*  "echo" command to print "Square root of number 2: $square_root"
<img width="768" alt="shell scripting 10" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/262a2f80-60f1-4e99-a1d8-78f9a314b61e">


## FILE BACKUP AND TIMESTAMPING

* Login on my ubuntu virtual box
* I make "shell-scripting" directory with the "mkdir" command
* I cd into the directory
* Create a "backup.sh" file with the "touch" command
* Navigate to my vscode with the command 'code.' to executed some blocks of codes and back to my powershell.
* I execute the script './backup.sh'
* Script did not execute hence permission denied
* To change mode and execute the script, I run the command "sudo chmod +x ./backup.sh
* Enter my password
* backup completed. files copied to "path/to/source/directory"
* 


<img width="430" alt="shell scripting 16" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/716c82c5-510d-4528-946b-fbe06e815e45">

<img width="430" alt="shell scripting 16" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/716c82c5-510d-4528-946b-fbe06e815e45">


* 
<img width="767" alt="shell scripting 12" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/cf825394-7d63-4c33-ab16-1f47f90e64ad">
