#  WEB SOLUTION WORDPRESS WITH LVM STORAGE MANAGEMENT AND CONFIGURING TO USE MYSQL DATABASE.
## (Understanding Three Tier Architecture)
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

* Execute the command "sudo gdisk /dev/nvme0n1p2" to create a single partition (write) on disk 2
<img width="675" alt="disk-3 8" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c1a2017d-28ad-4780-aacb-e21370d87684">

* Execute the command "sudo gdisk /dev/nvme0n1p3" to create a single partition (write) on disk 3
<img width="741" alt="disk-two 7" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/46c724a8-1527-40f4-8d2a-1746abbb6cd8">

* Execute the command "sudo gdisk /dev/nvme0n1p4" to create a single partition (write) on disk 4
<img width="703" alt="disk -one 6" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c544fd96-0f54-4701-ab0b-4c7bfcc9b2e9">

* With the "lsblk" utility or service command, I can view the 3 storage/disk partition I just configured 
<img width="547" alt="review lsblk 9" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/3ff306a7-44ea-422a-a116-2008cecb9b26">

## Step 4
* To install 'lvm2 package to manage logical partition, I run the command "sudo yum install lvm2"
<img width="936" alt="sudo yum install lvm2 10" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/2386ed33-1bdd-427d-9829-b3da0a8fb547">

* I execute the command "sudo lvmdiskscan" command to check for available partition
<img width="669" alt="sudo lumdiskscan 11" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/4e20f8e6-ca34-4458-a50f-ad896c4371b6">

## Step 5
* To successfully create pysical volume on all 3 storage, I execute the command "sudo pvcreate /dev/nvme0n1p2, sudo pvcreate /dev/nvme0n1p3, sudo pvcreate /dev/nvme0n1p4
<img width="674" alt="pysical volume created 12" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1c4dd4ee-a234-4cd4-a081-1b16a29702c7">

*  I "sudo pvs" to confirm that my pysical volume was successful and running
<img width="551" alt="pvs created 13" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/824c7939-9f7a-46e5-ab14-71b77dca47b7">

## Step 6
* I run the "vgcreate" utility/service to add all three pysical volumes to one single volume group "Webdata-vg" 
<img width="872" alt="add all three volume to a volume group 14" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/cfc8aefb-d972-4f7c-8f21-a43eee88da51">

*  I "sudo vgs" to verify group was successful and running
<img width="588" alt="volume group running  using command 15" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/4b5d6727-1e77-43dd-bd19-66e5bcde19e0">


## Step 7
* I use the "lvcreate" service/utility, to create two volumes: apps-lv(stores data in the website) and log-lv (stores data in the log). Both volumes will split the PV size equally, 
<img width="663" alt="two logical volumes created 16" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/1d1f11d4-80c4-4adb-9e8d-fb0e90f65e60">

* "Sudo lvs" verifys creation of logical volumes was successful and running
<img width="727" alt="sudo lvs running 17" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9f75bfa6-cd19-437c-9100-830400a2f927">

## Step 8
* To verify the entire complete setup, I execute the command "sudo vgdisplay -v #view complete setup - VG, PV, and LV
sudo lsblk"
<img width="960" alt="Entire setup verified 18" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8a93c5ad-bf78-401d-a0fb-9115a951a442">

* Format the LV with the command "mkfs.ext4"
<img width="906" alt="format logical volumes 19" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b9014f42-17a4-4169-b99c-96d17e99ca75">

  ## Step 9
  * Create a  "/var/www/html" dir to store website files, 
<img width="654" alt="create directory, store backup log data and mount LV 20" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/f203d2a1-c482-4e30-86d5-1bdc432a5d1b">

* Create another dir "/home/recovery/logs" to store backup of log data
<img width="870" alt="using rsync to back up  files in var log to home recovery log 21" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/79e5387a-341f-4ff8-a55a-848631335e2f">

## Step 10
* Mount /var/www/html on apps-lv
<img width="581" alt="sudo mount dev web data  22" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c661f75b-1d22-4f7c-8f84-4c42100f7b80">

* After previously deleting existing data on /var/log, I executed the command  "sudo mount /dev/webdata-vg/logs-lv /var/log" to mount /var/log on logs/lv logical volume

* I "sudo rsync -av /home/recovery/logs/log/. /var/log" to restore deleted log data back to /var/log

* Before mounting up the file system, I use  the rsync utility to backup all files in /var/log to /home/recovery/logs
<img width="954" alt="sudo rsync -av home 23" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/e0fca952-d055-46f5-8e73-15f8a9ff3d8e">

* I "sudo blkid" to display information about block devices
<img width="919" alt="sudo blkid 24" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/7c3501b1-b4c3-4906-9373-1d7ca3046bd9">

* I sudo vi "/etc/fstab" to update my UUID (Universally Unique identifier)
<img width="851" alt="sudo vo etc-fstab 25" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/3d9656c7-5439-4ae4-91d2-170493de1dc7">


* Test the configuration and reload the deamon, 
<img width="418" alt="sudo mount -a and sudo systemctl deamon reload  25" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9846f41b-c4ec-4ec1-a2d8-6cdce365bc01">

* Setup is running
<img width="685" alt="verify setup with the command df -h 26" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/8f382bf2-1743-43b3-a17c-980f688c8af5">


# PART 2: CONFIGURING MYSQL DATABASE

* Step 1:
* Spined up a Database Ec2 instance
* Created 3 volume and attached to Database Server
  
Execute the command "lsblk" to view blocks attached to server
<img width="477" alt="db1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/5d99dbe2-d8c3-43ee-a42e-b0b69b25ce35">

* Run "dh -f" to view all mounts and free space in server
<img width="495" alt="db2" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/18af12c8-a244-425e-a0ce-27f5af3b9831">

* Execute "sudo gdisk /dev/nvme0n1p4" to write partition on  disk
<img width="517" alt="db3" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/ecc0846d-0465-4e02-8118-fc7f6dc1fe93">

* Execute "sudo gdisk /dev/nvme0n1p3" to write partition on  disk
<img width="691" alt="db4" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/45d7ff4b-e352-476c-a74c-2e56b27756ae">

* Execute "sudo gdisk /dev/nvme0n1p2" to write partition on  disk
<img width="730" alt="db5" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c546aa46-c688-4661-8475-cbfb646a6cc2">
 
