pipeline {
          agent {
			label "ansible-control"
	}

          stages {
		stage ( " Install ansible, python, boto3 on the ansible control node ") {
			steps {
				sh '''sudo apt update 
				sudo apt install ansible -y
				sudo apt install python3-pip -y
    				sudo pip3 install boto
				sudo pip3 install botocore'''
			}
		}

	}
}

