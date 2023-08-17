pipeline {
    agent any
    
    stages {
        stage('Ansible Deployment') {
            steps {
                sh 'ansible-playbook web_app.yml -i serverdetail'
            }
        }
    }
}
