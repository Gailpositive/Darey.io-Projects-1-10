# BUILDING A COMPREHENSIVE BUSINESS  WEBSITE SOLUTION AND INTEGRATION OF VARIOUS TOOLS AND TECHNOLOGIES.
## A THREE-TIER WEB APPLICATION ARCHITECTURE, A SINGLE REMOTE MYSQL DATABASE AND AN NFS SERVER AS SHARED BACKEND STORAGE FILES. 
## Solution Prerequisites: Infrastruction: AWS. Three-Tier Webservers Linux: Redhat.  Database Server: Ubuntu + Mysql (Preferable but I used Redhat).  Storage server: Redhat + NFS Server.  Programming language: PHP. Code Repository: Github.  
## NOTE: Not all storage is suitable, hence it is important to know the suitable storage solution for every use case. Such as: what data will be stored, in what format, how this data will be accessed, by whom, from where, how frequently etc. Based on theses questions, I will be able to choose the right suitable storage for my solution. 
## SELF STUDY:
* Network attach storage (NAS) https://en.wikipedia.org/wiki/Network-attached_storage
* Storage area network (SAN) https://en.wikipedia.org/wiki/Storage_area_network, and related protocol like NFS(s), FTP, SMB, iSCSI.
* Block-level storage https://en.wikipedia.org/wiki/Block-level_storage and how it is used by cloud providers, and how it differs from Object Storage https://en.wikipedia.org/wiki/Object_storage.
* On the example of AWS services https://dzone.com/articles/confused-by-aws-storage-options-s3-ebs-amp-efs-explained, understand the difference between Block storage, Object storage and Network file system. 

## Creating a Business Website Using NFS For The Backend File Storage.
## STEP 1:PREPARE NFS SERVER
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

* Installing lvms packaging
<img width="852" alt="sudo yum install lvm2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/83eb3122-1987-4f22-8770-22d20954ddd8">

* Checking for available partition
<img width="445" alt="sudo lvmdiskscan" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/eb05f419-8a71-45b0-a3aa-03fb9a6b247e">

* Employing the "pvcreate" tool to designate each of the three disks as physical volumes for utilization by LVM
<img width="488" alt="pvcreate" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/33f822ef-982e-43ea-891f-8c85f3d1e8ef">

* PV has been created
 <img width="378" alt="sudo pvs" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b04cd710-681e-4b1c-9ba3-38b9840d8ead">
 
* Three logical volumes created.lv-apps stores website data. lv-logs stores log data, lv-opt stores ..... data.
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
