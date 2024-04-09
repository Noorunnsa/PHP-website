pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                   sh 'yum update -y && yum install epel-release -y && yum install ansible -y'
                }
            }
        stage('Verify Ansible Installation') {
            steps {
                sh 'ansible --version'
                sh 'echo ============================================'
                sh 'Ansible is successfully installed on Test server.'
            }
        }
    }
}
