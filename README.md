
# Summary

This project demonstrates integration of Ansible and Jenkins.

## Project Description


1. Create and configure a dedicated server for Jenkins
2. Create and configure a dedicated server for Ansible Control Node
3. Write Ansible Playbook, which provision and configure 2 EC2 Instances with webserver ( httpd )
4. Add ansible node to Jenkins as a slave node for running Ansible playbooks
5. Configure Jenkins to execute the Ansible Playbook from Ansible Control Node
server as part of the CI/CD pipeline to configure new 2 ec2 instances with WebServer.
6. So the Jenkinsfile configuration will do the following:
  
- Get ansible playbooks from Github
- Run ansible playbooks which will provision 2 ec2 instances and then configure HTTPD on them which will show the Public IP of each instances.

## Table of contents

- [Launching two instances on AWS](#launching-two-instances-on-aws)
- [Configure Jenkins on first instance](#configure-jenkins-on-first-instance)

## Launching two instances on AWS 

The Amazon Web Services (AWS) platform provides more than 200 fully featured services from data centers located all over the world, and is the world's most comprehensive cloud platform.

- Step 1: Create an AWS account/ Login if have already
- Step 2: Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/ 
- Step 3: Click on "Launch instance"
- Step 4: Number of instances = 2
- Step 5: Choose an Amazon Machine Image (AMI) (ex: Ubuntu 22.04)
- Step 6: Choose an Instance Type (ex: t2.medium)
- Step 7: Select key Pair/ Creat new if not available
- Step 8: Configure Network Settings (Select VPC an Security Group)
- Step 9: Configure Storage
- Step 10: Click on "Launch instance"
- Step 11: port 22,80,8080 must be allowed in security group that you have attached with instance.

## Configure Jenkins on first instance
 
Jenkins is an open source continuous integration/continuous delivery and deployment (CI/CD) automation software DevOps tool written in the Java programming language. It is used to implement CI/CD workflows, called pipelines.

Follow the official document:
  https://www.jenkins.io/doc/book/installing/linux/ 

```bash
# installing Java
sudo apt update -you
sudo apt install default-jre
```

```bash
# installing jenkins 
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
```bash
# Verify the installation
  sudo jenkins --version
```
```bash
# Start Jenkins 
  sudo systemctl start jenkins
```
```bash
# Enable Jenkins
  sudo systemctl enable jenkins
```
```bash
# Check status of Jenkins
  sudo systemctl status jenkins
```
* Provide jenkins user sudo power:
sudo vim /etc/sudoers.d/jenkins
```bash
jenkins ALL=(ALL) NOPASSWD:ALL
```



