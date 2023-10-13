pipeline {
	agent none
          stages {
		stage ( " Install ansible, python, boto3 on the ansible control node ") {
			agent {
       			         label "ansible-control"
        		}
			steps {
				sshagent(['ansible-cred']) {
					sh " ssh -o StrictHostKeyChecking=no ubuntu@172.31.30.223 sudo apt update "
					sh " ssh -o StrictHostKeyChecking=no ubuntu@172.31.30.223 sudo apt install ansible -y "
					sh " ssh -o StrictHostKeyChecking=no ubuntu@172.31.30.223 sudo apt install python3-pip -y "
    					sh " ssh -o StrictHostKeyChecking=no ubuntu@172.31.30.223 sudo pip3 install boto "
					sh " ssh -o StrictHostKeyChecking=no ubuntu@172.31.30.223 sudo pip3 install botocore "
					sh " ssh -o StrictHostKeyChecking=no ubuntu@172.31.30.223 pwd "
				}
			}
		}
		stage ("Copy ansible playbook, ansible configuration files, and ssh key file") {
                        steps {
				agent any
                                sshagent(['ansible-cred']) {
                                        sh " sudo scp -o StrictHostKeyChecking=no /home/ubuntu/ansi-jen ubuntu@172.31.30.223:/home/ubuntu "
					sh " sudo cd  -o StrictHostKeyChecking=no /home/ubuntu/ "
				}
			}
		}
	}
}

