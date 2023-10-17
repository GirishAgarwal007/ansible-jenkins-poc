
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


