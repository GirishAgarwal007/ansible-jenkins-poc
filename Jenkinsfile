pipeline {
	agent any
          stages {
		stage ( " Install ansible, python, boto3 on the ansible control node ") {
			steps {
				sshagent(['ansible-cred']) {
					sh '''sudo apt update 
					sudo apt install ansible -y
					sudo apt install python3-pip -y
    					sudo pip3 install boto
					sudo pip3 install botocore
					pwd'''
				}
			}
		}
		stage ("Copy ansible playbook, ansible configuration files, and ssh key file") {
                        steps {
                                sshagent(['ansible-cred']) {
                                        sh ''' scp /root/ansi-jen ubuntu@172.31.30.223:/home/ubuntu
					       cd /home/ubuntu/ '''
				}
			}
		}
	}
}

