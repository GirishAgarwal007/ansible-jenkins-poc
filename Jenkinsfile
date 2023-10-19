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
		stage ("Run the Ansible Playbooks") {
						steps {
							sh "cd /home/ubuntu/ansible-jenkins-poc/ ; ansible-playbook ec2_playbook.yml -e key=$key region=$region insta_type=$insta_type ami=$ami sg_group=$sg_group subnet=$subnet "
							sh " sleep 60"
							sh "cd /home/ubuntu/ansible-jenkins-poc/ ; ansible-playbook webserver.yml "
	}
}
