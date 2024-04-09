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
                        sh 'ssh -tt -o StrictHostKeyChecking=no jenkinsworker@192.168.0.112 "sudo yum update && sudo yum install -y epel-release && sudo yum install -y ansible"'
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
