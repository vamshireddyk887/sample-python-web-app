pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Copy Ansible Files') {
            steps {
                sh 'cp /home/vkambalapalli/ansi-train/inventory.ini .'
                sh 'cp /home/vkambalapalli/ansi-train/deploy.yml .'
            }
        }
        
        stage('Ansible Deployment') {
            steps {
                sh 'ansible-playbook -i inventory.ini deploy.yml'
            }
        }
    }
}
