pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                   script {
                    sh "sudo -S yum update -y"
                    sh "sudo -S yum install epel-release -y"
                    sh "sudo -S yum install ansible -y"
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
