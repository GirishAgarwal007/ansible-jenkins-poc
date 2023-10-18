pipeline {
	agent {
		label 'ansible-control'
	}
	stages {
		stage ("Pull Important files" ) {
						steps {
							sh "cd /home/ubuntu/ ; git clone https://github.com/GirishAgarwal007/ansible-jenkins-poc.git "
			}
		}
	}
}
