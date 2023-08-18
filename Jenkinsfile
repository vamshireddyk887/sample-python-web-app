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
                    dir('/home/vkambalapalli/terra-proj2') {
                        sh 'ls -l /var/lib/jenkins/workspace'
                        sh 'chmod -R 755 /home/vkambalapalli/terra-proj2'
                        sh 'terraform init'
                        sh 'terraform apply -auto-approve'
                    }
                }
            }
        }

        stage('Ansible Deployment') {
            steps {
                script {
                    sh 'ls -l /home/vkambalapalli/ansi-train'
                    sh 'ansible-playbook -i localhost, -c local /home/vkambalapalli/ansi-train/web_app.yml'
                }
            }
        }
    }
}
