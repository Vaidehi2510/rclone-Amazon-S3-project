# rclone S3 Project
This project demonstrates how to use rclone to transfer files to Amazon S3, using a virtual linux environment from the host os as windows

## Prerequisites

- Chocolatey (package manager for windows for easy installation)
- Vagrant
- VirtualBox
- Amazon S3 account with Access Key ID and Secret Access Key
- Gitbash ( I have used the gitbash terminal to integrate Virtual Box and Vagrant)
## Setup

1. Install chocolatey package manager for windows
2. Install Vagrant,Gitbash and VirtualBox using chocolatey.
3. Set up and start your Vagrant CentOS VM:
   vagrant init centos/8
   vagrant up
   vagrant ssh
4. Install rclone on the CentOS VM:
   
   using yum (if rclone is available in your yum repository)
   - check if rclone is available
     sudo yum update -y
     sudo yum whatprovides rclone
     if present: sudo yum install rclone -y
  
   manually ( helps you install the latest version of rclone)
   sudo yum install -y curl unzip
   curl -O https://downloads.rclone.org/rclone-current-linux-amd64.zip
   unzip rclone-current-linux-amd64.zip
   cd rclone-(special char)-linux-amd64
   sudo cp rclone /usr/local/bin/
   sudo chown root:root /usr/local/bin/rclone
   sudo chmod 755 /usr/local/bin/rclone
5. Configure rclone with your Amazon S3 credentials:
   rclone config
6. To copy a file to Amazon S3, use the following command:
   rclone copy testfile.txt (remote name):bucket_name/path/in/bucket
   rclone copy testfile.txt file_transfer:bucketrclonefiletransfer/folder1


