pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/VikramGitH/jenkins-ansible-ubuntu24.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'ansible/playbook-nginx.yml',
                    inventory: 'ansible/inventory.ini',
                    credentialsId: 'jenkins-ansible-ssh-ubuntu24',
                    disableHostKeyChecking: true
                )
            }
        }
    }
}

