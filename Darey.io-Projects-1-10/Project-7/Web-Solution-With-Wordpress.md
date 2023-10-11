#  WEB SOLUTION WORDPRESS WITH LVM (Logical Volume Mangement) STORAGE MANAGEMENT
## Understanding Three Tier Architecture
## Prerequisite: Provisioning Of Two AWS Ec2 Instances, Redhat Distribution For Web and Database Servers.



## Part 1: Configure Storage Subsystem For Web And Database Servers, Focusing On Disks, Partitions And Volumes In Linux

## Step 1

* Spining of a web and a database servers.
<img width="823" alt="two instances running 1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9f3af46f-c21c-4230-a012-40062d327bc4">

* Create three volumes in the same availability zones as my web server, each of 10 GiB and attach all three volumes one after the other to my web server Redhat Ec2  instance
<img width="779" alt="three volumes created 2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1f99bbab-34a8-4a17-8f81-4b1c833776e8">

* I open my terminal of choice
* With the command "sudo hostname wordpress-server" and bash, I change the IP address to wordpress-server
<img width="615" alt="to change Ip to hostname 3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/37d79aea-94a1-4e67-92b0-243ed0d050c3">

* Executing the "lsblk" command to examine the block devices connected to my server
<img width="598" alt="lsblk 4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/a07a6543-81ae-48ad-a254-5d491f1953ed">

* I Execute the command "ls /dev/" directory to view all three newly created blocks devices names:nvme0nlp2, nvme0nlp3, nvme0nlp4
<img width="885" alt="ls dev 5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b5e4f77d-ba25-45cd-a649-6feabcdc8ac1">

