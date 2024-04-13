pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                    script {
                    sshagent(['Jenkinslave']) {
                        sh 'ssh -tt -o StrictHostKeyChecking=no jenkinsworker@192.168.0.112 "sudo yum update -y && sudo yum install -y epel-release && sudo yum install -y ansible"'
                    }
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
