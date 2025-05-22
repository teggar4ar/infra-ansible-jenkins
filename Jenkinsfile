pipeline {
    agent any
    environment {
        ANSIBLE_FORCE_COLOR = 'true'
    }
    stages {
        stage('Checkout Source') {
            steps {
                git url: 'https://github.com/orion2182/infra-ansible-jenkins.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sshagent(['ansible-ssh-key']) {
                    sh 'ansible-playbook -i hosts.ini deploy.yml'
                }
            }
        }
    }
}
