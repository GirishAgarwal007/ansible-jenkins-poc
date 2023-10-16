pipeline {
	agent {
		label 'ansible-control'
	}
	stages {
		stage ("Pull Important files" ) {
						steps {
							git branch: 'main', url: 'https://github.com/GirishAgarwal007/ansible-jenkins-poc.git'
						}
					}
				}
			}
							 
