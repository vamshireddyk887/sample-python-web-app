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
            dir('/home/vkambalapalli/ansi-train') {
                script {
                sh "echo AWS_ACCESS_KEY_ID: \${AWS_ACCESS_KEY_ID}"
                sh "echo AWS_SECRET_ACCESS_KEY: \${AWS_SECRET_ACCESS_KEY}"
                sh "echo AWS_REGION: \${AWS_REGION}"
                sh 'ansible-playbook -i /home/vkambalapalli/ansible-scripts/ec2.py web_app.yml'
            }
        }
    }
}
    }
}
