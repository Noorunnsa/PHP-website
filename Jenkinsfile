pipeline {
    agent test-server
    stages {
        stage('Install Ansible') {
            steps {
                sh 'sudo yum update -y && sudo yum install epel-release -y && sudo yum install ansible -y'
            }
        }
        stage('Verify Ansible Installation') {
            steps {
                sh 'ansible --version'
                sh 'echo ============================================'
                sh 'Ansible is successully installed on Test server.'
            }
        }
    }
}
