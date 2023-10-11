#  WEB SOLUTION WORDPRESS WITH LVM (Logical Volume Mangement) STORAGE MANAGEMENT
## Understanding Three Tier Architecture
## Prerequisite: Provisioning Of Two AWS Ec2 Instances, Redhat Distribution For Web and Database Servers.



## Part 1: Configure Storage Subsystem For Web And Database Servers, Focusing On Disks, Partitions And Volumes In Linux

## Step 1

* Spining of a web and a database servers.
<img width="823" alt="two instances running 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9f3af46f-c21c-4230-a012-40062d327bc4">

* Create three volumes in the same availability zones as my web server, each of 10 GiB and attach all three volumes one after the other to my web server Redhat Ec2  instance
<img width="779" alt="three volumes created 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1f99bbab-34a8-4a17-8f81-4b1c833776e8">

## Step 2
* I open my terminal of choice
* With the command "sudo hostname wordpress-server" and bash, I change the IP address to wordpress-server
<img width="615" alt="to change Ip to hostname 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/37d79aea-94a1-4e67-92b0-243ed0d050c3">

## Step 3
* Executing the "lsblk" command to examine the block devices connected to my server
<img width="598" alt="lsblk 4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/a07a6543-81ae-48ad-a254-5d491f1953ed">

* I Execute the command "ls /dev/" directory to view all three newly created blocks devices names:nvme0n1p2, nvme0n1p3, nvme0n1p4
<img width="885" alt="ls dev 5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b5e4f77d-ba25-45cd-a649-6feabcdc8ac1">

*  Running the "df -h" command to view all mounts and free space on my server
<img width="681" alt="5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/07336010-2bc1-4e0d-9b12-eb4c340d7e61">

* To check the version of my disk, I run the "gdisk" command,   
<img width="546" alt="gdisk 6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b8a26bf1-8e3e-4bd1-8949-13ffad7a3c6a">

* Execute the command "sudo gdisk /dev/nvme0n1p2" to create a single partition on disk 2
<img width="675" alt="disk-3 8" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c1a2017d-28ad-4780-aacb-e21370d87684">

* Execute the command "sudo gdisk /dev/nvme0n1p3" to create a single partition on disk 3
<img width="741" alt="disk-two 7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/46c724a8-1527-40f4-8d2a-1746abbb6cd8">

* Execute the command "sudo gdisk /dev/nvme0n1p3" to create a single partition on disk 3
<img width="703" alt="disk -one 6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c544fd96-0f54-4701-ab0b-4c7bfcc9b2e9">
