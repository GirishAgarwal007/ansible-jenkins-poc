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
	stage ("Ansible Configurations") {
					steps {
						sh 'sudo chmod 400 sshkey '
					}
		
				}
	stage ("Run the Playbooks") {
				steps {
					sshagent(['ansible-cred']) {
 								sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.24.19 ansible-playbook -i new.aws_ec2.yml mainplay.yml "
								sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.24.19 sleep 30 "
                                                                sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.24.19 ansible-playbook -i new.aws_ec2.yml web.yml "
                                                        }
                        }
                }
	}
}					 
