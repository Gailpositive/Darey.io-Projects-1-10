# ANSIBLE-AUTOMATE-PROJECT

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
<img width="809" alt="ansible version config none" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/033dff36-2c29-4fc7-8692-d9b9f8ad85a0">

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

* Jenkins builds automatically
<img width="284" alt="testing jenkins  builds auto" src="https://github.com/Gailpositive/ansible-config-mgt/assets/111061512/51130079-aa69-4a44-8b41-e197aea385c6">
