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
                sh "echo aws_access_key_id: \${aws_access_key_id}"
                sh "echo aws_secret_access_key: \${aws_secret_access_key}"
                sh "echo aws_region: \${aws_region}"
                sh 'ansible-playbook -i /home/vkambalapalli/ansible-scripts/ec2.py web_app.yml'
            }
        }
    }
}
    }
}
