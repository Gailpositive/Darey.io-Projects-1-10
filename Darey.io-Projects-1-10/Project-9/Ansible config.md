# ANSIBLE CONFIGURATION MANAGEMENT -AUTOMATE-

## Ansible Client as a Jump Server (Bation Host)
A Jump Server (sometimes also referred as Bastion Host) is an intermediary server through which access to internal network can be provided. If you think about the current architecture you are working on, ideally, the webservers would be inside a secured network which cannot be reached directly from the Internet. That means, even DevOps engineers cannot SSH into the Web servers directly and can only access it through a Jump Server – it provide better security and reduces attack surface. On the diagram below the Virtual Private Network (VPC) is divided into two subnets – Public subnet has public IP addresses and Private subnet is only reachable by private IP addresses.

  
![image](https://github.com/travdevops/PBL-DevOps/assets/111061512/ff06fbe9-2c59-4d05-b7f4-e059055da8b4)


## TASKS
* Install and configure Ansible client to act as a Jump Server/Bastion Host
* Create a simple Ansible playbook to automate servers configuration


## STEP 1: INSTALL AND CONFIG ANSIBLE ON UBUNTU INSTANCE.
1. Open Jenkins and  Name the server Jenkins-ansible 
2. In my github account ,create a new repo called "ansible-config.mgt"
3. Install ansible.

* First, I create unbuntu ec2 instance
* I update my server with the command "Sudo apt update"
* To install ansible, I run the command "sudo apt install ansible -y
* To check the version, I run the command "ansible--version"
* Notice there is no ansible config file 
<img width="814" alt="Ansible version 101" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/c6e95bab-3f3b-4adc-971d-e3d142396c38">

* To install ansible config file, I use the "touch" command to create it
<img width="822" alt="ansible 102" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/0f806fbc-d954-4cf0-805c-892a48abe10b">

 ## 4,  STEP 2: CONFIG JENKINS TO BUILD JOB TO ARCHIVE MY REPOSITORY CONTENT EVERY TIME I SAVE IT.
* Create a freestyle project "ansible" in Jenkens and point it to "ansible-config.mgt" repository
* Configure a webhook in github and set the webhook to trigger ansible build
* Configure a Post-build job to save all (**) files.

* Ansible freestyle job pointing to "ansible-config.mgt repo
 <img width="960" alt="config1a" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/71b3ee57-9196-4d75-ac21-08debbd2737c">

* Github http url 
<img width="918" alt="Config2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/398343d8-85ef-4051-8280-59947a58674b">

* Specify  "/main" branch
* <img width="953" alt="Config3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/0d8086dd-d14a-49e9-87fb-f9b4effe504b">

* Set Github webhook trigger 
<img width="939" alt="Config4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d9ee7881-8862-4e2c-8ac4-1bf4fdb38870">

* On build steps, build job configured to save (**) files
<img width="952" alt="Config5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d5c970fe-c906-442a-b85d-52046ecb5d75"> 

## 5, STEP 3: TEST SETUP BY MAKING SOME CHANGINGS IN README.MD FILE IN MAIN BRANCH , MAKE SURE BUILDS STARTS AUTOMATICALLY AND JENKINS BUILDS ARTIFACTS IN FOLLOWING ORDER.

* Webhook successfully created
<img width="844" alt="webhook sucessful" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/cc13f592-8795-414c-bda6-bda558a60bf1">

* Readme file editted
<img width="635" alt="testing the readme" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/12ffc663-38e2-43d5-947d-97357ff8c02c">

* Jenkins builds artifacts automatically
<img width="284" alt="testing jenkins  builds auto" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/51130079-aa69-4a44-8b41-e197aea385c6">

ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/

* On my Terminal
<img width="655" alt="j terminal" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/f9797ef6-8843-4367-bd7a-06dd75fc0ebd">

## Note: Trigger Jenkins project execution only for /main (master) branch.

Now, my setup looks like this:
![image](https://github.com/travdevops/PBL-DevOps/assets/111061512/db84f534-eed6-4689-a4e2-16bd9f08e9f5)


## Note: everytime I stop/start my my Ansible server, I will have to reconfig github webhook Ip address. To avoid this, I can allocate an Elastic Ip to the server.Elastic IP is only free when allocated to an EC2 instance, so remenber to release Elastic Ip once I terminate Instance.

 ## 6, STEP 4: PREPARING THE DEVELOPMENT AREA USING VSCODE
Development ‘DevOps’ means I will require to write some codes and I shall have proper tools that will make my coding and debugging comfortable. I need an Integrated development environment (IDE) or Source-code Editor. There is a plethora of different IDEs and Source-code Editors for different languages with their own advantages and drawbacks, I can choose whichever I am comfortable with. Visual Studio Code is what I will use in this project.

* After you have successfully installed VSC, I 'll configure it to connect to my newly created GitHub repository: "ansible-config-mgt".

 
 * Config to vscode via codespace in github
 <img width="960" alt="git in vscode" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/9883645e-fe77-47b6-8d4f-29e3559249d7">
 
 * Clone down ansible-config-mgt repo to my Jenkins-Ansible instance with the command: "git clone <ansible-config-mgt repo link>"
<img width="569" alt="git clone ansible repo" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/938dbe9c-7bb3-43a7-a218-c52e24ed1601">

## 7, STEP 5: BEGIN ANSIBLE DEVELOPMENT
* In my ansible-config-mgt GitHub repository, I create a new branch called "Development" which I latter change to "hotfix" , that will be used for development of a new feature.
  
* Tip: Give the branches descriptive and comprehensive names, for example, if I use Jira or Trello as a project management tool – include ticket number (e.g. PRJ-145) in the name of my branch and add a topic and a brief description what this branch is about – a bugfix, hotfix, feature, release (e.g. feature/prj-145-lvm)

<img width="468" alt="developemnt branch" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/ccce6bf0-fc09-4e3a-a0a2-c4d71faf9c65">

* Checkout/switch to the newly created branch "Development"
<img width="409" alt="git 3 created new branch" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/d4aa0861-ed4e-4f1a-8490-9019e8aa197a">
 
* Create a directory and name it "playbook"
* Create another directory and name it "inventory"
* Within the playbooks folder, create a playbook file called "common.yml"
* Within the inventory folder, create an inventory file each for the following environments :Dev, staging, uat (testing), prod respectively
* These inventory files uses .ini languages to style to config ansible host
<img width="569" alt="git 6" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/26e0ec32-9c3a-4375-a146-3c66e5a67f0c">
<img width="492" alt="git 8" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/10e300ca-ef00-4651-99c6-a36316917da4">

<img width="916" alt="git 9" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/a969dca0-8c26-43ba-87ea-3d0d05ae97eb">

## 8, Step 4, SET AN ANSIBLE INVENTORY
* An Ansible inventory file defines the hosts and groups of hosts upon which commands, modules, and tasks in a playbook operate. Since our intention is to execute Linux commands on remote hosts, and ensure that it is the intended configuration on a particular server that occurs. It is important to have a way to organize our hosts in such an Inventory.
* Save below inventory structure in the inventory/dev file to start configuring the development servers. Ensure to replace the IP addresses according to my own setup.
* Note: Ansible uses TCP port 22 by default, which means it needs to ssh into target servers from Jenkins-Ansible host – for this I can implement the concept of ssh-agent.

* Now I need to import my key into ssh-agent: To learn how to setup SSH agent and connect VS Code to your Jenkins-Ansible instance, please see this video:
* • ( https://www.youtube.com/watch?v=OplGrY74qog) for Windows users – ssh-agent on windows
* • ( https://www.youtube.com/watch?v=OplGrY74qog) for Linux users – ssh-agent on linux

  ## I setup my SSH agent using my windows power shell terminal using the following script:

*  Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'

*   Name  : OpenSSH.Client~~~~0.0.1.0
State : NotPresent

*  Name  : OpenSSH.Server~~~~0.0.1.0
State : NotPresent

* Start the sshd service
"Start-Service sshd"

* OPTIONAL but recommended:
"Set-Service -Name sshd -StartupType 'Automatic'"

* Confirm the Firewall rule is configured. It should be created automatically by setup. Run the following to verify
" (!(Get-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -ErrorAction SilentlyContinue | Select-Object Name, Enabled)) {
    Write-Output "Firewall Rule 'OpenSSH-Server-In-TCP' does not exist, creating it..."
    New-NetFirewallRule -Name 'OpenSSH-Server-In-TCP' -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
} else {
    Write-Output "Firewall rule 'OpenSSH-Server-In-TCP' has been created and exists."
}

<img width="915" alt="powershell1" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/ff78a63e-f860-4548-be48-cb172d63ed28">
<img width="960" alt="powershell2" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/68e32bc7-55aa-44a0-9a2b-3b4d450a850e">
<img width="945" alt="powershell3" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/c9ae04d3-3de4-4c0a-ad0c-160b22fc6988">

## Import my key into SSH agent
* eval `ssh-agent -s`
* ssh-add <path-to-private-key>
*Confirm the key has been added with the command below, you should see the name of your key:
* ssh-add -l
* Now,ssh into your Jenkins-Ansible server using ssh-agent:
* ssh -A ubuntu@public-ip
<img width="588" alt="process to loging in remotely via ssh 9" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/1a5e1cb4-422d-4601-b0f5-bd1a8ef37ba1">

* From the Jenkins-Ansible, ssh into all the remote servers with the same command ssh user@public-ip
<img width="702" alt="ssh into all Nodes 7" src="https://github.com/travdevops/PBL-DevOps/assets/111061512/0d069913-043a-484c-b060-2479d6b71a17">

* Note: Ubuntu-based servers user is "ubuntu" and user for RHEL-based servers is "ec2-user".

## Update your inventory/dev.yml file with this snippet of code:
