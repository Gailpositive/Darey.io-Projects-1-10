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
 
