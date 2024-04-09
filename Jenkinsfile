pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                   script
                       {
                   sh """ssh -tt jenkinsworker@192.168.0.112 'sudo yum update -y'"""
                       }
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
