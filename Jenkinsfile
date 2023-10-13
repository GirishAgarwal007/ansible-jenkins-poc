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

	}
}

