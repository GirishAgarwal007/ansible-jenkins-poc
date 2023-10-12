pipeline {
          agent {
			label "ansible-control"
	}

          stages {
		stage ( " Install ansible, python, boto3 on the ansible control node ") {
			steps {
				sh '''sudo apt update 
				sudo apt install ansible -y
				sudo apt-get -y install python3-boto3
				sudo apt-get -y install python3-botocore
				sudo apt install python3-pip -y
    				sudo pip3 install boto
				sudo pip3 install botocore'''
			}
		}

                stage ( "Pull ansible configuration files and inventory file" ) {
                        steps {
                                git branch: 'main', url: 'https://github.com/GirishAgarwal007/ansible-jenkins-poc.git'
                        }
                }
		stage ( "Change permission of key file" ) {
                        steps {
                                sh 'sudo chmod 400 ansi-jen'
                   	 }
                }
		stage ( " Run the playbook ") {
			steps {
				sh 'ansible-playbook playbookpoc.yml'
			}
		}
	}
}

