pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                    script {
                    sshagent(['Jenkinslave']) {
                        // SSH into your Linux VM and install Ansible
                        sh 'ssh -o StrictHostKeyChecking=no jenkinsworker@192.168.0.112 "sudo apt update && sudo apt install -y ansible"'
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
