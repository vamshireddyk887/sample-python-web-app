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
                sh 'cp /home/vkambalapalli/ansi-train/serverdetail .'
                sh 'cp /home/vkambalapalli/ansi-train/web_app.yml .'
            }
        }
        
        stage('Ansible Deployment') {
            steps {
                sh 'ansible-playbook -i serverdetail web_app.yml'
            }
        }
    }
}
