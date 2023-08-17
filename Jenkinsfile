pipeline {
    agent any
    
    stages {
        stage('Ansible Deployment') {
            steps {
                sh 'ansible-playbook /home/vkambalapalli/ansi-train/web_app.yml -i /home/vkambalapalli/ansi-train/serverdetail'
            }
        }
    }
}
