pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Terraform Setup and Apply') {
            steps {
                script {
                    sh 'terraform init'
                    sh 'terraform apply -auto-approve'
                }
            }
        }

        stage('Ansible Deployment') {
            steps {
                script {
                    sh 'ansible-playbook -i localhost, -c local /home/vkambalapalli/ansi-train/web_app.yml'
                }
            }
        }
    }
}
