# BUILDING A COMPREHENSIVE BUSINESS  WEBSITE SOLUTION AND INTEGRATION OF VARIOUS TOOLS AND TECHNOLOGIES.
## A THREE-TIER WEB APPLICATION ARCHITECTURE, A SINGLE REMOTE MYSQL DATABASE AND AN NFS SERVER AS SHARED BACKEND STORAGE FILES. 
## Solution Prerequisites: Infrastruction: AWS.
## Three-Tier Webservers Linux: Redhat.  
## Database Server: Ubuntu + Mysql (Preferable but I used Redhat). 
## Storage server: Redhat + NFS Server. 
## Programming language: PHP. Code Repository: Github.  

## NOTE: Not all storage is suitable, hence it is important to know the suitable storage solution for every use case. Such as: what data will be stored, in what format, how this data will be accessed, by whom, from where, how frequently etc. Based on theses questions, I will be able to choose the right suitable storage for my solution. 

## SELF STUDY:
* Network attach storage (NAS) https://en.wikipedia.org/wiki/Network-attached_storage
* Storage area network (SAN) https://en.wikipedia.org/wiki/Storage_area_network, and related protocol like NFS(s), FTP, SMB, iSCSI.
* Block-level storage https://en.wikipedia.org/wiki/Block-level_storage and how it is used by cloud providers, and how it differs from Object Storage https://en.wikipedia.org/wiki/Object_storage.
* On the example of AWS services https://dzone.com/articles/confused-by-aws-storage-options-s3-ebs-amp-efs-explained, understand the difference between Block storage, Object storage and Network file system. 

## STEP 1: Creating a Business Website Using NFS For The Backend File Storage.
# PREPARE NFS SERVER
* Spin up AWS redhat instance
* Configure and attach 3 logical volumes (LVM) on the server: "lv-opt", "lv-apps", "lv-logs".
* Format the disk as "xfs"
* Create mount points on: "/mnt"
* Mount 'lv-opt' on "/mnt/opt"
* Mount 'lv-apps' on "/mnt/apps"
* Mount 'lv-logs' on "/mnt/logs"
* 

 * Three volumes created and attached to an NFS  server
 <img width="735" alt="three volumes attach 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/666f35fb-5c71-4e2b-8154-f9001c74be38">

* Running the command "lsblk" to inspect the names of  three blocks devices attached to the server :"xvdf", "xvdg", "xvdh".
<img width="530" alt="lsblk 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d85bc123-8aac-47b0-bada-e0762669b0cb">
  
* Running the "ls/dev/ to view all three created blocks devices
 <img width="815" alt="ls dev 4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/f55f4bef-8eba-49e8-922c-7b72f790ec82">

* With the "df-h" command, I can view all mounts and available space on my server
<img width="445" alt="view available space in dick 5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/7b955231-7cb6-4f0b-bb79-74bd0058e896">

* To partition the three disks individually, I run the command 'sudo fdisk /dev/xvdf
 <img width="624" alt="partition two updated and correct" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c73618fa-6a83-40df-b9ab-0ef3fcc33ef9">

* On the second disk,  I run the command 'sudo fdisk /dev/xvdg
<img width="583" alt="partition one updated and correct" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/743f3bd7-7d32-4d1b-82a0-15f1e49783e1">

* And on the three disk,  I run the command 'sudo fdisk /dev/xvdh
<img width="659" alt="partition three updated and correct" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/f7b4238b-8f0c-4826-aa04-311c5c568fd7">

* Executed the command "lsblk" to view a three partioned disks
<img width="522" alt="partition lsblk updated 4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/01e6fd38-ea33-4b5d-a033-3d249539564b">

* Installing lvm2 packaging
<img width="852" alt="sudo yum install lvm2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/83eb3122-1987-4f22-8770-22d20954ddd8">

* Checking for available partition
<img width="445" alt="sudo lvmdiskscan" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/eb05f419-8a71-45b0-a3aa-03fb9a6b247e">

* Employing the "pvcreate" tool to designate each of the three disks as physical volumes for utilization by LVM
<img width="488" alt="pvcreate" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/33f822ef-982e-43ea-891f-8c85f3d1e8ef">

* PV has been created
 <img width="378" alt="sudo pvs" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b04cd710-681e-4b1c-9ba3-38b9840d8ead">

* Use "pvcreate" to add all three PV to one  volumes group called "webdata-vg"
<img width="544" alt="df -h sudo mount" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/2fa10a0a-b72f-4281-90c0-b4653df943d1">

* "VG successfully created
<img width="579" alt="webdata-vg created" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8d03247d-99f0-4fce-9a76-097155f65c3b">

 
* Three logical volumes created: lv-apps stores website data. lv-logs stores log data, lv-opt stores ..... data.
<img width="493" alt="sudo lvcreate" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c9ade003-6bd5-409e-b514-de3606ba8bcf">

* Logical volumes created and running.
<img width="600" alt="sudo lvs" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/70174253-5a51-4084-8ea6-96e1a78823e1">

* Verifying the entire set up with the command "sudo vgdisplay -v #view complete setup - VG, PV, and LV"
<img width="743" alt="verify entire set up 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c180afc5-bb70-4931-8aa7-5f61b36fee21">

<img width="772" alt="verify entire set up 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/59a10e02-128c-498d-b8a2-8d095c1f1b2e">

<img width="868" alt="verify entire set up 3 n4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/3c808ee8-5a71-471f-aef3-0b9e74631b32">

<img width="675" alt="verify entire set up 5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1f83b924-f4f9-4017-a980-e59075484d59">

* "sudo lsbik"
<img width="578" alt="lsbik comes after mounting LV directories" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/f7cae3a0-b0ca-488a-863c-70755d63af96">

* Format logical volumes with "ext4" filesystem
 <img width="637" alt="sudo mkfs -t xfs devwebdata-vglv-apps" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/33a51f25-af82-4157-87b1-0ea2e660b270">

* Create mount point "/mnt"
<img width="486" alt="create mounts point" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/26fae9a5-72e4-48df-a81a-15b664d51226">

* Create directory to store web files and recovery log to back up log data
* Can also use "sudo mkdir -p /var/www/html
  <img width="420" alt="create mnt directory to store to store website file and create recovry files" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e034fa96-7741-4b0a-9917-216af30e0d9b">

* Mount on all three LV on "/mnt"
*  and use the rsyn utility tool to backup all files in the log directory "/var/log" into the "/home/recovery/log"
*  Run "sudo rsync -av /home/recovery/logs/. /var/log" to restore log files back into "/var/log directory
<img width="666" alt="This process comes immediately before mounting" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/46bcb384-57fd-4471-ad21-4508982d9854">

* "lsblk"
<img width="666" alt="This process comes immediately before mounting" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/bce52bee-3a97-4b41-a2b2-324a123ee51c">

* "sudo blkid"
<img width="806" alt="sudo blkid," src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/2fb0f9cb-cc64-4827-8133-03c6110b08cf">

* Update "/etc/fstab" using my UUID
* "sudo vi /etc/fstab"
<img width="681" alt="sudo vi etc fstab" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/d0c6ede9-0a36-4bca-9cb3-ae09380af1c6">

* Test the config and reload deamon
<img width="513" alt="sudo mount to test config and reload deamon 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8779efe7-b7f9-42b4-86e3-d2deb828a355">

* Setup running
<img width="572" alt="verify set running df -h" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/f0bbd966-b821-40b9-867c-3ba8857552a0">


## STEP 2: INSTALLING AND CONFIGURE NFS Server
* Run the following script:
* sudo yum -y update
* sudo yum install nfs-utils -y
* sudo systemctl start nfs-server.service
* sudo systemctl enable nfs-server.service
* sudo systemctl status nfs-server.service


# NOTE:Make  
