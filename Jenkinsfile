pipeline {
	agent none
          stages {
		stage ( " Install ansible, python, boto3 on the ansible control node ") {
			agent {
       			         label "ansible-control"
        		}
			steps {
					sh " sudo apt update "
					sh " sudo apt install ansible -y "
					sh " sudo apt install python3-pip -y "
    					sh " sudo pip3 install boto "
					sh " sudo pip3 install botocore "
					sh " pwd "
				}
			}
		stage ("Copy ansible playbook, ansible configuration files, and ssh key file") {
                        agent any
				steps {
                                        sh " sudo scp -i ansi-jen /home/ubuntu/ansi-jen ubuntu@172.31.30.223:/home/ubuntu "
					sh " sudo scp -i ansi-jen /home/ubuntu/ansible.cfg ubuntu@172.31.30.223:/home/ubuntu "
					sh " sudo scp -i ansi-jen /home/ubuntu/playbookpoc.yml ubuntu@172.31.30.223:/home/ubuntu "
					sh " sudo scp -i ansi-jen /home/ubuntu/hosts ubuntu@172.31.30.223:/home/ubuntu "
				}
			}
		}
	}


