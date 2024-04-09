pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                sshagent (credentials: ['jenkinsworker']) {
         sh "ssh jenkinsworker@192.168.0.112 sudo yum update -y"
         sh "ssh jenkinsworker@192.168.0.112 sudo yum install epel-release -y"
         sh "ssh jenkinsworker@192.168.0.112 sudo yum install ansible -y"
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
