pipeline {
    agent {
        label 'test-server'
    }
    environment {
        SUDO_PASS = credentials('jenkinsworker')
    }
    stages {
        stage('Install Ansible') {
            steps {
                   script {
                    sh "echo $SUDO_PASS | sudo -S yum update -y"
                    sh "echo $SUDO_PASS | sudo -S yum install epel-release -y"
                    sh "echo $SUDO_PASS | sudo -S yum install ansible -y"
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
